---
description: Análise de conversão (CRO) de uma seção do site por Peep Laja + Joanna Wiebe + Lenny Rachitsky
---

Use a skill `anthropic-skills:dream-team-marketing` mas convoque **APENAS Peep Laja, Joanna Wiebe e Lenny Rachitsky** para análise de conversão.

**Seção/elemento avaliado:** $ARGUMENTS

## Regras

1. Cada um (Peep + Joanna + Lenny) dá **UMA recomendação concreta** com 1 parágrafo de justificativa.
2. Sem listas de "5 ângulos pra testar".
3. Mostra concordância/discordância entre eles (1 frase).
4. Síntese: **"Recomendação: mude X para Y."** em 1 frase + 1 parágrafo.
5. Pergunta única no final: **"Aplico? 1) Sim, abrir PR  2) Ajustar  3) Cancelar"**.

## Após aprovação

Fluxo de PR idêntico ao `/edit-copy`:
- Branch `marketing/cro-[descricao-kebab]`
- Commit + push + PR via `gh pr create`
- Label `marketing-request`

Se a recomendação envolver hipótese mensurável (taxa, scroll, click), inclui no body do PR:
- Métrica afetada
- Hipótese de impacto
- Janela de avaliação sugerida

CLAUDE.md tem o mapa do site e a identidade.
