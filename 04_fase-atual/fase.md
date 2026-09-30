# Fase 1 — Fundação do piloto, catálogo, conectividade e baseline

## Objetivo
Transformar o objetivo amplo em um piloto tecnicamente demonstrável: ativos congelados, fontes comprovadas, métricas definidas e primeira visão real de cobertura/condição.

## Resultado visível
Um **Painel de Prontidão e Condição Inicial da Moenda** com o catálogo homologado, cobertura real por ativo/sensor, amostra de tendências e lacunas de dados. A entrega gera valor mesmo se a integração definitiva ou os modelos ainda não estiverem disponíveis.

## Inclui
- Workshop com operação, manutenção, PCM, automação/TI e segurança.
- Catálogo dos equipamentos críticos, componentes, tags, sensores, variáveis e unidades.
- Matriz de criticidade e sensores obrigatórios por classe; toda exclusão do universo inicial precisa de justificativa e aprovação.
- Mapeamento SCADA → ativo físico → PIMS/OS, com percentual máximo de lacunas aceito e tratamento por ativo.
- Prova de acesso a dados: API, banco, historiador, exportação ou arquivo.
- Amostra histórica e perfil de frequência, continuidade, atraso e qualidade.
- Fonte de verdade para falhas, paradas, intervenções e OS.
- Definições operacionais de K1, K2 e K3, com denominadores e janelas.
- Baseline inicial de cobertura e inventário de eventos elegíveis, consultando também o Excel “KPIs Moenda e Caldeira 2024”.
- Dimensionamento das séries temporais: frequência, volume, retenção, granularidade, downsampling, reprocessamento e custo.
- Inventário de historiadores e plataformas existentes, incluindo validação do papel de IONICS e Solinftec para evitar duplicação.
- Protótipo funcional do painel de prontidão e condição inicial.
- Política preliminar de alerta, escalonamento e decisão humana.
- Arquitetura de segurança OT somente leitura aprovada por TI/OT.
- Calendário safra/entressafra e compromisso mínimo dos especialistas, com responsáveis e horas por semana.
- Thresholds preliminares para saída do modo sombra: exposição, cobertura, ruído, falsos positivos e regra para ausência de falhas elegíveis.

## Fora desta fase
Modelo preditivo em produção, diagnóstico automático, recomendação operacional ou escrita no PIMS.

## Checklist
- [ ] Responsáveis e RACI do piloto definidos.
- [ ] Catálogo e criticidade homologados.
- [ ] Tags e sensores obrigatórios mapeados.
- [ ] Acesso a amostra real demonstrado.
- [ ] Fonte de falhas/paradas/OS homologada.
- [ ] K1–K3 definidos operacionalmente.
- [ ] Qualidade e lacunas documentadas.
- [ ] Painel inicial demonstrado com dados reais.
- [ ] Lista de bloqueadores e contornos aprovada.

## Critérios de aceite
- **CA-F1-01:** 100% dos ativos elegíveis do piloto possuem identificador, classe, criticidade, responsável e vínculo conhecido ou lacuna explícita com as fontes.
- **CA-F1-02:** ao menos uma amostra real de cada fonte aprovada é ingerida e exibida com ativo, variável, unidade, timestamp e origem.
- **CA-F1-03:** o painel diferencia claramente ativo coberto, parcialmente coberto, sem dados e dado atrasado.
- **CA-F1-04:** K1–K3 possuem fórmula, denominador, janela, fonte e responsável aprovados ou estão marcados como bloqueados, sem estimativa inventada.
- **CA-F1-05:** existe decisão documentada para G1–G10, com dono e evidência necessária.
- **CA-F1-06:** G1–G4 e G9 estão aprovados para liberar a Fase 2; os demais podem permanecer pendentes apenas com dono, prazo e marco de bloqueio explícitos.
- **CA-F1-07:** se G2 não for satisfeito por nenhum contorno seguro e útil, o projeto pausa e retorna à Kim e ao cliente, sem iniciar a Fase 2.

## Demonstração
Selecionar ativos reais e mostrar: cadastro, tags, última leitura, histórico disponível, estado da cobertura e vínculo com evento/OS quando existir.

