# Emenda E-F1-01 — Recorte da conectividade da Fase 1: IoTebe como fonte aprovada

**Data:** 23/11/2026
**Aprovada por:** Kim (consultora)
**Afeta:** SPEC-1-002 (T2.2, T2.3 e nova T2.4), SPEC-1-005 (T5.2), `fase.md`
**Origem do sinal:** consultoria de 04/11/2026. Gustavo (PCM) relatou que a etapa 2 estava travada aguardando o TI
mapear as fontes e que a leitura do IoTebe já funcionava. A consultora se comprometeu a analisar como seguir sem
essa dependência.

## Por que

- A leitura real da moenda já está comprovada desde 03/11/2026 pela API em nuvem do IoTebe: 34 pontos de medição,
  1 amostra por minuto, 95,6–98,8% de cobertura em 24 h, 14 dos 15 ativos do K1, com os seis metadados do CA-1-004.
- O escopo definitivo (§8) só prevê pausa no fim da Fase 1 **"sem qualquer acesso viável aos dados da moenda"**. Esse
  acesso existe. O mesmo §8 diz que, **sem integração PIMS, vale a importação periódica com vínculo manual da OS, sem
  bloquear o painel de condição**.
- As 7 pendências de inventário (SPEC-1-002, itens 1–7) travavam T2.2, T2.3, T4.2, T4.3, T5.2, T5.3 e T6.3, embora a
  prova de dado real já exista.

## O que muda

1. **Fonte aprovada da Fase 1.** A API em nuvem do IoTebe, em modo somente leitura (protocolo somente-GET autorizado
   por Luís em 03–04/11/2026), passa a ser a fonte aprovada de sinais de condição da Fase 1.

2. **Demais fontes vão para o backlog.** SCADA Sonne, historiador, TOTVS PIMS MI em tempo real, IONICS, Solinftec e
   exportações automatizadas saem da Fase 1 com o estado **"não consultada — backlog de fontes"**. Elas **não são
   declaradas inexistentes** e **não bloqueiam** T2.2, T2.3 nem T5.2. Se o TI/OT responder sobre alguma delas, a
   resposta é registrada na SPEC-1-002 e avaliada como evolução na liberação da Fase 2.

3. **T2.2 recortada.** A prova de leitura real é feita com o IoTebe.
   - Dono: PCM/executor (Gustavo), com aprovação de Luís.
   - CA-1-004 e CA-1-021: provados com a amostra IoTebe.
   - CA-1-005, para a Fase 1: o caminho é gateway IoTebe → nuvem do fornecedor → leitura, sem rota para a rede OT
     (segmentação por desenho). A **aprovação de Luís como dono do risco** substitui o parecer formal de TI/OT. O
     parecer de TI/OT passa a ser recomendado e é anexado quando existir, mas não bloqueia.
   - **Continuam obrigatórias, com Luís:** a pendência 1 (expiração e rotação da credencial IoTebe) e a pendência 10
     (chave com permissão de escrita). Para a 10, Luís aceita o risco com os controles C1 (snapshot de configuração)
     e C2 (prova de zero escrita), ou pede ao fornecedor uma chave somente leitura. Sem essa decisão, o CA-1-005 não
     fecha.

4. **T2.3 com o recorte.** As classes cobertas pelo IoTebe são avaliadas normalmente. As classes sem sensor IoTebe
   ficam **"bloqueadas — fonte em backlog"**, com justificativa, sem inventar frequência. O parecer G2/G9 registra que
   o G2 foi satisfeito pelo contorno IoTebe para as classes cobertas.

5. **Nova T2.4 — OS e falhas por exportação CSV.** A fonte de OS, falhas e paradas da Fase 1 passa a ser a
   **exportação CSV do PIMS MI feita pelo PCM**, com frequência mínima semanal, em vez de integração.
   - Campos mínimos: número da OS, data de abertura, data de fechamento, equipamento/TAG, tipo/modalidade, houve
     parada (sim/não) e descrição.
   - Importação no cadastro de OS do app, preservando arquivo de origem (hash), aba e linha.
   - OS sem TAG do catálogo vira lacuna explícita. Nenhuma OS é criada automaticamente no PIMS (escopo §9 mantido).
   - O campo "houve parada" inicia a taxonomia de falha/parada (pendência 9). O K2 continua **inconclusivo** até
     existirem eventos elegíveis suficientes. Nada muda na regra de não declarar K2 atingido sem evidência.

6. **T5.2 no app.** A pré-condição passa a ser **T1.3, T2.2 (recorte IoTebe), T4.2 e T5.1 aceitas**. A evidência
   exigida inclui o **painel construído no app Skip "Controle de Equipamentos" (57219), visível no preview, com dados
   reais do IoTebe**, e não apenas pacote de prova.

## O que não muda

- Os critérios de aceite CA-1-004, CA-1-006, CA-1-013 a CA-1-016 e CA-1-021 continuam com o mesmo texto.
- Nenhuma escrita no IoTebe, SCADA, CLP ou PIMS. Nenhuma OS automática.
- K1/K2/K3, denominadores e janelas homologados na SPEC-1-003 ficam como estão.
- A T6.1 (workshop) e a T6.3 (decisão de saída) continuam com a consultora.

## Ordem sugerida a partir daqui

1. Luís: teste humano da T2.1 e da T5.1; decisão sobre a chave IoTebe (pendências 1 e 10).
2. Gustavo: T4.1 (perfilador de qualidade, sem dependência) e T2.4 (exportar o CSV de OS do PIMS MI).
3. T2.2 com o IoTebe → T4.2 → T5.2 no app → T5.3 e T2.3.
