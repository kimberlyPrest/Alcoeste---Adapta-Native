# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: em_correcao
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”; decisões de mapeamento dadas em 2026-10-01 — “Código como chave única”, “Importar como componentes”, “Ignorar coluna APAGAR”.
- teste_humano: falhou em 2026-10-02T08:37:00-03:00 — Luís: “Encontrei uma falha no teste”. Em 2026-10-02T08:44 Luís instruiu: “ignore o erro mencionado. substitua a planilha ‘Equipamentos - Copia’ pela planilha em anexo, e veja se os requisitos da task atual foram preenchidos”, anexando 86c82f5c-completo.xlsx (SHA-256 b252462dcff5fd279d071e81a18bbf9586e38efd6ba7e85a542759b8be5b5fe3).
- verificacao_automatica: passou na última execução registrada — Skip QA e fixture sintética 12/12 antes do relato de falha humana. Em 2026-10-02T08:46 o validador da T1.1 foi executado localmente contra o anexo: homologação bloqueada (ver changelog).
- aprendizado: pendente
- ultima_acao: Luís anexou a planilha da moenda (226 registros, aba única Base Montagem) e pediu verificação dos requisitos da T1.1 contra ela. O validador v1.0.0 foi executado localmente (sem persistir nada no Skip): no modo as-is bloqueia por cabeçalhos ausentes (Código, Status); no modo com o mapeamento decidido por Luís (Código Equipamento = Código, sem Status = componente), os 226 registros são bloqueados porque o validador trata toda TAG curta repetida como TAG composta de componente e exige a aba TAG Localização, que o arquivo não tem.
- proxima_acao: decidir com o consultor se o validador v1.0.0 precisa de emenda (regra de TAG curta repetida como localização + aba TAG Localização opcional quando a própria aba contém as localizações) ou se a planilha da moenda deve ganhar a aba TAG Localização; nenhuma alteração de código até essa decisão.
- atualizado_em: 2026-10-02T08:46:21-03:00
