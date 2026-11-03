# Estado atual — Adapta Cliente

- task_id: T2.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-002.md
- etapa: aguardando_autorizacao
- autorizacao_implementacao: ausente — análise da T2.1 emitida em 2026-11-03; aguardando "pode implementar" em mensagem nova.
- teste_humano: pendente
- verificacao_automatica: pendente
- aprendizado: pendente
- ultima_acao: T2.1 selecionada e analisada. Pré-condição satisfeita — Peterson nomeado responsável TI/OT por Luís em 03/11/2026. Insumos levantados com dado real: API IoTebe (fonte já em uso, 34 spots NG1VT com sensor, 1 amostra/min, cobertura 24h entre 95,6% e 98,8%, gap máximo 241 s, 8 variáveis por spot incluindo VELOCIDADE/ACELERAÇÃO/TEMPERATURA/KURTOSIS/SKEWNESS/RMS, timestamp UNIX); 14 dos 15 ativos do denominador K1 com sensor — única lacuna ET09. Decisões de Luís em 03/11: Exaustor Direito/Esquerdo é da caldeira, fora do escopo da moenda (expansão futura); o acesso à API IoTebe permite todos os acessos aos dados, mas a diretriz vigente é usar somente GET, sem escrita; o IoTebe oferece menor privilégio (visualizador, colaborador, administrador) apenas por usuário cadastrado, não por chave de API. Fontes ainda não inventariadas: SCADA Sonne, historiador, IONICS, Solinftec, PIMS MI, exportações e base de OS/PIMS. 03_documentos e 02_reunioes seguem vazios.
- proxima_acao: Aguardar autorização de Luís para implementar a T2.1 (validador do gate G2 com TDD RED + inventário das fontes + protocolo da prova de acesso + diagrama preliminar IT/OT).
- atualizado_em: 2026-11-03T14:20:00-03:00
