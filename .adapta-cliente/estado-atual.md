# Estado atual — Adapta Cliente

- task_id: T1.1
- champion: Marie Egashira
- spec: 04_fase-atual/specs/SPEC-1-001.md
- etapa: aguardando_teste_humano
- autorizacao_implementacao: confirmada em 2026-09-30T10:41:22-03:00 — “Autorizar implementação da T1.1”. Em 2026-10-13T12:04 Luís autorizou a emenda v1.1.0 sem homologação da consultora — “pode implementar a v1.1.0 para dar sequência no desenvolvimento, caso necessário depois retrocedemos para alguma correção”.
- teste_humano: falhou em 2026-10-13T15:40 — “Deu erro no teste”. Debug concluído no mesmo dia; novo teste pendente.
- verificacao_automatica: passou — Skip QA da versão 0.0.9/hash 0a28eb9 (setup, análise estática, build, integrações OK; suíte não executada pela plataforma) e 13/13 testes locais (12 anteriores + 1 novo de alias). Reprodução do caminho completo da app com a planilha real 0ab918e8: 226 candidatos, 135 aceitos, 91 bloqueados (87 classe/sensores T1.2 + 4 grafias RE07/TQ09).
- aprendizado: pendente
- ultima_acao: DEBUG T1.1 — causa raiz demonstrada: a planilha da moenda rotula a coluna de TAG como “TAG Localização” e o contrato v1.1.0 exigia o cabeçalho canônico “TAG”; o validador parava no cabeçalho ausente com 0 registros processados. Correção mínima v1.1.0b: alias oficial tagHeaderAliases (TAG ← “TAG Localização”) no headerIndex. Aplicado no Skip versão 0.0.9/hash 0a28eb9, QA OK, não publicada. Reversão: restaurar validate.js/schema-v1.js/readWorkbook.js da versão 0.0.7 (hash 67460fa).
- proxima_acao: Luís repetir o teste no preview com a planilha da moenda (0ab918e8-completo.xlsx) e confirmar o resultado: ~135/226 aceitos, 91 bloqueados (87 classe/sensores + 4 grafias), sem bloqueio de “Coluna obrigatória ausente: TAG”.
- atualizado_em: 2026-10-13T18:50:00-03:00
