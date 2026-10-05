# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: em_correcao
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”; decisões de mapeamento dadas em 2026-10-01 — “Código como chave única”, “Importar como componentes”, “Ignorar coluna APAGAR”.
- teste_humano: falhou em 2026-10-02T08:37:00-03:00 — Luís: “Encontrei uma falha no teste”. Em 2026-10-02T08:44 Luís instruiu ignorar o erro anterior e validar a planilha da moenda anexada. Em 2026-10-05T15:53 Luís reformatou a planilha (fd7fda49-completo.xlsx, SHA-256 e976c341…) e pediu nova verificação e lista de tasks pendentes.
- verificacao_automatica: passou na última execução registrada — Skip QA e fixture sintética 12/12 antes do relato de falha humana. Em 2026-10-05T15:56 o validador v1.0.0 foi executado localmente contra a planilha reformatada em dois formatos: nativo (bloqueio por cabeçalhos ausentes) e canônico (Código Equipamento→Código, aba TAG Localização gerada das 8 TAGs curtas) — homologação segue bloqueada por regras do validador incompatíveis com o modelo de dados da moenda (TAG curta repetida como localização; ativos sem Código Equipamento com sensores; sem coluna Classe), ver changelog.
- aprendizado: pendente
- ultima_acao: Luís reformatou a planilha da moenda e pediu verificação das pendências e lista de tasks pendentes. Dados do arquivo reformatado estão limpos (zero TAG composta duplicada, zero componente órfão, zero sem descrição, zero sem Código do MIS, criticidade 100%); o bloqueio remanescente é do validador v1.0.0, cujo contrato pressupõe o layout da planilha antiga da planta.
- proxima_acao: decisão de Kim/consultoria entre emendar o validador para v1.1.0 (modelo da moenda: TAG curta repetida = localização; aba TAG Localização opcional; Código Equipamento como chave; classe derivada da família ou coluna Classe a incluir) ou manter v1.0.0 e reformatar a planilha para o layout canônico; enquanto isso, resolver MEL0579 duplicado (linhas 138/147) com o PCM.
- atualizado_em: 2026-10-05T15:56:14-03:00
