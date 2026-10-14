# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: concluida
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”. Em 2026-10-13T12:04 Luís autorizou a emenda v1.1.0 sem homologação da consultora — “pode implementar a v1.1.0 para dar sequência no desenvolvimento, caso necessário depois retrocedemos para alguma correção”.
- teste_humano: aprovado em 2026-10-14T09:47 — teste da versão 0.0.9 processou a planilha da moenda com o comportamento projetado (87 ativos · 139 componentes · 87 bloqueados por classe/sensores · 313 pendências conhecidas); aceite formal em 2026-10-14T09:54 — “Certo. Pode concluir a T1.1”.
- verificacao_automatica: passou — evidência final pelo caminho completo da app contra f5b114ce-completo.xlsx (SHA-256 d1c35b94…): 226 candidatos, 139 aceitos, 87 bloqueados (classe/sensores → T1.2), zero PARENT_ASSET_UNRESOLVED (grafia RS07/TQ109 confirmada por evidência), zero duplicatas, zero cabeçalho ausente. 13/13 testes locais. Skip QA 0.0.9/0a28eb9 OK.
- aprendizado: capturado:06_notas/aprendizado-continuo/2026-10-14-t11-alias-cabecalho.md
- ultima_acao: T1.1 concluída. Evidências: f5b114ce-completo.xlsx (planilha final corrigida), 2129ed0a-Fam_lias.xlsx (110 famílias, cobertura 100% das 23 da moenda), 65c1f620-Equipamentos.xlsx (17 categorias de equipamento — vocabulário de Classes). Reversão da emenda v1.1.0 segue documentada (restaurar 0.0.7/67460fa) até a Kim homologar.
- proxima_acao: Aguardar Luís solicitar a T1.2 (tabela Família→Classe com as 23 famílias da moenda + mapa classe→exige sensor de vibração; decisão PCM, homologação Kim).
- atualizado_em: 2026-10-14T10:00:00-03:00
