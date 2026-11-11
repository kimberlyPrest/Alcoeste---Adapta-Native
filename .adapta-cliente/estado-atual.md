# Estado atual — Adapta Cliente

- task_id: T5.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-005.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: confirmada — Luís autorizou em 10/11/2026 ("Vamos iniciar a T5.1" + decisões sobre estados, perfis e amostra).
- teste_humano: pendente — Luís abrir `artifacts/T5.1-teste-humano-abra-este-arquivo.html` (38/38).
- verificacao_automatica: passou — 38/38 testes em pacote limpo reextraído do zip v1.0 (545ac2bc); HTML 38/38 verificado no navegador; 3 mutações aplicadas para provar que a suíte reprova; verificação com o catálogo real: 178 nao_se_aplica + 48 sem_dados, zero completo (não fabrica leitura sem amostra).
- aprendizado: registrado — a ordem de precedência precisou de teste próprio; mutação não era pega.
- ultima_acao: T5.1 IMPLEMENTADA (v1.0, zip 545ac2bc). **Decisões do cliente aplicadas:** (1) os 5 estados no formato proposto, com precedência conflitante(50) > atrasado(40) > sem_dados(30) > parcial(20) > completo(10); (2) 4 perfis — operacao_pcm, gestao, auditoria e **ti_ot próprio**, com **PCM exportando**; (3) amostra pode ser só de vibração, com a lacuna de processo declarada no painel. **Achado durante a implementação:** a classificação retornava cedo no estado atrasado e não calculava as variáveis ausentes — um ativo atrasado que também era parcial aparecia só como atrasado, e ao consertar o atraso "melhoraria" para parcial sem ninguém instalar sensor. Corrigido: ausentes calculadas sempre, com teste específico. **Achado no teste dos testes:** a mutação que trocava a precedência de `sem_dados` passava despercebida — o teste só verificava que `conflitante` era o maior. Adicionado teste que trava a ORDEM declarada; agora a mutação reprova. `nao_se_aplica` ficou como estado de EXIBIÇÃO, separado dos 5, para nunca ser lido como "está tudo bem". Contrato declara as lacunas: sem série de processo, ET09 sem sensor, e "conflitante" sem uso até o PIMS entrar.
- proxima_acao: Luís abrir o HTML e confirmar; depois seguir para T5.2 (painel visual, depende de amostra) ou T5.3 (segurança server-side).
- bloqueio_declarado: nenhum bloqueio técnico. A T5.2 depende de amostra aprovada (T2.2, com o Peterson) — mas o contrato já está pronto e não depende dele.
- atualizado_em: 2026-11-11T08:55:00-03:00
