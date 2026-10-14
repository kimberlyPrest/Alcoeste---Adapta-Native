# Status

**Fase atual:** Fase 1 — Fundação do piloto, catálogo, conectividade e baseline
**Estado:** em execução — Leva A concluída (T1.1); Leva B iniciada (T1.2 concluída, T2.1/T3.1 pendentes)
**Progresso das tasks:** 2/17 concluídas (T1.1, T1.2) — 12%
**Atualizado em:** 2026-10-14

## T1.1 — CONCLUÍDA (14/10/2026)
- Esquema de importação v1.1.0b (Skip 0.0.9/0a28eb9): TAG curta = localização, Status derivável, aba TAG Localização opcional, alias de cabeçalho, Código como chave.
- Evidência: f5b114ce-completo.xlsx (SHA d1c35b94) — 139/226 aceitos, 87 bloqueados (pendências da T1.2), grafias RS07/TQ109 confirmadas, zero duplicatas.
- Emenda aplicada sob autorização de Luís, sem homologação da Kim (reversão documentada; dívida marcada no código).

## T1.2 — CONCLUÍDA (14/10/2026)
- Contrato v1.2.0 (Skip 0.0.10/15fb6d4): Classe derivada da Família (23 famílias, rascunho pendente de validação do PCM) + cobertura orientada por criticidade em família rotativa (regra confirmada por Luís; lacuna nunca bloqueia nem marca "saudável").
- Evidência: 226 candidatos → 222 aceitos, 4 bloqueados (MEL0097/BBA0053/MEL0096/BBA0054 com família vazia — pendência de dado do PCM); cobertura: 9 covered / 12 uncovered (TM01-05, PR01-03, HI01-02, ET09, PI02 — todos criticidade A) / 19 not-required / 47 not-applicable; 14/14 testes automatizados; CA-1-001 e CA-1-002 verificados com evidência.
- Lacuna real do piloto mapeada: 12 ativos de criticidade A sem sensor (backlog de monitoramento); os 9 cobertos são os pontos IoTebe ativos.
