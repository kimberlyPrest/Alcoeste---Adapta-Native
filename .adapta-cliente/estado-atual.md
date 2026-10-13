# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”. Em 2026-10-13T12:04 Luís autorizou a emenda v1.1.0 sem homologação da consultora — “pode implementar a v1.1.0 para dar sequência no desenvolvimento, caso necessário depois retrocedemos para alguma correção”.
- teste_humano: pendente — teste pelo preview do app com a planilha da moenda (0ab918e8-completo.xlsx). Resultado esperado: 135/226 aceitos; 91 bloqueados (87 por classe/sensores pendentes de homologação T1.2 + 4 por grafia de pai RE07/TQ09); SEM DUPLICATE_COMPONENT_TAG em massa.
- verificacao_automatica: passou — Skip QA da versão 0.0.8/hash 683477b (setup, análise estática, build, integrações OK; suíte não executada pela plataforma) e 12/12 testes locais (11 originais da fixture RED + 1 novo teste sintético v1.1.0).
- aprendizado: pendente
- ultima_acao: Emenda v1.1.0 implementada e aplicada no Skip (projeto 57219, versão 0.0.8/hash 683477b, modo development, não publicada): schema-v1-1.js (TAG curta repetida = localização; aba TAG Localização opcional; Status derivável da estrutura da TAG; Código como chave; Classe permanece opcional), validate.js emendado (localizações embutidas + Status derivado), readWorkbook.js com schema ativo v1.1.0, subtítulo da prévia atualizado e novo teste sintético no suite. Reversão documentada nos arquivos: restaurar validate.js/schema-v1.js/readWorkbook.js da versão 0.0.7 (hash 67460fa). Dívida deliberada marcada (adapta-divida): dois modelos no mesmo contrato; unificar quando a Kim homologar. Dados reais da moenda permanecem fora do repositório; nenhum equipamento gravado; nenhum envio ao Skip Cloud.
- proxima_acao: Luís testar o preview com a planilha da moenda e confirmar se funcionou; em paralelo, Kim decidir a emenda (DÚVIDA de 02/10) e PCM corrigir as 2 grafias de TAG de pai (RE07→RS07, TQ09→TQ109).
- atualizado_em: 2026-10-13T15:25:00-03:00
