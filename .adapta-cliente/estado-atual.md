# Estado atual — Adapta Cliente

- task_id: T3.2
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-003.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: parcial — Luís enviou em 04/11/2026 os três arquivos de insumo da T3.2.
- teste_humano: APROVADO em 05/11/2026 ("Agora está certo") sobre a v1.2 — a v1.0 estava errada por erro de semântica e a v1.1 corrigiu.
- verificacao_automatica: passou — 21/21 testes em pacote limpo reextraído do zip v1.2 (f54472de); 87 registros, 61 intervalos; medianas FACAS 484.002 t e MARTELOS 560.857 t; teste humano HTML verificado no navegador (19/19).
- aprendizado: registrado — AP-2026-11-05 (semântica de coluna em planilha de terceiro). Detalhe em 06_notas.
- ultima_acao: T3.2 FECHADA (v1.2). Luís confirmou o teste e confirmou em seguida o valor do 2º ciclo de martelos de 2024 — **908.799,61 t** — encerrando a única divergência entre arquivos. Incorporado como fato decidido pelo cliente: o valor do arquivo de 2024 prevalece e a coluna de 2024 em MARTELOS do arquivo de 2025 é erro de preenchimento (traz valores de FACAS). A verificação cruzada virou código (`verificar-divergencias.mjs`) com teste que falha se a divergência sumir ou se o valor errado voltar ao baseline. Artefato: artifacts/T3.2-baseline-intervencoes-v1.2.zip (sha256 f54472de); teste humano: artifacts/T3.2-teste-humano-abra-este-arquivo.html (19/19). Nada publicado no app Skip.
- proxima_acao: Registrar a conclusão da T3.2 na SPEC-1-003 (CA-1-008 ✅, checklist) e no fase.md, e liberar a T3.3 (homologação da Kim, CA-1-009) como próxima da trilha. Recomendado também iniciar T5.1 (contrato do painel), que não depende de insumo externo.
- bloqueio_declarado: K2 permanece inconclusivo — os três Excel registram troca preventiva, não parada não programada; a base de OS do Skip contém apenas fixture e o arquivo de OS da moenda ainda está sendo aguardado.
- atualizado_em: 2026-11-05T12:45:00-03:00
