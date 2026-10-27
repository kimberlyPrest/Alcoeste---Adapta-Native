# Estado atual — Adapta Cliente

- task_id: T3.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-003.md
- etapa: aguardando_autorizacao
- autorizacao_implementacao: ausente — análise da T3.1 entregue em 2026-10-23; parâmetros dos KPIs fechados pelo Diretor-Presidente em 2026-10-27; aguardando "pode implementar" em mensagem nova.
- teste_humano: pendente
- verificacao_automatica: pendente
- aprendizado: pendente
- ultima_acao: Parâmetros de K1/K2/K3 fechados pelo Diretor-Presidente em 27/10/2026. Briefing operacional v1.0 emitido e aprovado (insumo que faltava ao handoff). Decisões: (1) denominador K1 = criticidade A (21) menos hilos HI01/HI02, pontes PR01/PR02/PR03 e PI02 inativo = 15 ativos; (2) ternos TM01–TM05 permanecem no denominador com cobertura contada pelos acionamentos AC01–AC03; (3) PI02 excluído enquanto inativo, com reentrada automática ao sair do estado; (4) ET09 permanece no denominador como lacuna real declarada (único ativo em operação sem sensor no escopo); (5) janela de antecipação do K2 = 7 dias; (6) janela dos três KPIs = mensal (micro) + safra mar–dez (macro). Baseline K1 calculado sobre o catálogo congelado: 14 cobertos ÷ 15 = 93,3% (9 com sensor direto + 5 ternos via acionamento).
- proxima_acao: Aguardar autorização explícita de Luís para implementar o contrato de medição K1–K3 v1.0.0 (kpiContract.js + calculateKpis.js puro com TDD GREEN e caminhos de erro de CA-1-008), usando os parâmetros do briefing v1.0.
- pendencias_externas: taxonomia formal de falha/parada (Excel "KPIs Moenda e Caldeira 2024" não anexado ao handoff); donos nomeados por nome nos papéis PCM/Manutenção/Engenharia de Dados; homologação formal do PCM sobre o denominador. Nenhuma bloqueia a implementação do contrato, pois os parâmetros são dados versionados, não código.
- atualizado_em: 2026-10-27T12:20:00-03:00
