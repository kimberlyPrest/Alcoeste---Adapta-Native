# Termo de Homologação — Catálogo de Ativos da Moenda (SPEC-1-001)

**Task:** T1.3 — Homologar e congelar a versão do catálogo e suas exclusões
**Data:** 2026-10-19
**Homologador:** Luís Arakaki (Diretor-Presidente, Alcoeste Bioenergia)
**Autorização:** "Posso estar implementando agora, e caso a Kim divergir reverter as alterações?" (19/10, 09:28)
**Teste humano:** APROVADO — "Realizei o teste humano, 226/226 aceitos, 0 bloqueados" (19/10, 09:56)
**Validação do rascunho Família→Classe:** APROVADA pelo homologador na mesma mensagem — as 23 famílias da moenda deixam de ser rascunho e passam a vocabulário homologado do catálogo.
**Precedente de reversibilidade:** emendas v1.1.0/v1.2.0 aplicadas sob autorização do cliente com homologação da consultora pendente; se Kim divergir, reverte-se para a versão anterior documentada abaixo, sem perda de histórico.

## Versão congelada

| Artefato | Identificador | SHA-256 |
|---|---|---|
| Planilha do catálogo (dados) | b15a040c-completo.xlsx | `5e751003e4984cc8d94b0e790c1daa4b7922d0777871ee2e1fe85b65c80fb711` |
| Contrato de validação | v1.2.0 (schema-v1-2.js) | `6c23017b458d678d520026cdc5c8d31805ec5c07e2258384b3c76c583fcf7230` |
| Validador | validate.js | `db83e0673ccb30ede70cd8943b775b201f9fc57db6a09fd45d8dae8ed67ace0d` |
| Leitor | readWorkbook.js | `5daa40f9afd892742593d8be32f5bc7e61b529889618b263da87fedf2a2959c4` |
| App Skip | projeto 57219, versão 0.0.10 / hash 15fb6d4 (development, não publicada) | — |

## Conteúdo do catálogo congelado

- **226 registros: 83 ativos + 143 componentes**, 8 localizações, zero bloqueios.
- **Classe derivada da Família** — tabela Família→Classe das 23 famílias da moenda, HOMOLOGADA pelo Diretor-Presidente em 19/10 (promovida de rascunho).
- **Cobertura (política criticidade-rotativo):** 9 covered (pontos IoTebe) · 12 uncovered — lacunas explícitas de criticidade A (TM01-05, PR01-03, HI01-02, ET09, PI02) · 19 not-required (B/C rotativos) · 47 not-applicable (estáticos).
- **Re-modelagem aprovada pelo PCM (19/10):** MEL0097, BBA0053, MEL0096, BBA0054 (motores/bombas de lubrificação, criticidade C) reclassificados como componentes dos ativos LB05/LB06 — "Sistemas de lubrificação" (família LB, estática). O pai possui família; componentes não exigem.

## Exclusões do universo inicial (CA-1-003)

**Zero exclusões.** Nenhum registro foi excluído do universo; o denominador de K1 permanece integral (226 registros, 83 ativos). A prova de exclusão sem aprovação permanece coberta pela fixture RED da T1.1 (EXCLUSION_NOT_APPROVED bloqueia).

## Provas executadas (19/10)

1. **Revalidação do congelado (caminho completo da app):** 226/226 aceitos, 0 bloqueados, cobertura 9/12/19/43.
2. **Regressão de versionamento (TDD REFACTOR/REGRESSÃO da SPEC):** cópia do catálogo com mutação controlada de criticidade (TM01: A→B, linha 132, coluna 9 — único diff auditável) → validador reclassifica TM01 de `uncovered` para `not-required` (uncovered 12→11); **original permanece íntegro** (SHA idêntico antes e depois da prova) e a alteração fica auditável no diff célula a célula. PASSOU.
3. **Regressão automatizada:** 14/14 testes do contrato v1.2.0 passando.
4. **Verificação independente pós-teste humano:** SHA da planilha e dos 3 arquivos do contrato idênticos aos do termo; revalidação completa 226/226; 12 lacunas todas criticidade A; sem persistência nem envio ao Skip Cloud.
5. **Caminhos de erro da SPEC** (provas da T1.2, vigentes): arquivo vazio bloqueia; família vazia bloqueia para o PCM; ativo sem sensor nunca aparece coberto/saudável (CA-1-002).

## Reversão

- Restaurar `validate.js`, `schema-v1-2.js`, `readWorkbook.js` da versão 0.0.9 (hash 0a28eb9) — instrução documentada nos próprios arquivos (adapta-divida: unificar quando a Kim homologar).
- A planilha b15a040c permanece como dado de entrada versionado; reverter o contrato não apaga o histórico de homologação deste termo.

## Pendências externas (não bloqueiam o congelamento)

- Homologação da Kim das emendas v1.1.0/v1.1.0b/v1.2.0 (pendente desde 02/10; escalada em 13/10). Precedente: aplicação autorizada pelo cliente com reversão garantida.
- ~~Validação do rascunho Família→Classe pelo PCM (23 famílias)~~ RESOLVIDA em 19/10 — validada pelo homologador.
