# Estado atual — Adapta Cliente

- task_id: T3.2
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-003.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: parcial — Luís enviou em 04/11/2026 os três arquivos de insumo que faltavam à T3.2 ("Segue em anexo os arquivos excel de 2024, 2025 e 2026"), o que autoriza o trabalho sobre o dado; a entrega ainda não foi apresentada para aceite formal desta task.
- teste_humano: pendente
- verificacao_automatica: passou — 15/15 testes de borda (baseline.test.js) em pacote limpo reextraído do zip; dataset consolidado com 85 registros e zero duplicata; correção de ano verificada (21 registros do arquivo 2024 datados em 2024); 47 intervalos válidos de vida útil, todos positivos; teste humano HTML verificado no navegador antes da entrega (15/15, mediana 540.541 t, 14 componentes).
- aprendizado: pendente
- ultima_acao: T3.2 executada com os três Excel "KPIs Moenda e Caldeira" (2024/2025/2026) enviados por Luís. Consolidados 85 registros de intervenção preventiva (62 pentes, 16 facas/martelos, 7 rotores), zero duplicata entre arquivos. Correção de dado aplicada: as datas do arquivo rotulado 2024 estavam gravadas com ano 2025 e foram reescritas para 2024 conforme informado pelo cliente em 04/11/2026 — planilha original preservada, correção viva na extração e declarada no dataset. Calculados 47 intervalos de moagem entre trocas (mediana geral 540.541 t): pente superior do 2º Terno é o componente de maior desgaste (10 intervalos, mediana 305.006 t); facas do picador ~100.838 t/jogo; martelos do desfibrador ~217.580 t. Limitações declaradas no relatório: 2024 tem 14 registros de pente contra 28 em 2026 (registro incompleto, não queda de frequência); facas sem lançamento em 2026; rotores com 1–2 registros por lado (amostra insuficiente). Artefato: artifacts/T3.2-baseline-intervencoes-v1.0.zip (sha256 df81a584). Nada publicado no app Skip.
- proxima_acao: Aguardar teste humano de Luís no artefato T3.2-teste-humano-abra-este-arquivo.html e a confirmação de que funcionou; ao chegar o arquivo de OS da moenda (informado como ainda pendente em 04/11/2026), retomar o K2 com denominador real.
- bloqueio_declarado: K2 permanece inconclusivo — os três Excel registram troca preventiva, não parada não programada; a base de OS do Skip contém apenas fixture e o arquivo de OS da moenda ainda está sendo aguardado. Não é falha do programa: é lacuna de insumo declarada, com plano de coleta no relatório.
- atualizado_em: 2026-11-04T14:30:00-03:00
