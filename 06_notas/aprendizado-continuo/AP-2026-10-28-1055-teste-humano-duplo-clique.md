# AP-2026-10-28-1055 — Teste humano exige artefato de clique único, não pacote de engenharia

- Status: candidato
- Escopo: projeto do cliente
- Task/SPEC: T3.1 / SPEC-1-003 · origens: `06_notas/debug/debug-2026-10-28-teste-humano-windows.md`
- Sinal: o gate de teste humano da T3.1 falhou com "Windows Script Host / Linha 5 / Código 800A03EA" quando o champion abriu `kpiContract.test.js` por duplo clique. O Windows associa `.js` ao Windows Script Host (motor JScript), que não suporta módulos ES — a linha 5 era `import test from 'node:test'`. Nada no produto estava errado; o erro foi de formato de entrega.
- Evidência: captura de tela do erro enviada pelo champion em 2026-10-28; `800A03EA` documentado como erro de compilação do JScript; após a correção, o mesmo conteúdo executado no navegador deu 27/27 testes e 11/11 provas, e o HTML regenerado a partir do zip apresentou hash idêntico ao entregue (5b75f025) — prova de que o artefato de clique único não divergiu do teste automatizado.
- Regra reutilizável: toda entrega que dependa de um gate humano deve incluir, na própria entrega, um artefato autocontido aberto por duplo clique (HTML gerado a partir dos mesmos testes, com shim mínimo do runner), sem exigir instalação de runtime, terminal ou variável de ambiente.
- Quando aplicar: qualquer task cujo critério de pronto dependa de o cliente executar algo para aceitar — testes automatizados, validações de planilha, contratos verificáveis. Gerar o visualizador junto com o pacote e verificar seu resultado no navegador antes de entregar.
- Quando não aplicar: quando o teste humano for inerentemente operacional (abrir o app Skip, conferir uma tela de produção, validar comportamento em equipamento real) — nesses casos o artefato não substitui a execução e o roteiro deve descrever o caminho real.
- Confiança: alta — causa raiz demonstrada pela linha exata do erro e correção validada por hash e por execução no navegador.
- Privacidade: sem segredo, dado pessoal ou conteúdo bruto.