## Gate de saída
Cliente e consultora aprovam catálogo, fontes, métricas, contornos e recorte de classes que seguirão para ingestão contínua.


## Tasks

### Leva A
| ID | Task | Dono | SPEC | Critério | Recorte da prova | Evidência esperada | Pré-condições | Status |
|---|---|---|---|---|---|---|---|---|
| T1.1 | Preparar e validar o esquema de importação do universo inicial de ativos | Produto/Dados | SPEC-1-001 | Fixture com ativo completo, sem sensor, tag duplicada e exclusão é importada sem perda de origem; pendências ficam bloqueadas | TDD RED — validação do catálogo | fixture, relatório RED e esquema versionado | Fontes candidatas disponibilizadas | ☐ |
| T2.1 | Inventariar fontes OT e desenhar protocolo seguro da prova de acesso | TI/OT | SPEC-1-002 | Inventário cobre SCADA, historiador, IONICS, Solinftec e exportações; protocolo proíbe teste de escrita em produção | Pré-condição + TDD RED | inventário, diagrama preliminar e protocolo autorizado | Responsável TI/OT designado | ☐ |
| T3.1 | Definir dicionário operacional e memória de cálculo de K1, K2 e K3 | PCM | SPEC-1-003 | CA-1-007 passa com termos, fórmulas, fontes, janelas, exclusões e donos | TDD GREEN — contrato dos KPIs | contrato de medição versionado | Briefing aprovado e responsáveis nomeados | ☐ |
| T4.1 | Implementar fixture e perfilador reproduzível de qualidade de séries | Engenharia de Dados | SPEC-1-004 | Fixture detecta gap, duplicidade, atraso, unidade alterada, vazio e timestamp inválido | TDD RED — caminhos de erro | fixture, configuração e relatório RED | Esquema da amostra definido | ☐ |
| T5.1 | Definir contrato do painel, estados, perfis e auditoria | Produto/Segurança | SPEC-1-005 | Mapa de telas e matriz perfil×ação cobrem estados completo, parcial, sem dados, atrasado e conflitante | Pré-condições + TDD RED | contrato de UI/API, matriz de perfis e cenários RED | SPECs revisadas e regras de cobertura definidas | ☐ |
| T6.1 | Conduzir workshop e registrar RACI, safra, capacidade e critérios dos gates | Consultora | SPEC-1-006 | CA-1-017 e CA-1-020 possuem donos, RACI, horas/semana, calendário e critérios registrados ou bloqueio explícito | Checklist + CA-1-017/020 | ata, RACI, calendário e ledger inicial | Participantes de PCM, operação, manutenção e TI/OT confirmados | ☐ |

### Leva B
| ID | Task | Dono | SPEC | Critério | Recorte da prova | Evidência esperada | Pré-condições | Status |
|---|---|---|---|---|---|---|---|---|
| T1.2 | Consolidar ativos, componentes, tags, sensores e criticidade com lacunas explícitas | PCM/Manutenção | SPEC-1-001 | CA-1-001 e CA-1-002 passam para 100% dos candidatos | TDD GREEN — catálogo e estados de cobertura | export completo e relatório de lacunas | T1.1 aceita e responsáveis nomeados | ☐ |
| T2.2 | Executar prova de leitura somente leitura com dados reais da moenda | Automação/TI-OT | SPEC-1-002 | CA-1-004, CA-1-005 e CA-1-021 passam, incluindo segmentação e ciclo de vida da credencial | TDD GREEN — amostra real e arquitetura OT | amostra sanitizada, logs, diagrama e parecer TI/OT | T2.1 aceita; janela e autorização OT aprovadas | ☐ |
| T6.2 | Aprovar protocolo de incidente e integridade das aprovações | Responsável TI/OT | SPEC-1-006 | CA-1-023 e CA-1-024 passam em cenários de credencial, acesso, exportação e aprovação sem identidade/hash | TDD RED/REGRESSÃO — incidente e autoria | runbook, simulação de mesa, registros assinados/hash | T2.1 e T6.1 aceitas | ☐ |

