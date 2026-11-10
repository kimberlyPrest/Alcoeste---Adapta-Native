# Estado atual — Adapta Cliente

- task_id: T3.3
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-003.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: confirmada — Luís autorizou em 05/11/2026 ("Sim") implementar o lacre de procedência do catálogo, após a auditoria de campos.
- teste_humano: pendente — Luís abrir `artifacts/T3.3-teste-humano-abra-este-arquivo.html` (68/68) e confirmar. A homologação formal do CA-1-009 é da consultora (Kim).
- verificacao_automatica: passou — 68/68 testes em pacote limpo reextraído do zip v1.3 (27 contrato + 41 integridade/catálogo/reentrada); HTML 68/68 no navegador; provas em dado real passam declarando o hash calculado do arquivo lido; baseline real 14/15 = 93,3%; auditoria de campos em 9 lidos / 10 sem efeito.
- aprendizado: registrado — AP-2026-11-05-b e -c (campo sem consumidor; lacre do dado de entrada).
- ultima_acao: T3.3 v1.3 (zip 9ca8b57a). **Auditoria de campos** (autorizada por Luís): 19 campos testados por comportamento — 9 provados lidos, 10 sem efeito. Método em duas verificações porque a estática mente: o nome aparecer no código não significa ser lido (`reason` e `approvalRef` aparecem só em comentário). Script `auditar-campos.mjs` deixa a varredura repetível. **Achado de risco ALTO corrigido:** `catalogBaseline.reference` nunca era conferido — o contrato selava a si mesmo (digest) e aceitava qualquer dataset, exibindo número com `baselineValid: true`. Implementado: o dataset declara `catalogReference` (SHA-256 do arquivo) e o cálculo compara; sem declaração → `CATALOG_REFERENCE_MISSING`; divergência → `CATALOG_REFERENCE_MISMATCH`; ambos bloqueiam os três KPIs com `value: null`. Sem override — mudança legítima exige nova versão do contrato. As duas provas em dado real passaram a calcular o hash do arquivo que leem, então o lacre morde de verdade. **Pendências de risco médio declaradas (não corrigidas, decisão do cliente):** `windows.safra.startsMonth/endsMonth` são ignorados (janela "safra" aceita jan-fev e exibe rótulo Safra); `qualityRule` promete avaliar qualidade (SPEC-1-004) que ainda não existe. Risco baixo: `inconclusiveWhen`, `blockedWhen`, `category`, `reason`, `approvalRef`, `states`, `spec`, `briefing` descrevem mas não governam.
- proxima_acao: Luís abrir o HTML e confirmar; depois encaminhar `T3.3-dossie-homologacao.md` + `T3.3-auditoria-campos-contrato.md` + zip v1.3 para a Kim homologar o CA-1-009, com as duas pendências de risco médio declaradas (dono e gatilho explícitos). Só depois a T3.3 fecha.
- bloqueio_declarado: homologação do CA-1-009 depende da consultora. K2 segue inconclusivo — sem base de OS da moenda.
- atualizado_em: 2026-11-10T09:25:00-03:00
