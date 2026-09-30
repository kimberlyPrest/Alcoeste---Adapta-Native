# Escopo Definitivo — Alcoeste Bioenergia

## 1. Direção aprovada
Construir e validar um **piloto de monitoramento preditivo dos equipamentos críticos da moenda**, capaz de transformar sinais operacionais em alertas antecipados, hipóteses diagnósticas e recomendações acionáveis para avaliação da equipe de manutenção.

O produto será uma camada de inteligência sobre as fontes existentes. Não substituirá o SCADA, o PIMS, os sensores ou os procedimentos técnicos da Alcoeste.

## 2. Recorte do piloto
O universo do projeto será o conjunto homologado de equipamentos críticos da moenda, mencionado no kick-off como aproximadamente 80 equipamentos. O número final, os componentes, sensores obrigatórios e classes de criticidade serão congelados na Fase 1. Toda exclusão em relação ao universo inicial deverá ter justificativa técnica, aprovação do cliente e aparecer no painel de K1; o catálogo não poderá ser reduzido apenas para facilitar o atingimento da meta.

A expansão para toda a indústria ou para a frota automotiva é evolução futura e dependerá do resultado do piloto.

## 3. Resultado contratado do ciclo
Ao final das cinco fases, a Alcoeste deverá possuir um piloto operacional e medido que:
- mostre quais ativos críticos estão efetivamente cobertos por dados confiáveis;
- identifique desvios e tendências antes da falha quando os sinais permitirem;
- produza alertas explicáveis, priorizados e rastreáveis;
- apresente hipótese diagnóstica e recomendação com confiança explícita;
- preserve decisão humana sobre inspeção, manutenção e parada;
- registre o desfecho para medir utilidade, antecedência e erros;
- permita decidir, por evidência, se o piloto deve ser expandido.

## 4. Componentes do produto
1. **Catálogo de ativos críticos:** equipamento, componente, tag, sensor, variável, unidade, criticidade, responsável e vínculos entre sistemas.
2. **Camada de ingestão:** integração, exportação ou carga controlada de dados, com origem e timestamp preservados.
3. **Qualidade e cobertura:** monitoramento de lacunas, atraso, duplicidade, unidade e disponibilidade do sinal.
4. **Painel de condição:** estado e tendência por ativo, componente e variável.
5. **Motor de detecção:** regras homologadas e, onde houver dados suficientes, modelos analíticos versionados.
6. **Central de alertas:** consolidação, criticidade, reconhecimento, tratamento, justificativa e escalonamento.
7. **Diagnóstico assistido:** causa provável, sinais relacionados, evidências e confiança.
8. **Recomendação assistida:** ação e janela sugeridas, submetidas a validação humana.
9. **Feedback operacional:** decisão, inspeção, intervenção, OS, falha confirmada e resultado.
10. **Painel de indicadores:** K1–K3 e indicadores de guarda.
11. **Administração e auditoria:** perfis, parâmetros, versões e histórico de mudanças.

## 5. Regras de negócio
- **RN-01:** somente ativos do catálogo homologado entram no denominador de cobertura.
- **RN-02:** ausência ou atraso de dados é “cobertura indisponível”, não “ativo normal”.
- **RN-03:** toda leitura deve manter origem, ativo, variável, unidade e timestamp.
- **RN-04:** limites fixos devem ter responsável técnico, vigência e versão.
- **RN-05:** detecção analítica deve registrar dados, janela, versão e confiança.
- **RN-06:** eventos correlatos devem ser agrupados para conter tempestade de alertas.
- **RN-07:** alerta crítico precisa informar ativo, evidência, criticidade e condição observada.
- **RN-08:** diagnóstico será tratado como hipótese até confirmação em inspeção/intervenção.
- **RN-09:** recomendação não é ordem automática; requer decisão humana registrada.
- **RN-10:** recomendação de parada nunca aciona equipamento automaticamente.
- **RN-11:** falso positivo, alerta útil, falha confirmada e evento sem antecipação devem ser registráveis.
- **RN-12:** alteração de criticidade, regra ou modelo deve ser auditável e reversível.
- **RN-13:** o piloto começa em modo sombra; comunicação operacional é liberada somente após gate G8.
- **RN-14:** integração com PIMS no piloto pode ser leitura ou vínculo de referência; escrita/abertura automática de OS fica excluída.
- **RN-15:** quando não houver histórico suficiente, o sistema opera por regras homologadas e coleta evidências, sem prometer predição baseada em IA.
- **RN-16:** o cliente verá explicitamente quais resultados vêm de regras homologadas e quais vêm de modelo analítico/IA; nenhuma regra fixa será apresentada como predição por IA.
- **RN-17:** mudanças de fórmula, janela ou tolerância dos KPIs não alteram silenciosamente as metas 90/80/80; qualquer mudança que afete comparabilidade exige aprovação explícita do cliente.