### Leva C
| ID | Task | Dono | SPEC | Critério | Recorte da prova | Evidência esperada | Pré-condições | Status |
|---|---|---|---|---|---|---|---|---|
| T1.3 | Homologar e congelar a versão do catálogo e suas exclusões | Gestão Industrial | SPEC-1-001 | CA-1-003 passa e alteração posterior preserva versão anterior | TDD REGRESSÃO — versionamento e exclusões | termo de homologação, versão/hash e diff | T1.2 aceita | ☐ |
| T2.3 | Classificar viabilidade e frequência por classe e emitir parecer técnico G2/G9 | PCM | SPEC-1-002 | CA-1-006 passa; cada classe fica útil ou bloqueada com justificativa; ausência total gera parecer G2-A | Cenário limite/falha + regressão segura | matriz classe×fonte×frequência e parecer técnico | T2.2 concluída ou impossibilidade documentada | ☐ |
| T4.2 | Perfilar amostra real e dimensionar armazenamento da Fase 2 | Engenharia de Dados | SPEC-1-004 | CA-1-010 e CA-1-011 passam com métricas e estimativas reproduzíveis | TDD GREEN — perfil e dimensionamento | relatório versionado e memória de custo/retenção | T2.2 aceita e T4.1 aceita | ☐ |

### Leva D
| ID | Task | Dono | SPEC | Critério | Recorte da prova | Evidência esperada | Pré-condições | Status |
|---|---|---|---|---|---|---|---|---|
| T3.2 | Montar dataset rastreável e calcular o baseline inicial | Engenharia de Dados | SPEC-1-003 | CA-1-008 passa; ausência de dado/evento resulta bloqueado ou inconclusivo, nunca sucesso | TDD RED/GREEN — bordas e baseline | dataset, memória de cálculo e relatório de lacunas | T1.3, T3.1 aceitas e fontes PIMS/Excel disponibilizadas | ☐ |
| T4.3 | Emitir parecer de aptidão preditiva por classe | Especialista de Manutenção | SPEC-1-004 | CA-1-012 passa e nenhuma classe insuficiente é marcada apta | TDD REGRESSÃO — decisão por classe | matriz de aptidão com fonte, aprovador e limitações | T3.1 e T4.2 aceitas | ☐ |
| T5.2 | Construir painel de prontidão e condição inicial com amostra aprovada | Desenvolvimento | SPEC-1-005 | CA-1-013, CA-1-014 e CA-1-015 passam em testes UI/API | TDD GREEN — resumo, filtros, detalhe e estados negativos | suíte executada, capturas e build demonstrável | T1.3, T2.2 ou parecer G2-A, T4.2 e T5.1 aceitas | ☐ |

### Leva E
| ID | Task | Dono | SPEC | Critério | Recorte da prova | Evidência esperada | Pré-condições | Status |
|---|---|---|---|---|---|---|---|---|
| T3.3 | Homologar contrato e proteção de comparabilidade dos KPIs | Consultora | SPEC-1-003 | CA-1-009 passa e mudança de fórmula/exclusão sem aprovação é rejeitada | TDD REGRESSÃO — versão e comparabilidade | aprovação verificável, hash e teste de alteração | T3.1 e T3.2 aceitas | ☐ |
| T5.3 | Validar autorização server-side, auditoria e exportação controlada do painel | QA de Segurança | SPEC-1-005 | CA-1-016 e CA-1-022 passam; API nega acesso/exportação indevidos e registra tentativas | TDD REGRESSÃO — permissão e auditoria | logs, respostas 403, relatório de testes e demonstração | T5.2 aceita; perfis de teste criados | ☐ |

### Leva F
| ID | Task | Dono | SPEC | Critério | Recorte da prova | Evidência esperada | Pré-condições | Status |
|---|---|---|---|---|---|---|---|---|
| T6.3 | Consolidar evidências e emitir decisão de saída da Fase 1 | Consultora | SPEC-1-006 | CA-1-018 e CA-1-019 passam: F2 liberada somente com G1–G4/G9 aprovados; sem G2 ocorre pausa | TDD GREEN — cenários go, G2 bloqueado e G6 pendente | ledger final, termo go/no-go versionado e backlog | T1.3, T2.3, T3.3, T4.3, T5.3 e T6.2 aceitas | ☐ |
