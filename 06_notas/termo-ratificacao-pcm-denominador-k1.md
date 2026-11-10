# Termo de Ratificação do Denominador do K1

**Ratificador:** Gustavo Godoy — PCM (Planejamento e Controle de Manutenção)
**Solicitante:** Luís Arakaki — Diretor-Presidente
**Data:** 2026-11-05
**Documento respondido:** `Ratificacao-PCM-denominador-K1-RESPONDIDO.docx` · SHA-256 `078dbd1d4909cb6c5efed2b04665848638e75ee7dce9ca60ae9f9dc1b0896a85`

## Respostas

| # | Pergunta | Resposta | Comentário |
|---|---|---|---|
| 1 | Os 15 ativos são o recorte correto dos críticos da moenda? | **SIM** | — |
| 2 | As 6 exclusões procedem? | **SIM** | "Caso o cenário mude, irei informar para serem incluídos na contagem." |
| 3 | Ternos TM01–TM05 contam como cobertos pela cadeia AC01–AC03? | **SIM** | "Hoje temos sensores nos mancais e volandeiras dos acionamentos." |

**Denominador de 15 ativos ratificado.** K1 de referência: 14/15 = 93,3%.

## Defeito encontrado a partir do comentário da pergunta 2

O PCM disse que **avisaria** quando o cenário mudasse — o que revela que o negócio conta com a **reentrada automática** prometida no contrato. Verificado: a promessa **não era cumprida**. O campo `reentryOnActive: true` existia, mas o cálculo nunca o lia. O PI02 voltaria a operar e seguiria fora do denominador, em silêncio.

**Correção:** o cálculo passa a ler `reentryOnActive`. Ativo excluído por estado, com leitura válida na janela, reentra sozinho com registro `REENTRY_ON_ACTIVE`, usando o mesmo critério de "coberto" do resto do K1. Exclusões de segurança (HI01, HI02, PR01–PR03) nunca reentram.

| Situação do PI02 | Denominador | Aviso |
|---|---|---|
| Parado (sem leitura) | 15 | não |
| Operando (leitura válida) | 16 | `REENTRY_ON_ACTIVE` |
| Leitura inválida | 15 | não |
| Leitura fora da janela | 15 | não |

## Evidência

62/62 testes (27 contrato + 35 integridade/reentrada), pacote limpo reextraído; HTML 62/62 no navegador; baseline real segue 14/15 = 93,3%; prova do CA-1-009 mantida nos 5 cenários. ZIP v1.2: `ae13d9cb41dd0ff28d894ecd605be81e9095641351b828941612ddf3b5091ad3`.

## Efeito na T3.3

Pendência "ratificação do PCM sobre o denominador" **ENCERRADA**. Permanecem: taxonomia formal de falha/parada (aberta, não bloqueia) e donos por nome (PCM agora nomeado). A homologação do CA-1-009 continua sendo da consultora.
