# Estado atual — Adapta Cliente

- task_id: T1.2
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: concluida
- autorizacao_implementacao: confirmada em 2026-10-14T13:33 — “Sim” de Luís ao plano corrigido da T1.2 (classe derivada da Família; cobertura por criticidade em família rotativa).
- teste_humano: aprovado em 2026-10-14T14:25 — “Testei e funcionou”.
- verificacao_automatica: passou — verificação independente do zero: 14/14 testes locais; caminho completo da app contra f5b114ce (226 candidatos, 222 aceitos, 4 bloqueados com família vazia — pendência PCM; cobertura 9 covered/12 uncovered/19 not-required/47 not-applicable); CA-1-002 provado (todos os 12 descobertos têm COVERAGE_GAP_UNCOVERED, nenhum marcado coberto/saudável); caminhos de erro exercitados (arquivo vazio bloqueia; família vazia bloqueia para o PCM); nenhum segredo no pacote; Skip QA 0.0.10/15fb6d4 OK.
- aprendizado: capturado:06_notas/aprendizado-continuo/2026-10-14-t12-derivacao-e-cobertura.md
- ultima_acao: T1.2 concluída — fase.md marcado (T1.1 ✅ 14/10, T1.2 ✅ 14/10), STATUS.md atualizado (2/17 = 12%), changelog 1a1553e0, estado concluida. Lacuna real do piloto mapeada: 12 ativos de criticidade A sem sensor (TM01-05, PR01-03, HI01-02, ET09, PI02); 9 cobertos = pontos IoTebe. Pendências para a T1.3: PCM valida rascunho Família→Classe e preenche a família dos 4 ativos bloqueados; Kim homologa emendas v1.1.0/v1.2.0.
- proxima_acao: Aguardar Luís solicitar a próxima task (Leva B: T2.1 pré-condição de fontes OT com TI/OT, ou T3.1 dicionário de KPIs com PCM — ambas independentes da decisão da Kim).
- atualizado_em: 2026-10-14T14:30:00-03:00
