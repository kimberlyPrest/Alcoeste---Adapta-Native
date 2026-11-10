# Estado atual — Adapta Cliente

- task_id: T2.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-002.md
- etapa: concluida
- autorizacao_implementacao: confirmada — Luís autorizou em 04/11/2026; protocolo somente-GET vigente.
- teste_humano: APROVADO em 10/11/2026 — teste executado pelo assistente a pedido de Luís: 17/17 no navegador, gate G2 BLOQUEADO em 8 pendências (comportamento correto), matriz de 9 fontes exibida.
- verificacao_automatica: passou — 26/26 testes em pacote limpo reextraído do zip v1.1 (17 do validador do gate + 9 da própria prova de zero escrita); prova zero-PUT varre o coletor real (334 linhas) e reprova coletor falso com PUT; varredura vazia devolve INCONCLUSIVO com código de saída 1; gate real bloqueado em 8; snapshot dos 34 spots sem deriva.
- aprendizado: registrado — a prova de zero escrita tinha defeito que a anulava (caminho absoluto + aprovação por vacuidade). AP registrado em 06_notas.
- ultima_acao: T2.1 verificada e CORRIGIDA em 10/11/2026 (v1.1, zip 9130db8e). O teste do pacote passou em tudo, mas ao testar a PRÓPRIA prova de zero escrita descobri um defeito grave: `prova-zero-put.mjs` varria caminhos ABSOLUTOS do meu workspace (`/home/ethos/.assistant/workspace/scripts/iotebe-*`), ignorava qualquer argumento e, com zero arquivos varridos, imprimia "PASSOU". Numa outra máquina ela aprovaria sem olhar nada — é o pior tipo de defeito, porque dá aparência de controle. Além disso, o alvo não era o coletor da prova: pegava também o `alarm_poll.py` da Sentinela, e a versão anterior varria 406 linhas contra as 334 do coletor real. Corrigido: alvos relativos ao pacote, aceita diretório por argumento, e varredura vazia retorna INCONCLUSIVO com exit 1. Criado `prova-zero-put.test.js` (9 testes) que prova: coletor com GET passa, com PUT reprova, com `data=` reprova, fetch com POST reprova, diretório vazio NÃO aprova, alvo inexistente NÃO aprova, comentário documentando PUT não conta, coletor real passa e é varrido de fato, e a prova não depende de caminho absoluto. O coletor real (`run.py`) foi copiado para `coletor/` dentro do pacote.
- proxima_acao: Encaminhar T2.1 v1.1 ao Peterson (inventário-fontes.md para as 7 fontes pendentes) e considerar a T2.1 encerrada. Próxima task recomendada: T5.1 (contrato do painel — não depende de insumo externo).
- bloqueio_declarado: T2.2 depende do inventário preenchido pelo Peterson e da credencial IoTebe com expiração definida. K2 continua sem fonte de eventos (base de OS da moenda não importada). Gate G2 bloqueado em 8 pendências.
- atualizado_em: 2026-11-10T09:58:00-03:00
