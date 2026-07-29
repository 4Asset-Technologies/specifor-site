---
description: Lista PRs abertos do repositório com status atual
---

Execute:

```bash
gh pr list --state open --json number,title,labels,createdAt,author,headRefName,url --limit 50
```

Formate a saída como **duas tabelas markdown**:

## 🟡 Aguardando aprovação (label `marketing-request`)

| # | Título | Autor | Aberto há | Link |
|---|---|---|---|---|

## 📋 Outros PRs

| # | Título | Autor | Aberto há | Link |
|---|---|---|---|---|

Use cálculo simples de "aberto há" (dias / horas a partir de `createdAt`).

Se não houver PRs abertos, responda apenas:
> ✅ Nenhum PR aberto. Todas as mudanças anteriores já foram aprovadas e estão no site.

Não comente nem opine sobre o conteúdo dos PRs — só liste.
