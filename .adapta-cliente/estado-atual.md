# Estado atual — Adapta Cliente

- task_id: T1.2
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: confirmada em 2026-10-14T13:33 — “Sim” de Luís ao plano corrigido da T1.2 (classe derivada da Família; cobertura por criticidade em família rotativa).
- teste_humano: pendente — teste pelo preview com a planilha da moenda (f5b114ce-completo.xlsx). Resultado esperado: 226 candidatos, 222 aceitos, 4 bloqueados (MEL0097/BBA0053/MEL0096/BBA0054 com Código da Família vazio — pendência de dado para o PCM); cobertura dos 87 ativos: 9 covered, 12 uncovered (lacunas explícitas A: TM01-05, PR01-03, HI01-02, ET09, PI02), 19 not-required, 47 not-applicable; sem bloqueio de classe/sensor para os demais.
- verificacao_automatica: passou — Skip QA da versão 0.0.10/hash 15fb6d4 (setup, análise estática, build, integrações OK) e 14/14 testes locais; prova real pelo caminho completo da app com f5b114ce (números acima).
- aprendizado: pendente
- ultima_acao: T1.2 implementada (v1.2.0): tabela Família→Classe (rascunho PCM) + política de cobertura criticidade-rotativo + resumo de lacunas no relatório; correções de TDD durante a implementação (busca normalizada da tabela; “Não” não conta mais como sensor). Reversão: restaurar validate.js/schema-v1-1.js/readWorkbook.js da versão 0.0.9 (hash 0a28eb9).
- proxima_acao: Luís testar o preview com a planilha da moenda e confirmar os números esperados; em paralelo, PCM validar o rascunho Família→Classe e preencher a família dos 4 ativos bloqueados.
- atualizado_em: 2026-10-14T15:45:00-03:00
