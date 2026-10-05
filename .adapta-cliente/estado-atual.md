# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: em_correcao
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”; decisões de mapeamento dadas em 2026-10-01 — “Código como chave única”, “Importar como componentes”, “Ignorar coluna APAGAR”.
- teste_humano: falhou em 2026-10-02T08:37:00-03:00 — Luís: “Encontrei uma falha no teste”. Em 2026-10-05T16:29 Luís anexou a planilha corrigida (0ab918e8-completo.xlsx, SHA-256 092a8e40…) com a coluna “Código” adicionada pelo PCM e perguntou sobre a origem das colunas exigidas e o que falta para concluir a T1.1.
- verificacao_automatica: passou na última execução registrada — Skip QA e fixture sintética 12/12 antes do relato de falha humana. Em 2026-10-05T16:32 o validador v1.0.0 foi executado localmente contra a planilha corrigida no mapeamento do modelo da moenda (TAG curta = ativo; TAG composta = componente; coluna Código do PCM como identificador; aba TAG Localização gerada das 8 TAGs curtas): 135 de 226 registros aceitos; bloqueios remanescentes: MISSING_ASSET_CLASS 87 e SENSOR_REQUIREMENT_UNDEFINED 87 (pendências conhecidas da Fase 1, não defeito da planilha) e PARENT_ASSET_UNRESOLVED 4 (2 casos de TAG de pai com erro de grafia: RE07 vs RS07 linha 122, TQ09 vs TQ109 linha 191). MEL0579 confirmado corrigido: aparece apenas na linha 147 (TAG 1-0003-04-ET26-1-1).
- aprendizado: pendente
- ultima_acao: Revalidação completa da planilha corrigida executada com sucesso; duplicidade de código eliminada (Código único nas 226 linhas); 2 bloqueios de dados reais identificados (grafia de TAG de pai em 2 famílias) e 2 pendências estruturais (coluna Classe e regra de sensores por classe, que dependem de homologação do PCM/consultoria).
- proxima_acao: PCM corrigir a grafia das TAGs de pai (1-0003-03-RE07-* → RS07; 1-0003-07-TQ09-* → TQ109) ou confirmar qual grafia é a correta; Kim decidir a emenda v1.1.0 do validador (modelo da moenda) registrada no changelog; classe/sensores por classe seguem para homologação na T1.2.
- atualizado_em: 2026-10-05T16:32:06-03:00
