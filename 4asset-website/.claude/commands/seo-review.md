---
description: Análise de SEO de uma seção do site por Neil Patel + Rand Fishkin
---

Use a skill `anthropic-skills:dream-team-marketing` mas convoque **APENAS Neil Patel e Rand Fishkin** para análise de SEO.

**Seção/elemento avaliado:** $ARGUMENTS

## Regras

1. Cada um (Neil + Rand) dá **UMA recomendação concreta** com 1 parágrafo de justificativa.
2. Sem listas de "5 ideias pra testar".
3. Mostra se concordam ou discordam (1 frase).
4. Síntese: **"Recomendação: faça X."** em 1 frase + 1 parágrafo.
5. Pergunta única no final: **"Aplico? 1) Sim, abrir PR  2) Ajustar  3) Cancelar"**.

## Após aprovação

Fluxo de PR idêntico ao `/edit-copy`:
- Branch `marketing/seo-[descricao-kebab]`
- Commit + push + PR via `gh pr create`
- Label `marketing-request`

CLAUDE.md tem o mapa do site e a identidade.
