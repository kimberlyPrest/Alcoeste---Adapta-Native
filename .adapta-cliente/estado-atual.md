# Estado atual — Adapta Cliente

- task_id: T2.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-002.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: confirmada em 2026-11-04T09:46-03:00 — trecho da mensagem: "Autorizo a T2.1 com esses controles." (resposta ao relatório de análise e à explicação dos riscos do código sem PUT e do caminho de acesso às bases).
- teste_humano: pendente
- verificacao_automatica: passou — 17/17 testes do validador do gate G2 (TDD com RED registrado); gate rodando sobre o inventário real: BLOQUEADO com 8 bloqueios (7 fontes não inventariadas + credencial IoTebe sem expiração), que é o comportamento correto; prova de zero escrita: 3 arquivos / 406 linhas varridas, nenhuma chamada de escrita — e a prova foi testada contra um coletor falso com PUT, reprovando-o (não é decorativa); snapshot de configuração: 34 spots comparados, nenhuma deriva; pacote limpo reextraído do zip: 17/17.
- aprendizado: pendente
- ultima_acao: T2.1 implementada (autorizada por "Autorizo a T2.1 com esses controles" em 04/11/2026). Entregues: inventario.js (9 fontes com lacuna declarada), validarGate.js (validador puro do gate G2, 6 cenários de erro da SPEC), validarGate.test.js (17 testes), protocolo-prova-acesso.md (regras, 4 controles compensatórios, arquitetura de rede, governança da credencial), inventario-fontes.md (documento para o Peterson preencher), snapshot-config.mjs (controle C1), prova-zero-put.mjs (controle C2), prova-gate-real.mjs e teste-humano-t21.html verificado no navegador (17/17, 9 fontes, 8 bloqueios). Artefato: artifacts/T2.1-inventario-fontes-v1.0.zip (sha256 7acdc033). Achados: API IoTebe devolve HTTP 429 em varredura de 34 spots em sequência (exige throttle/retry no protocolo); o PUT /spot/{id} altera 6 campos de configuração e GET /spot/{id} devolve exatamente esses campos, viabilizando detecção por snapshot; base de OS do Skip está vazia (só fixture), portanto K2 não é mensurável hoje. Nada publicado no app Skip.
- proxima_acao: Aguardar teste humano de Luís no artefato T2.1-teste-humano-abra-este-arquivo.html e a confirmação explícita de que funcionou antes de concluir a T2.1.
- atualizado_em: 2026-11-04T09:55:00-03:00
