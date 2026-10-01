# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: bloqueada
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”
- teste_humano: pendente
- verificacao_automatica: pendente
- aprendizado: pendente
- duvidas:
  - DÚVIDA (Kim/TI-OT): integração contínua ao TOTVS PIMS MI como fonte única — caminho de leitura, frequência e autorização pendentes.
  - DÚVIDA (Luís, 01/10): decisões de mapeamento da planilha recebida — chave única do ativo, tratamento das 1.100 linhas sem status e semântica da coluna APAGAR.
- ultima_acao: Planilha de ativos recebida e analisada (1.926 registros na Base Montagem, 127 na TAG Localização). Achados registrados no changelog: TAG de localização não é chave única, 1.100 sem status, 4 sem criticidade, coluna APAGAR ambígua, sem coluna de sensores. Decisões de mapeamento pedidas a Luís.
- proxima_acao: com as decisões de Luís, implementar esquema versionado, fixture sintética com casos RED e validação da importação da planilha no Skip
- atualizado_em: 2026-10-01T12:20:00-03:00
