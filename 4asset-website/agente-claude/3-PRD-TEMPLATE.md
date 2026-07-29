# PRD TEMPLATE — vira corpo do PR

> Adicione em: **Project → Knowledge → Upload file**
> Este template é usado pelo agente ao final do fluxo do Dream Team. O PRD completo é colado como **corpo do PR** no GitHub. Marketing **nunca** precisa abrir o GitHub para ver — o link do PR é enviado no chat só pra registro.

---

# PRD — [TÍTULO CURTO]

## 1. Identificação
- **Solicitado por:** [nome do membro do marketing — coletado via elicitation]
- **Data:** [data ISO]
- **Canal:** Claude Project · Site 4Asset
- **Tipo:** [copy · SEO · conversão · funil · tagging · atribuição · design · estratégia]
- **Slash command usado:** `/dream-team` · `/edit-copy` · `/seo-review` · etc.

## 2. Pedido original
> [Mensagem original do usuário, sem editar]

## 3. Contexto identificado
- **Página/seção afetada:** [ex: Hero · Pilares · Cards de produto · Footer]
- **Arquivo(s):** `index.html` (linhas X-Y) · `privacidade.html` · etc.
- **Versão pública atual:** https://herculesbreno.github.io/site-4asset/

## 4. Análise do Dream Team

> Para cada especialista convocado, registre o parecer em primeira pessoa, no estilo da persona.

### [Nome] · [Domínio]
[Parecer de 2-4 parágrafos:
- Diagnóstico
- Recomendação concreta
- Hipótese mensurável (quando aplicável)
- Riscos]

[Repita para cada especialista convocado]

## 5. Síntese
### Consensos
- [Ponto de acordo entre os especialistas]

### Tensões / trade-offs
- **[Especialista A] x [Especialista B]:** [resumo da discordância]

### Recomendação final
[Sua proposta consolidada como orquestrador, considerando o contexto da 4Asset — B2B, decisor enterprise, RD Station + GA4.]

## 6. Implementação proposta

### Arquivos afetados
- `[arquivo]` — linhas [X-Y] — [tipo de mudança]

### Antes (trecho atual)
```html
[código atual fiel ao repositório]
```

### Depois (trecho proposto)
```html
[código proposto]
```

### CSS / JS alterados
[Liste ou "Nenhum"]

### Impacto em outras seções
[Liste ou "Nenhum"]

## 7. Métricas de validação
- **North Star:** [ex: leads qualificados via RD]
- **Métricas secundárias:** [ex: scroll, click CTA]
- **Linha de base:** [valor ou "auditoria pendente"]
- **Hipótese de impacto:** [ex: "+15% em CTR no CTA hero em 30 dias"]
- **Janela de avaliação:** [ex: 30 dias]
- **Tagueamento adicional?** [se sim, listar evento + schema]

## 8. Auditorias externas necessárias
> O Dream Team identificou validações que dependem de dados ao vivo.

- [ ] [Ex: confirmar evento `cta_hero_click` no GTM]
- [ ] [Ex: validar UTM no RD Station]
- [ ] [Ex: pedir audit do share of search]

## 9. Riscos
- **[Risco]:** [descrição + mitigação]

## 10. Aprovações
- [ ] Solicitante (marketing)
- [ ] Gestor (Hercules / Maurício)
- [ ] Dev (apenas se mudança envolver CSS/JS/estrutura)

---

## 🔧 Output do PR (gerado automaticamente pelo Claude via GitHub Connector)

Após aprovação:
- **Branch:** `dreamteam/[descricao-kebab-case]` ou `marketing/[descricao]`
- **Título do PR:** `[dreamteam] [resumo até 60 chars]` ou `[marketing] [resumo]`
- **Labels:** `marketing-request`, `dream-team` (se aplicável)
- **Corpo do PR:** este PRD inteiro (seções 1-10), suprimindo a seção 🔧
- **Assinatura final:**
  ```
  ---
  Solicitado por: [nome]
  Analisado pelo Dream Team em: [data]
  Especialistas convocados: [lista]
  Pedido via: Claude Project · /dream-team
  ```

## 💬 Mensagem final para o marketing no chat (após PR criado)

> ✅ **PR aberto e encaminhado para aprovação.**
>
> 🔗 [link do PR]
> 👤 Aprovador notificado: [nome]
> ⏱️ Você recebe o status final em até X horas.
>
> Quer fazer outro pedido?
