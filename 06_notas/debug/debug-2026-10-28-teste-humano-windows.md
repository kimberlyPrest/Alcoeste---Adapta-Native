# Debug Summary — T3.1 · erro ao abrir o teste no Windows

**Data:** 2026-10-28 · **Champion:** Marie Egashira · **Task:** T3.1 · **Ambiente:** Windows 10/11, duplo clique no arquivo

## Task e problema

Ao extrair `T3.1-contrato-kpis-v1.0.0.zip` e abrir `kpiContract.test.js` no Windows, aparece a caixa "Windows Script Host":

```
Script: C:\Users\...\T3.1-contrato-kpis-v1.0.0\kpiContract.test.js
Linha: 5
Caract.: 1
Erro: Erro de sintaxe
Código: 800A03EA
Origem: Erro de compilação do JavaScript
```

## Reprodução

1. Causa determinística e independente do conteúdo do contrato: qualquer `.js` com `import` de ES module aberto por duplo clique no Windows falha igual.
2. `kpiContract.test.js` linha 5 é `import test from 'node:test'`.
3. `800A03EA` = erro de compilação no motor **JScript** do Windows Script Host, que só entende ECMAScript 3/5 e não possui `import`, `export`, módulo nem `node:test`.

## Causa raiz

**Não é falha do contrato nem do cálculo.** O Windows associa a extensão `.js` ao **Windows Script Host**, não ao Node.js. O arquivo foi executado pelo motor errado. O contrato está íntegro: os mesmos 27 testes passam no ambiente correto (27/27 em Node e 27/27 no navegador, ambos reexecutados nesta correção).

**Causa raiz de processo:** a entrega do teste humano exigia abrir terminal e rodar `node --test`. Instrução tecnicamente correta, mas com atrito real para quem não vive no terminal — e o gate de teste humano existe para o dono validar o resultado, não para provar destreza com CLI.

## Correção

Entrega de um **artefato de teste humano sem instalação**:

- `T3.1-teste-humano-abra-este-arquivo.html` — arquivo único, aberto por duplo clique no navegador padrão do Windows. Injeta o contrato, o cálculo e **as mesmas 27 asserções** do teste automatizado, com um shim mínimo de `node:test`/`node:assert` (sem reimplementar as assertivas). Mostra o placar, a lista dos 27 testes com status e 11 provas em dado real. Nada é enviado para fora: roda localmente.
- `build-teste-humano.mjs` — gerador do HTML a partir das fontes, para o HTML não divergir do teste automatizado em versões futuras.
- O HTML foi **verificado no navegador antes da entrega**: 27/27 testes e 11/11 provas, com captura de tela registrada em `captura-teste-humano.png`.

## Verificação automática

| Prova | Resultado |
|---|---|
| `node --test kpiContract.test.js` | 27/27 |
| `node --test validate.test.js` (regressão T1.2) | 14/14 |
| `node prova-baseline-real.mjs` | K1 14/15 = 93,3% · reproduz o briefing v1.0 |
| `node prova-comparabilidade.mjs` | CA-1-009 bloqueia sem aprovação · CA-1-008 não fabrica 100% |
| HTML no navegador (verificação do próprio artefato) | 27/27 testes · 11/11 provas |

## Gate atual

Encerrado — teste humano aprovado por Luís em 28/10 07:54 ("Certo, agora o teste funcionou") e task concluída.

## Aprendizado

Sinal capturado: **teste humano precisa de artefato de clique único.** Entregar pacote de engenharia com instrução de terminal transfere o atrito para o dono e pode ser confundido com falha do produto (o erro do Windows Script Host parecia erro do contrato). Para as próximas tasks com entrega verificável, incluir na própria entrega um visualizador HTML autocontido, gerado a partir dos mesmos testes, e nunca exigir instalação de runtime para o gate humano.
