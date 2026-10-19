# Aprendizado contínuo — 2026-10-19 · T1.3

**Sinal reutilizável:** SIM.

**Padrão:** planilhas com FÓRMULAS não podem ser mutadas via openpyxl com `data_only=True` + `save()`: o openpyxl grava a fórmula com `<v></v>` vazio (cache perdido) e leitores que dependem do valor em cache (read-excel-file) retornam null — a mutação parece aplicar-se mas o arquivo fica sem dado, quebrando qualquer prova de regressão silenciosamente.

**Correção aplicada:** mutação em nível de XML dentro do zip (trocar apenas o `<v>` da célula alvo, preservando sharedStrings e cache), ou usar openpyxl SEM data_only (preserva fórmulas, mas exige recálculo externo).

**Orientação:** antes de qualquer prova que modifique xlsx, verificar se a planilha contém fórmulas (`<f>` no XML) e escolher o método de edição que preserva o cache de valores. Sintoma típico: células que tinham valor passam a ler null após o round-trip openpyxl.
