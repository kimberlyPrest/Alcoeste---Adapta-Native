# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: em_correcao
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”; decisões de mapeamento dadas em 2026-10-01 — “Código como chave única”, “Importar como componentes”, “Ignorar coluna APAGAR”.
- teste_humano: falhou em 2026-10-02T08:37:00-03:00 — Luís: “Encontrei uma falha no teste”. Em 2026-10-05T16:29 Luís anexou a planilha corrigida (0ab918e8-completo.xlsx, SHA-256 092a8e40…) com a coluna “Código” adicionada pelo PCM.
- verificacao_automatica: passou na última execução registrada — Skip QA e fixture sintética 12/12 antes do relato de falha humana. Em 2026-10-05T16:32 o validador v1.0.0 executado localmente contra a planilha corrigida no mapeamento da moenda: 135/226 aceitos; bloqueios: MISSING_ASSET_CLASS 87 e SENSOR_REQUIREMENT_UNDEFINED 87 (homologação T1.2) e PARENT_ASSET_UNRESOLVED 4 (grafia RE07≠RS07 linha 122, TQ09≠TQ109 linha 191). MEL0579 confirmado corrigido (só linha 147).
- aprendizado: pendente
- ultima_acao: Em 2026-10-13T08:25 Luís informou que ainda se aguarda a validação da emenda. Verificado no handoff: nenhuma decisão da consultora desde a DÚVIDA de 02/10 — changelog sem entrada nova entre 05/10 e 13/10, tabela de Emendas da SPEC-1-001 vazia, estado inalterado. Escalada registrada no changelog (commit 431748b9); Luís orientado a cobrar a decisão diretamente com a consultora.
- proxima_acao: Luís cobrar a decisão da emenda v1.1.0 diretamente com a consultora (mensagem pronta foi entregue); em paralelo, PCM corrigir as 2 grafias de TAG de pai (RE07→RS07, TQ09→TQ109). Com a decisão em mãos, implementar a v1.1.0 e revalidar a planilha no app.
- atualizado_em: 2026-10-13T08:26:00-03:00
