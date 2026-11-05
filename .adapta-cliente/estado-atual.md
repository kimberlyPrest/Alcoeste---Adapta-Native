# Estado atual — Adapta Cliente

- task_id: T3.2
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-003.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: parcial — Luís enviou em 04/11/2026 os três arquivos de insumo da T3.2; aceite formal da entrega ainda pendente após a correção de 05/11.
- teste_humano: aprovado em 04/11/2026 (v1.0), mas a v1.1 CORRIGE um erro de cálculo — exige novo teste humano.
- verificacao_automatica: passou — 17/17 testes em pacote limpo reextraído do zip; 87 registros; 61 intervalos; medianas FACAS 484.002 t e MARTELOS 560.857 t; correção de ano em 21 registros; teste humano HTML verificado no navegador (16/16).
- aprendizado: pendente
- ultima_acao: T3.2 CORRIGIDA (v1.1). Luís perguntou como cheguei em "facas 100.838 t e martelos 217.580 t" e a pergunta expôs um ERRO DE SEMÂNTICA: eu calculei a DIFERENÇA entre trocas consecutivas na aba FACAS-MARTELOS, mas nessa aba a coluna do ano JÁ É o incremento do ciclo. Prova: a coluna "MOAGEM TOTAL" é a soma dos valores (2.150.190 em 2025), não o último (683.083); se fosse acumulada, o total seria o último. Correção aplicada: intervalos por aba (PENTES acumulado → diferença; FACAS/MARTELOS/ROTORES incremento → o próprio valor). Números corretos: FACAS 8 ciclos / mediana 484.002 t; MARTELOS 10 ciclos / mediana 560.857 t; geral 61 intervalos / mediana 610.418 t. SEGUNDO achado: divergência entre arquivos — o arquivo de 2025 traz a coluna 2024 de MARTELOS com valores de FACAS (401.606,77 vs 908.799,61 no arquivo de 2024); aplicada a regra "cada arquivo é autoridade sobre a sua safra", porque a soma do arquivo de 2024 fecha com a moagem da safra (1.832.859,88 t); pendência declarada para o PCM. Artefato: artifacts/T3.2-baseline-intervencoes-v1.1.zip (sha256 81b1a475). Nada publicado no app Skip.
- proxima_acao: Aguardar novo teste humano de Luís no artefato T3.2-teste-humano-abra-este-arquivo.html (v1.1, 16/16) e a confirmação; ao chegar o arquivo de OS da moenda, retomar o K2 com denominador real.
- bloqueio_declarado: K2 permanece inconclusivo — os três Excel registram troca preventiva, não parada não programada; a base de OS do Skip contém apenas fixture e o arquivo de OS da moenda ainda está sendo aguardado.
- atualizado_em: 2026-11-05T12:10:00-03:00
