---
description: Edição direta e rápida de texto no site (sem análise estratégica)
---

Edição simples e objetiva — sem convocar o Dream Team.

**Pedido do usuário:** $ARGUMENTS

## Fluxo

1. **Lê o arquivo afetado** (consulta o mapa em CLAUDE.md se não estiver claro qual seção é).
2. **Identifica o trecho exato** a alterar.
3. **Confirma em UMA frase**: "Vou trocar **X** por **Y** em [seção]. Confirma? 1) Sim 2) Ajustar"
4. **Se aprovado**, executa via Bash:
   ```bash
   git checkout main && git pull
   git checkout -b marketing/[descricao-kebab]
   # ... Edit do arquivo ...
   git add [arquivo] && git commit -m "marketing: [resumo curto]"
   git push -u origin marketing/[descricao-kebab]
   gh pr create --base main --title "[marketing] [resumo]" --body "[body curto]" --label "marketing-request"
   ```
5. **Retorna**: link do PR + "Revise e clique em **Merge** quando aprovar. Site atualiza em ~30s."

## Body do PR (curto, não use PRD)

```markdown
## Pedido
[pedido original do usuário]

## Mudança
| | Antes | Depois |
|---|---|---|
| ... | ... | ... |

## Arquivo afetado
- `[arquivo]` linha [N]

---
Solicitado por: [usuário do Codespace, via `$GITHUB_USER` ou perguntar]
```

## Regras

- ❌ NUNCA commit direto em `main`
- ❌ NUNCA `gh pr merge` automático — sempre espera humano clicar
- ❌ Não use PRD completo pra edição trivial
- ✅ Mantenha identação e tags HTML do entorno ao editar

Se a mudança parecer **estratégica** (mudar posicionamento, headline, CTA principal), pergunta: "Isso parece estratégico — quer que eu chame o `/dream-team` antes ou faço direto? 1) Dream Team 2) Direto 3) Cancelar."
