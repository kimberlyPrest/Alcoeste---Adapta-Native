# Controle do aprendizado contínuo

Registro dos aprendizados verificados por task. Ausência de sinal reutilizável também é registrada.

| Data | Task | Aprendizado | Arquivo |
|---|---|---|---|
| 2026-10-19 | T1.3 | Mutação de planilha xlsx: edição via openpyxl perde o cache de fórmula; corrigir em XML-level. | `2026-10-19-t13-mutacao-fomula-cache.md` |
| 2026-10-28 | T3.1 | Teste humano no Windows: entregar HTML autocontido de duplo clique, nunca `.js` (cai no Windows Script Host). | `AP-2026-10-28-1055-teste-humano-duplo-clique.md` |
| 2026-11-10 | T3.3 | Campo documentado que o código não lê é promessa quebrada. Testar o critério como ataque; auditar campos por comportamento. | `AP-2026-11-10-campo-sem-consumidor.md` |

## Notas de método

- **T3.2 (05/11/2026)** — sem sinal novo reutilizável além do já registrado em T1.3 sobre edição de planilha. A lição de semântica de coluna (acumulado vs incremento) foi ruim o bastante para virar regra operacional, mas é específica de leitura de planilha de terceiro e está descrita no próprio dataset (`semanticas` em `dataset-intervencoes.json`) e nos testes.
- **Pendências de conhecimento declaradas** ao fim da T3.3: taxonomia formal de falha/parada (o Excel não a traz) e donos por nome em Manutenção/Eng. de Dados. Ambas são lacunas de insumo, não de aprendizado.
