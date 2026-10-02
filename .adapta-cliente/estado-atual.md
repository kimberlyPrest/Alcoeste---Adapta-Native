# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: bloqueada
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”; decisões de mapeamento dadas em 2026-10-01 — “Código como chave única”, “Importar como componentes”, “Ignorar coluna APAGAR”.
- teste_humano: falhou em 2026-10-02T08:37:00-03:00 — Luís: “Encontrei uma falha no teste”; passo e resultado observados ainda não informados. Em 2026-10-02T08:40 Luís esclareceu que o teste desta fase deve usar planilha pequena da moenda, não o inventário da planta inteira; o arquivo revisado ainda não consta entre os anexos disponíveis.
- verificacao_automatica: passou na última execução registrada — Skip QA e fixture sintética 12/12 antes do relato de falha humana.
- aprendizado: pendente
- ultima_acao: Luís informou que substituiu a planilha completa por um recorte de teste da moenda e pediu ao Skip um campo para anexá-la. Conferi `uploads/`: só existe a cópia anterior `Equipamentos_-_Copia.xlsx` (1.926 registros; SHA-256 e17ab11b36e0275d101a45634c42e37a4637793420e3f4ef9c517972a40c5fcc). Não há novo XLSX no ambiente. O preview continua exigindo autenticação; não contornei o login. Sem o arquivo revisado e sem o passo/resultado da falha, não é possível reproduzir.
- proxima_acao: Luís anexar a planilha reduzida da moenda e informar qual passo da prévia falhou, o resultado esperado/observado e mensagem/relatório de erro
- atualizado_em: 2026-10-02T08:40:00-03:00
