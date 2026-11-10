# Status

**Fase atual:** Fase 1 — Fundação do piloto, catálogo, conectividade e baseline
**Estado:** em execução — SPEC-1-001 concluída (T1.1, T1.2, T1.3); SPEC-1-003 concluída em execução (T3.1, T3.2, T3.3); Levas A–F em sequência
**Progresso das tasks:** 6/17 concluídas em execução (T1.1, T1.2, T1.3, T3.1, T3.2, T3.3) — 35%
**Atualizado em:** 2026-11-10

## T3.3 — EXECUÇÃO CONCLUÍDA (10/11/2026) · homologação do CA-1-009 pendente

- **Proteção de comparabilidade do contrato de KPIs.** Três lacunas encontradas e fechadas, todas do mesmo tipo: campo documentado que o código não cumpria.
  1. **Só o denominador era protegido.** Editar meta, fórmula, janela, exclusão ou dono passava com `baselineValid: true`, sem registro. Caso concreto: K1 em 80% não cumpria a meta de 90%; rebaixando a meta para 70% no arquivo, o mesmo 80% passava a "cumprir". Protegido com digest SHA-256 do contrato escrito como literal + registro de versões aprovadas.
  2. **`reentryOnActive` nunca era lido.** O contrato prometia que o PI02 reentraria ao voltar a operar; o cálculo ignorava o campo. O ativo voltaria a operar e seguiria fora do denominador para sempre, em silêncio. Achado no comentário do PCM na ratificação ("caso o cenário mude, irei informar"). Corrigido com reentrada automática e registro `REENTRY_ON_ACTIVE`.
  3. **`catalogBaseline.reference` nunca era conferido.** O contrato selava a si mesmo e aceitava dataset de qualquer catálogo, exibindo número como válido. Achado na auditoria de campos. Corrigido: o dataset declara `catalogReference` (SHA-256 do arquivo) e divergência bloqueia os três KPIs.
- **Qualquer bloqueio contamina os três KPIs** com `value: null` — não só o KPI tocado. Códigos: `CONTRACT_INTEGRITY_MISSING/_MISMATCH`, `CONTRACT_VERSION_NOT_APPROVED/_DIGEST_MISMATCH`, `CATALOG_REFERENCE_MISSING/_MISMATCH`.
- **Auditoria de campos:** 19 testados por comportamento (editar, re-selar o contrato e ver se o resultado muda — a checagem estática mente): **9 lidos, 10 sem efeito**. Script `auditar-campos.mjs` deixa a varredura repetível.
- **Evidência:** 68/68 testes em pacote limpo reextraído do zip v1.3 (27 contrato + 41 integridade); HTML 68/68 no navegador; digest do contrato recalculado confere (`a819e3e2`); baseline real 14/15 = 93,3% reproduzindo o briefing v1.0; prova do CA-1-009 nos 5 cenários. **Teste humano aprovado por Luís Arakaki em 10/11/2026.**
- **Artefato:** `artifacts/T3.3-contrato-integridade-v1.3.zip` (sha256 9ca8b57a). Dossiê: `artifacts/T3.3-dossie-homologacao.md`. Auditoria: `artifacts/T3.3-auditoria-campos-contrato.md`.
- **Pendências declaradas, não bloqueiam o CA-1-009:** janela "safra" aceita qualquer data (`startsMonth`/`endsMonth` ignorados) — gatilho: quando o painel (T5.2) exibir visão de safra; `qualityRule` promete avaliar qualidade do sinal (SPEC-1-004) que ainda não existe — gatilho: quando T4.1/T4.2 definirem "qualidade aceitável"; taxonomia formal de falha/parada; donos por nome em Manutenção e Eng. de Dados.
- **Homologação formal do CA-1-009 pela consultora está pendente.** Quem construiu não atesta.

## Ratificação do PCM sobre o denominador do K1 — ENCERRADA (05/11/2026)

- **Gustavo Godoy (PCM)** respondeu **SIM** às três perguntas: os 15 ativos são o recorte correto; as 6 exclusões procedem; os ternos TM01–TM05 podem ser contados como cobertos pela cadeia de acionamento AC01–AC03 ("hoje temos sensores nos mancais e volandeiras dos acionamentos").
- Denominador de **15 ativos ratificado tecnicamente**; K1 de referência 14/15 = 93,3%, acima da meta de 90%.
- Termo: `06_notas/termo-ratificacao-pcm-denominador-k1.md` (documento assinado com SHA-256 `078dbd1d`).

