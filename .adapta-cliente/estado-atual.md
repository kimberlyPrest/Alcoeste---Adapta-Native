# Estado atual — Adapta Cliente

- task_id: T2.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-002.md
- etapa: concluida
- autorizacao_implementacao: confirmada — Luís autorizou em 04/11/2026; protocolo somente-GET vigente.
- teste_humano: APROVADO em 10/11/2026 — teste executado pelo assistente a pedido de Luís: 17/17 no navegador, gate G2 BLOQUEADO (comportamento correto).
- verificacao_automatica: passou — 26/26 testes em pacote limpo reextraído do zip v1.2 (17 do validador do gate + 9 da própria prova de zero escrita); zero-PUT varre o coletor real e reprova coletor com PUT; varredura vazia devolve INCONCLUSIVO (exit 1); gate real com 7 bloqueios; 3 de 9 fontes com estado definido.
- aprendizado: registrado — a prova de zero escrita tinha defeito que a anulava (caminho absoluto + aprovação por vacuidade).
- ultima_acao: T2.1 v1.2 (zip 94933902). **Análise do alcance dos PUT do IoTebe** conferida contra o OpenAPI v2.0.1 do próprio fornecedor, após resposta do suporte técnico: (a) **injeção de dado (PUT /virtual) NÃO alcança o piloto** — só escreve em spot INTEGRADO, e os 34 spots do piloto são `type=NG1VT` com `sensor_id`; o risco que eu havia registrado era maior do que o real. (b) **Mas o PUT /spot/{id} alcança**, e altera 6 campos que incluem `machine_type`, `rotation_speed`, `variable_rotation_speed`, `power` e `bearing_type` — não é "mudar nome de ponto": são parâmetros que a plataforma usa para interpretar a medição e calcular limite de alarme. O risco que permanece é deslocamento de parâmetro de cadastro, não falsificação de série. Registrado em `alcanceDosPut` no inventário. **Fonte da base de OS definida por Luís:** sai do **PIMS MI**, e o **Peterson** libera o acesso — isso resolve "de onde vem" e "quem entrega"; falta a execução. **Excel de KPIs corrigido:** não é fonte de eventos (papel `historico_de_trocas`); foi entregue na T3.2 com 87 registros, mas sem classificação de falha — alimenta vida útil, não K2. Com isso o gate caiu de 8 para **7 bloqueios** (o Excel contava duas vezes por falta de campos explícitos).
- proxima_acao: Encaminhar ao Peterson: `inventario-fontes.md` v1.1 (6 fontes pendentes, com PIMS MI marcado como PRIORIDADE por fornecer a base de OS) e o pedido de expiração da credencial IoTebe. Depois disso, T2.2.
- bloqueio_declarado: T2.2 depende das 6 fontes do Peterson e da expiração da credencial. K2 segue sem fonte de eventos — a base de OS vem do PIMS MI (acesso com Peterson) e a taxonomia de falha não tem fonte declarada.
- atualizado_em: 2026-11-10T10:15:00-03:00
