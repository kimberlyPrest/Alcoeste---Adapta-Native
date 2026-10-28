# Status

**Fase atual:** Fase 1 — Fundação do piloto, catálogo, conectividade e baseline
**Estado:** em execução — SPEC-1-001 concluída (T1.1, T1.2, T1.3); SPEC-1-003 em andamento (T3.1 concluída); Levas A–F em sequência
**Progresso das tasks:** 4/17 concluídas (T1.1, T1.2, T1.3, T3.1) — 24%
**Atualizado em:** 2026-10-28

## T3.1 — CONCLUÍDA (28/10/2026)
- Contrato de medição dos KPIs v1.0.0 (SPEC-1-003): fórmula, numerador, denominador, janelas, fonte, exclusões e dono de K1/K2/K3, com cálculo puro e reprodutível.
- Parâmetros aprovados por Luís em 27/10: denominador K1 = 15 ativos (21 de criticidade A − hilos HI01/HI02 − pontes PR01/PR02/PR03 − PI02 inativo); ternos TM01–TM05 cobertos pelos acionamentos AC01–AC03; PI02 com reentrada automática ao voltar a operar; ET09 declarado como lacuna real; janela de antecipação do K2 = 7 dias; janelas mensal e safra nos três KPIs.
- Baseline K1 sobre o catálogo congelado 7c754e0e: 14/15 = 93,3% (9 com sensor direto + 5 ternos via acionamento); única lacuna ET09. K2 e K3 inconclusivos — não há eventos nem alertas na fonte ainda, comportamento correto por CA-1-008.
- Evidência: 27/27 testes TDD do contrato (RED registrado antes da implementação); 14/14 de regressão do catálogo; prova real de baseline reproduzindo o briefing v1.0; prova do CA-1-009 (mudança de denominador sem aprovação bloqueia o cálculo inteiro; com aprovação é aceita e destacada); 17/17 critérios da SPEC-1-003 com evidência observável.
- Artefato: artifacts/T3.1-contrato-kpis-v1.0.0.zip (sha256 ebf97408). Briefing operacional v1.0 em artifacts/t31-briefing-kpis/. Nada publicado no app Skip: a task entrega contrato e memória de cálculo; o painel é a T5.2.
- Pendências externas (não bloqueiam): taxonomia formal de falha/parada (Excel "KPIs Moenda e Caldeira 2024" ausente do handoff); donos nomeados por nome nos papéis PCM/Manutenção/Engenharia de Dados; ratificação formal do PCM sobre o denominador (homologação é da T3.3).

## SPEC-1-001 — CONCLUÍDA (19/10/2026)
- Catálogo da moenda homologado e congelado: 226 registros (83 ativos + 143 componentes), 8 localizações, zero bloqueios, ZERO exclusões (denominador de K1 integral).
- Versão congelada: planilha b15a040c (SHA 5e751003), contrato v1.2.0 (schema 6c23017b, validador db83e067, leitor 5daa40f9), Skip 0.0.10/15fb6d4. Termo: 06_notas/termo-homologacao-t1.3.md.
- Prova de regressão de versionamento PASSOU: mutação controlada TM01 A→B reclassifica cobertura (uncovered→not-required), original íntegro por SHA, diff auditável de 1 célula.
- Cobertura congelada: 9 covered (IoTebe) / 12 lacunas explícitas de criticidade A (TM01-05, PR01-03, HI01-02, ET09, PI02) / 19 not-required / 47 not-applicable.
- Catálogo atualizado em 27/10 para 7c754e0e (correção de responsáveis André→Antônio nos motores e Deivid nas demais ocorrências, coluna Status, 18 sensores corrigidos, 2 criticidades B→A): 226/226 aceitos, 0 bloqueados, cobertura 9/12/19/43 — universo idêntico ao baseline congelado b15a040c. Hash de referência do catálogo passa a ser 7c754e0e.
- Pendências externas: homologação da Kim das emendas v1.1.0/v1.1.0b/v1.2.0 ENCERRADA — aprovada pela consultora e executada em 23/10 (Skip 0.0.11/cbb981d). Validação do rascunho Família→Classe pelo PCM ENCERRADA — validada por Luís em 19/10 e promovida a vocabulário homologado no termo da T1.3.

## T1.1 — CONCLUÍDA (14/10/2026)
- Esquema de importação v1.1.0b (Skip 0.0.9/0a28eb9): TAG curta = localização, Status derivável, aba TAG Localização opcional, alias de cabeçalho, Código como chave.
- Evidência: f5b114ce-completo.xlsx (SHA d1c35b94) — 139/226 aceitos, 87 bloqueados (pendências da T1.2), grafias RS07/TQ109 confirmadas, zero duplicatas.

## T1.2 — CONCLUÍDA (14/10/2026)
- Contrato v1.2.0 (Skip 0.0.10/15fb6d4): Classe derivada da Família (23 famílias, rascunho pendente de validação do PCM) + cobertura orientada por criticidade em família rotativa (regra confirmada por Luís; lacuna nunca bloqueia nem marca "saudável").
- Evidência: 226 candidatos → 222 aceitos, 4 bloqueados (MEL0097/BBA0053/MEL0096/BBA0054 com família vazia — pendência de dado do PCM); 14/14 testes automatizados; CA-1-001 e CA-1-002 verificados com evidência.

## Próximas tasks elegíveis
- T4.1 (fixture e perfilador de séries) · T5.1 (contrato do painel) · T2.1 (fontes OT — travada: sem responsável TI/OT designado) · T6.1 (workshop/RACI — dono consultora).
- T3.2 depende de T3.1 (concluída) e de fontes PIMS/Excel disponibilizadas — ainda pendente de insumo.