## T3.2 — CONCLUÍDA (05/11/2026)

- Dataset rastreável e baseline inicial (CA-1-008): **87 registros**, **61 intervalos**; mediana geral **610.418 t**.
- **FACAS** (picador): 8 ciclos, mediana **484.002 t** · **MARTELOS** (desfibrador): 10 ciclos, mediana **560.857 t** · **pente superior do 2º Terno**: 10 trocas, mediana **305.006 t** — maior desgaste.
- **Semântica por aba** (erro real corrigido): em PENTES a coluna é acumulada (intervalo = diferença); em FACAS-MARTELOS e ROTORES é o incremento do ciclo (intervalo = o próprio valor). Provado contra a coluna "MOAGEM TOTAL", que é a soma.
- **Divergência entre arquivos resolvida por Luís:** 2º ciclo de martelos de 2024 = **908.799,61 t** (arquivo de 2024), não 401.606,77 (arquivo de 2025, preenchido com valores de FACAS).
- K1 **mensurável** 14/15 = 93,3%; K2 **inconclusivo** (os Excel registram troca preventiva, não parada não programada); K3 **inconclusivo**. Nenhum declarado atingido.
- Artefato: `artifacts/T3.2-baseline-intervencoes-v1.2.zip` (sha256 f54472de); 21/21 testes.

## T3.1 — CONCLUÍDA (28/10/2026)

- Contrato de medição dos KPIs v1.0.0 (SPEC-1-003): fórmula, numerador, denominador, janelas, fonte, exclusões e dono de K1/K2/K3, com cálculo puro e reprodutível.
- Parâmetros aprovados por Luís em 27/10: denominador K1 = 15 ativos; ternos TM01–TM05 cobertos pelos acionamentos AC01–AC03; PI02 com reentrada automática; ET09 declarado como lacuna real; janela de antecipação do K2 = 7 dias; janelas mensal e safra.
- Baseline K1 sobre o catálogo congelado 7c754e0e: 14/15 = 93,3%. K2 e K3 inconclusivos — comportamento correto por CA-1-008.
- Evidência: 27/27 testes TDD; 14/14 de regressão; prova real de baseline; prova do CA-1-009. Artefato: `artifacts/T3.1-contrato-kpis-v1.0.0.zip`.

## SPEC-1-001 — CONCLUÍDA (19/10/2026)

- Catálogo da moenda homologado e congelado: 226 registros (83 ativos + 143 componentes), 8 localizações, zero bloqueios, ZERO exclusões.
- Versão congelada: planilha b15a040c (SHA 5e751003), contrato v1.2.0, Skip 0.0.10/15fb6d4. Termo: 06_notas/termo-homologacao-t1.3.md.
- Catálogo atualizado em 27/10 para **7c754e0e** (correção de responsáveis André→Antônio nos motores e Deivid nas demais; coluna Status; 18 sensores; 2 criticidades B→A): 226/226 aceitos, cobertura 9/12/19/43.
- Pendências externas: homologação da Kim das emendas ENCERRADA (23/10, Skip 0.0.11/cbb981d). Validação do rascunho Família→Classe ENCERRADA (Luís, 19/10).

## T1.1 / T1.2 — CONCLUÍDAS (14/10/2026)

- T1.1: esquema de importação v1.1.0b — 139/226 aceitos, 87 bloqueados (pendências da T1.2), zero duplicatas.
- T1.2: contrato v1.2.0 — Classe derivada da Família (23 famílias) + cobertura orientada por criticidade; 226 candidatos → 222 aceitos, 4 bloqueados (família vazia); 14/14 testes.

## Próximas tasks elegíveis

- **T5.1** (contrato do painel, estados, perfis e auditoria) — sem insumo externo, recomendada como próxima.
- **T4.1** (fixture e perfilador de qualidade de séries) — independente.
- **T2.2** (prova de leitura real) — depende da T2.1 aceita; hoje T2.1 aguarda teste humano.
- **T6.1** (workshop/RACI) — dona é a consultora; travada por fator externo.
- **T2.1** aguarda teste humano de Luís desde 04/11.
