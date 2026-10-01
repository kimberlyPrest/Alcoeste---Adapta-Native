# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: bloqueada
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”; decisões de mapeamento dadas em 2026-10-01 12:37: “Código como chave única”, “Importar como componentes”, “Ignorar coluna APAGAR”.
- teste_humano: pendente
- verificacao_automatica: pendente
- aprendizado: pendente
- ultima_acao: Reconciliado o mapeamento com a planilha real e a SPEC. 825 registros ATIVO têm Código único; entre as 1.100 linhas sem status, 12 códigos se repetem (26 linhas) e há 8 TAGs compostas duplicadas. Código+TAG é único nas 1.847 linhas com os dois campos. Importação dos 1.926 registros para o catálogo operacional não foi executada: T1.1 limita-se ao esquema/fixture/prova RED; carga completa aproxima-se da T1.2 e o universo piloto de ~80 ainda não está selecionado. Modelo atual do Skip não comporta componente, origem auditável ou fluxo de homologação; não migrei nem substituí os seeds existentes.
- proxima_acao: aguardar Kim esclarecer recorte T1.1/T1.2 e Luís/PCM aprovar chave de componente e universo inicial do piloto; depois executar apenas o artefato T1.1 autorizado
- atualizado_em: 2026-10-01T12:46:49-03:00
