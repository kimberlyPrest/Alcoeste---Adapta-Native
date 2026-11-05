# Estado atual — Adapta Cliente

- task_id: T3.3
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-003.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: confirmada — Luís autorizou em 05/11/2026 ("Sim") implementar a proteção de integridade do contrato antes de enviar a T3.3 para a Kim.
- teste_humano: pendente — Luís precisa abrir `artifacts/T3.3-teste-humano-abra-este-arquivo.html` (56/56) e confirmar. A homologação formal do CA-1-009 é da consultora (Kim), não do assistente nem do cliente.
- verificacao_automatica: passou — 56/56 testes em pacote limpo reextraído do zip (27 do contrato T3.1 + 29 de integridade T3.3); HTML verificado no navegador 56/56; prova em dado real confirma CA-1-009 nos 5 cenários; baseline real continua 14/15 = 93,3%.
- aprendizado: registrado — AP-2026-11-05-b (lacuna de integridade encontrada antes da homologação).
- ultima_acao: T3.3 IMPLEMENTADA (v1.1, zip 75e76145). Recusa fundamentada a homologar: quem constrói não atesta. Ao revisar o que o CA-1-009 exigia, encontrei brecha real ANTES do envio — o contrato só protegia mudança de DENOMINADOR; editar meta, fórmula, janela, exclusão ou dono direto no arquivo passava com `baselineValid: true` e nenhum registro. Caso concreto: K1 em 80% não cumpria a meta de 90%; rebaixando a meta para 70% no arquivo, o mesmo 80% passava a "cumprir", sem rastro. Corrigido com dois lacres independentes: (1) digest SHA-256 do conteúdo escrito como LITERAL em `kpiContract.js` (`a819e3e2c9b9a54e9018d9b13118601087ce47b28dd4fb8a67e8970f9aa5c712`) — se fosse calculado na carga, mudaria junto com a edição e nunca acusaria nada; (2) registro `APPROVED_VERSIONS` com digest aprovado, `approvalRef` e `approvedBy` — sem ele bastaria editar e recalcular o digest. 10 caminhos de ataque testados, todos bloqueiam os TRÊS KPIs com `value: null`. SHA-256 em JS puro validado contra vetores do NIST para rodar também no navegador. Dossiê para a homologadora em `artifacts/T3.3-dossie-homologacao.md`. Parâmetros aprovados em 27/10 (metas 90/80/80, denominador 15 ativos, exclusões 6, janelas) NÃO foram alterados — mudou apenas o lacre.
- proxima_acao: Luís abrir o HTML de teste humano e confirmar; depois encaminhar `T3.3-dossie-homologacao.md` + zip para a Kim homologar o CA-1-009. Só depois disso a T3.3 fecha.
- bloqueio_declarado: a homologação do CA-1-009 depende da consultora. K2 segue inconclusivo — os Excel registram troca preventiva, não parada não programada, e o arquivo de OS da moenda ainda é aguardado.
- atualizado_em: 2026-11-05T14:15:00-03:00
