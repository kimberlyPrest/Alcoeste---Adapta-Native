# Estado atual — Adapta Cliente

- task_id: T5.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-005.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: confirmada — Luís autorizou em 10/11/2026 e corrigiu os perfis em 11/11/2026.
- teste_humano: pendente — Luís abrir `artifacts/T5.1-teste-humano-abra-este-arquivo.html` (42/42).
- verificacao_automatica: passou — 42/42 testes em pacote limpo reextraído do zip v1.1 (da1fd196); HTML 42/42 no navegador; 4 mutações aplicadas para provar que a suíte reprova; catálogo real: 178 nao_se_aplica + 48 sem_dados, zero completo.
- aprendizado: registrado — a ordem de precedência precisou de teste próprio; e a matriz perfil×ação precisa de teste que compare contrato e matriz.
- ultima_acao: T5.1 CORRIGIDA (v1.1, zip da1fd196). **Correção do cliente em 11/11/2026:** eu havia juntado Operação e PCM num perfil só (`operacao_pcm`). O cliente separou — **Operação NÃO exporta** (consulta e filtra) e **PCM exporta**. Aplicado: 5 perfis (`operacao`, `pcm`, `gestao`, `auditoria`, `ti_ot`), com 5 testes novos travando a separação, incluindo um que compara a lista `exportacao.exigePerfil` do contrato com a matriz — para as duas não divergirem no futuro. Mutação confirmada: devolver `exportar` à Operação reprova em 3 testes. Estado anterior mantido: os 5 estados com precedência conflitante(50) > atrasado(40) > sem_dados(30) > parcial(20) > completo(10); TI/OT com perfil próprio; `nao_se_aplica` como estado de exibição separado.
- proxima_acao: Luís abrir o HTML e confirmar; depois seguir para T5.3 (segurança server-side, sem dependência de amostra).
- bloqueio_declarado: nenhum bloqueio técnico. A T5.2 (painel visual) depende de amostra aprovada (T2.2, com o Peterson).
- atualizado_em: 2026-11-11T09:10:00-03:00
