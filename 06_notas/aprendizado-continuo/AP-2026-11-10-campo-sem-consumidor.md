# AP-2026-11-10 — Campo documentado que o código não lê é promessa quebrada

**Task:** T3.3 · **Data:** 2026-11-10 · **Origem:** revisão do CA-1-009 antes da homologação e comentário do PCM na ratificação do denominador

## O padrão

Três vezes no mesmo contrato, o documento prometia um comportamento e o código não executava. Nenhuma delas produzia erro: o sistema simplesmente não fazia o que prometia, em silêncio.

| # | Campo | Prometia | Fazia | Como apareceu |
|---|---|---|---|---|
| 1 | proteção de meta/fórmula/janela | mudança exige versão aprovada | só o denominador era protegido | revisar o critério como ataque |
| 2 | `reentryOnActive` | PI02 reentra ao voltar a operar | nunca lido | comentário do PCM: "caso o cenário mude, irei informar" |
| 3 | `catalogBaseline.reference` | fixa o catálogo | nunca conferido | auditoria de campos |

O achado 1 e o 3 vieram de **procurar o defeito de propósito**. O achado 2 veio de **ler o que o cliente escreveu** — o PCM disse que avisaria quando o cenário mudasse, o que só faz sentido se o sistema não avisasse sozinho. A frase do cliente era o teste.

## O que fazer

1. **Testar o critério de aceite como ataque, não reler o código.** "Alteração exige aprovação" vira: editar cada campo e ver se alguém acusa.
2. **Ler o que o cliente escreve como especificação.** Se ele descreve um comportamento ("eu aviso"), verificar se o sistema já não deveria fazer isso sozinho.
3. **Auditar campos por comportamento, não por leitura de código.** A checagem estática mente: `reason` e `approvalRef` aparecem no código, mas só dentro de um laço que monta mensagem — não governam nada. Editar o campo, re-selar o contrato e ver se o resultado muda é o teste que vale. Script: `auditar-campos.mjs`.
4. **Ao implementar um contrato, listar todo campo que existe e não é lido.** Cada um é uma promessa pendente de auditoria.

## Detalhes técnicos que custaram tempo

- **Lacre que não lacra:** digest calculado em tempo de carga muda junto com a edição e nunca acusa. Tem de ser **literal** no arquivo. E o literal sozinho não basta: sem registro de versões aprovadas, basta editar e recalcular o digest.
- **Selo do papel, porta do dado aberta:** o contrato sela a si mesmo mas aceitava qualquer dataset. O lacre do dado de entrada (`catalogReference`) é parte do mesmo problema.
- **Prova que sempre passa:** as provas em dado real copiavam a constante do contrato como hash do catálogo. Corrigido para **calcular o hash do arquivo que leem** — assim o lacre morde de verdade.
- **`severity` sobrescrito:** ao montar a issue com espalhamento (`{ ...problema }`), o `severity: 'blocking'` do helper era apagado pelo `undefined` do objeto espalhado. O código aparecia na lista, mas o `baselineValid` continuava `true`.
- **Teste contaminado:** a auditoria rodava tudo na janela `mensal` e com dataset completo, então campos de janela e de cobertura nunca eram exercitados e apareciam como "não lidos". Cada sonda precisa do cenário que ativa o campo.

## Regra que fica

> Antes de declarar um contrato pronto, levantar todo campo folha e provar, por comportamento, que ele é lido — ou declarar que é documentação. Campo sem consumidor é dívida invisível: o documento fica correto e o sistema, mentiroso.