## 6. Critérios de sucesso e validação
- **K1 — 90% de cobertura contínua:** fórmula e tolerância fechadas na Fase 1; acompanhada desde a Fase 2.
- **K2 — 80% das anomalias relevantes antecipadas:** medido apenas sobre eventos elegíveis, com fonte de verdade e janela aprovadas; validado nas Fases 4 e 5. Se a amostra ou o baseline permanecerem insuficientes, K2 será declarado inconclusivo — nunca tratado como atingido — e a decisão de expansão dependerá de aprovação explícita baseada em K1, K3, indicadores de guarda, limitações e plano com dono/prazo para formar baseline.
- **K3 — 80% dos alertas críticos com diagnóstico e recomendação:** medido em alertas críticos válidos; validado nas Fases 4 e 5.

As metas do briefing serão preservadas, mas não serão declaradas atingidas sem denominador, baseline, janela e evidência aprovados.

## 7. Dependências
- Disponibilidade de responsáveis técnicos e operacionais, com capacidade mínima em horas por semana acordada na Fase 1.
- Calendário do piloto compatível com a safra, a entressafra e as janelas de operação/manutenção.
- Catálogo de ativos, tags e criticidade.
- Acesso a dados do SCADA Sonne ou exportação equivalente.
- Histórico de vibração, temperatura, torque e estado operacional quando disponível.
- Registro de falhas/paradas/intervenções e OS no PIMS, no Excel “KPIs Moenda e Caldeira 2024” quando aplicável, ou em outra fonte homologada.
- Homologação de limites, regras, segurança e escalonamento.

## 8. Contornos para bloqueadores
- **Sem API do SCADA:** carga automatizada por arquivo ou exportação controlada somente se a frequência sustentar a janela útil da classe; exportação retrospectiva não será chamada de monitoramento contínuo ou preditivo.
- **Sem qualquer acesso viável aos dados da moenda:** pausa ao final da Fase 1 e decisão humana de reescopo ou encerramento; Fases 2–5 não avançam.
- **Sem integração PIMS:** importação periódica e vínculo manual da OS, sem bloquear painel de condição.
- **Sem histórico suficiente:** regras determinísticas + modo sombra + formação de base; modelo por classe fica condicionado.
- **Sem sensor obrigatório:** ativo aparece como não coberto e não entra artificialmente como saudável.
- **Sem baseline de falhas:** K2 permanece “não mensurável”; coletar baseline sem inventar percentual.

## 9. Excluído do projeto
- Financeiro, governança corporativa, qualidade laboratorial e recuperação industrial fora da moenda.
- Expansão para todos os equipamentos industriais ou frota agrícola.
- Compra, instalação, substituição ou calibração de sensores.
- Substituição dos sistemas industriais existentes.
- Controle automático, desligamento, atuação em CLP ou OS automática.
- Manutenção prescritiva sem validação do especialista.
- Promessa de eliminar paradas, atingir ganho de 40 mil toneladas ou garantir ROI antes da medição.

## 10. Sequência das cinco fases
1. **Fundação do piloto, catálogo, conectividade e baseline.**
2. **Ingestão contínua, qualidade e painel de condição.**
3. **Detecção de anomalias e alertas em modo sombra.**
4. **Diagnóstico e recomendação assistidos com validação técnica.**
5. **Operação controlada, medição dos KPIs e decisão de expansão.**

## 11. Gates antes da execução detalhada
O escopo pode ser aprovado documentalmente, mas a execução preditiva depende de G1–G8 descritos no PRD. SPECs e tasks da Fase 1 somente serão geradas após aprovação da Kim e do cliente. As fases seguintes serão detalhadas em onda, conforme evidências do piloto.
