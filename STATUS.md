# Status

**Fase atual:** Fase 1 — Fundação do piloto, catálogo, conectividade e baseline
**Estado:** em execução — SPEC-1-001 concluída (T1.1, T1.2, T1.3); Levas A–F em sequência
**Progresso das tasks:** 3/17 concluídas (T1.1, T1.2, T1.3) — 18%
**Atualizado em:** 2026-10-19

## SPEC-1-001 — CONCLUÍDA (19/10/2026)
- Catálogo da moenda homologado e congelado: 226 registros (83 ativos + 143 componentes), 8 localizações, zero bloqueios, ZERO exclusões (denominador de K1 integral).
- Versão congelada: planilha b15a040c (SHA 5e751003), contrato v1.2.0 (schema 6c23017b, validador db83e067, leitor 5daa40f9), Skip 0.0.10/15fb6d4. Termo: 06_notas/termo-homologacao-t1.3.md.
- Prova de regressão de versionamento PASSOU: mutação controlada TM01 A→B reclassifica cobertura (uncovered→not-required), original íntegro por SHA, diff auditável de 1 célula.
- Cobertura congelada: 9 covered (IoTebe) / 12 lacunas explícitas de criticidade A (TM01-05, PR01-03, HI01-02, ET09, PI02) / 19 not-required / 47 not-applicable.
- Pendências externas (não bloqueiam): homologação da Kim das emendas v1.1.0/v1.1.0b/v1.2.0 (desde 02/10, escalada 13/10; precedente de reversão garantida) e validação do rascunho Família→Classe pelo PCM.

## T1.1 — CONCLUÍDA (14/10/2026)
- Esquema de importação v1.1.0b (Skip 0.0.9/0a28eb9): TAG curta = localização, Status derivável, aba TAG Localização opcional, alias de cabeçalho, Código como chave.
- Evidência: f5b114ce-completo.xlsx (SHA d1c35b94) — 139/226 aceitos, 87 bloqueados (pendências da T1.2), grafias RS07/TQ109 confirmadas, zero duplicatas.

## T1.2 — CONCLUÍDA (14/10/2026)
- Contrato v1.2.0 (Skip 0.0.10/15fb6d4): Classe derivada da Família (23 famílias, rascunho pendente de validação do PCM) + cobertura orientada por criticidade em família rotativa (regra confirmada por Luís; lacuna nunca bloqueia nem marca "saudável").
- Evidência: 226 candidatos → 222 aceitos, 4 bloqueados (MEL0097/BBA0053/MEL0096/BBA0054 com família vazia — pendência de dado do PCM); 14/14 testes automatizados; CA-1-001 e CA-1-002 verificados com evidência.
