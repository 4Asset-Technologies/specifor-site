---
description: Convoca o Dream Team de Marketing para análise estratégica de mudanças no site 4Asset
---

Use a skill `anthropic-skills:dream-team-marketing` para conduzir a análise estratégica.

**Pedido do usuário:** $ARGUMENTS

## Overrides obrigatórios (substituem o comportamento padrão da skill)

A skill traz 9 especialistas. Você **não vai usar todos** — convoca só os relevantes pro tipo de pedido:

| Tipo de pedido | Convoque |
|---|---|
| Copy / headline / CTA | Joanna Wiebe + Peep Laja + Rand Fishkin |
| SEO / keywords | Neil Patel + Rand Fishkin |
| Conversão / value prop | Peep Laja + Joanna Wiebe + Lenny Rachitsky |
| Funil / aquisição | Andrew Chen + Lenny Rachitsky + Christopher Mercer |
| Tagging / GTM / GA4 | Julius Fedorovicius + Christopher Mercer |
| Atribuição / RD Station | Christopher Mercer + Andrew Chen |
| Design / UX | Sahil Lavingia + Peep Laja |
| Métricas / North Star | Lenny Rachitsky + Andrew Chen |
| Mudança grande / posicionamento | Todos os 9 |

## REGRA DE OURO — decisões, não menus

1. Cada especialista entrega **UMA recomendação concreta**, defendida em **1 parágrafo** (máx 4 frases).
2. **NUNCA** lista "5 ângulos pra testar". Sem tabela de alternativas.
3. Mostra **concordância ou discordância explícita** entre os especialistas (1 frase).
4. Síntese final = **VEREDICTO fechado**: copy / headline / decisão em 1 frase + 1 parágrafo de justificativa.
5. Máximo **UMA pergunta de clarificação** antes do veredicto — e só se a resposta muda a recomendação.
6. Termina sempre com: **"Aplico no site? 1) Sim, abrir PR  2) Ajustar  3) Cancelar"**

## Anti-padrão proibido

❌ "Aqui vão 5 ângulos testáveis: dor / autoridade / resultado / nicho / prova social — sua escolha."
❌ "Você pode testar A, B ou C — depende do perfil de cliente."
❌ Tabela com 5 headlines diferentes.

## Padrão obrigatório

✅ "**Joanna recomenda:** 'Gestão de ativos para transmissoras, do laudo à conformidade ANEEL.' Nomeia segmento, jobs-to-be-done e regulador. Sem 'plataforma', sem superlativo. **Peep concorda.** **Rand** aceita se houver cliente nomeável.
**Veredicto:** Headline = 'Gestão de ativos para transmissoras, do laudo à conformidade ANEEL.' Subheadline = '...'. Aplico? 1) Sim 2) Ajustar 3) Cancelar"

## Após aprovação ("1) Sim, abrir PR")

Executa o fluxo de PR (mesmo do `/edit-copy`):
```bash
git checkout main && git pull
git checkout -b dreamteam/[descricao-kebab]
# ... Edit do arquivo ...
git add [arquivo] && git commit -m "dreamteam: [resumo]"
git push -u origin dreamteam/[descricao-kebab]
gh pr create --base main --title "[dreamteam] [resumo]" --body "[PRD completo do veredicto]" --label "marketing-request"
```

**Body do PR** pra `/dream-team` = PRD completo (use o template em `agente-claude/3-PRD-TEMPLATE.md` como referência), incluindo:
- Pedido original
- Especialistas convocados
- Recomendações de cada um (1 parágrafo cada)
- Síntese / veredicto
- Mudança aplicada (antes/depois)
- Métricas de validação propostas

**Retorna:** link do PR + "Revise o PRD no PR e clique em **Merge** quando aprovar."

## CLAUDE.md tem

- Mapa do site (qual elemento mora em qual arquivo/linha)
- Identidade visual (cores, fonte, tom)
- Regras de conteúdo (números oficiais, clientes, termos banidos)

Consulte sempre antes de propor uma alteração.
