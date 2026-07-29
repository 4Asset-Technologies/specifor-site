# Specifor On Premise — Design System

Camada de **design** que se aplica por cima do **conteúdo** (texto/seções) sem alterá-lo.
Princípio central:

> **Conteúdo** = o que está publicado (texto, seções, imagens). É a fonte da verdade e **nunca** é alterado pelo design system.
> **Design** = aparência (cor, vidro, espaçamento, animação). Vive em `design-system.css` e é aplicado automaticamente às classes que já existem.

Marketing (ou qualquer pessoa) sobe conteúdo novo → o design system estiliza sozinho, desde que use as classes/padrões abaixo. O **agente** (ver seção final) garante isso a cada push.

---

## Arquivos

| Arquivo | Papel |
|---|---|
| `design-system.css` | A camada de design. Linkar **depois** do `<style>` da página. |
| `styleguide.html` | Referência visual — todos os tokens e componentes. Abra para copiar blocos. |
| `DESIGN.md` | Este documento. |
| `.github/workflows/design-system.yml` | O agente (CI) que aplica/revê o design a cada push/PR. |
| `.github/design-system-agent.md` | Instruções do agente. |
| `.stylelintrc.json` | Regras que barram valores fora dos tokens. |

**Instalação numa página:** adicione antes de `</head>`:
```html
<link rel="stylesheet" href="design-system.css">
```

---

## Tokens (fonte única da verdade)

Definidos em `:root` no `design-system.css`. **Nunca** use valores "chumbados" — use o token.

| Token | Valor | Uso |
|---|---|---|
| `--ds-icon` | `#5cc6ff` | Cor padrão do glyph de **todos** os ícones |
| `--ds-brand` | `#4f63ff` | Azul da marca |
| `--ds-ink` | `#0f1d33` | Superfície/tinta escura |
| `--ds-surface-dark` | `#05070d` | Fundo de seções escuras |
| `--ds-glass-bg` / `-border` / `-blur` / `-shadow` / `-sheen` | — | Receita do badge "Liquid Glass" |
| `--ds-r-badge` / `--ds-r-card` | `16px` / `18px` | Raios padrão |
| `--ds-ease-glass` | `cubic-bezier(.16,1,.3,1)` | Varredura/hover (ref.: botão "Agent Portal") |
| `--ds-ease-spring` | `cubic-bezier(.34,1.4,.64,1)` | Elevação/entrada de cards |
| `--ds-fill-hover` | `rgba(255,255,255,0.10)` | Preenchimento que varre no hover |

---

## Componentes

### Badge de ícone (Liquid Glass)
Vidro fosco (blur), brilho especular no topo, profundidade e sombra, cantos squircle. Glyph em `--ds-icon`.
Aplica automaticamente a `.icon-badge` dentro de `.market-card`, `.h-stat` e `.hero .hero-stats`, e ao `.addon-item .icon` (como "chip").

### Hero — big numbers
Ícone com badge de vidro + **fundo que "varre" do centro no hover** (`scaleX(0)→scaleX(1)`, origem central, `--ds-ease-glass`, `--ds-fill-hover`). Número e label ficam acima do fundo.

### "O que resolve" (orbit cards)
Cards ancorados nas bordas da tablet (colados em qualquer largura); topo/base colados, **meio mais afastado** (arco). Posições independentes da tela; no responsivo a composição encolhe junto, nunca empilha.

### Setores / Mercados (cards com foto)
Grid uniforme (3→2→1). Card grande com **foto full-bleed** + degradê + nome branco + glow azul no hover.
A **foto é conteúdo**: adicione `<img class="m-img" src="setor.jpg" alt="Setor de X">` dentro do card. Sem foto, use a classe `is-placeholder` (fundo de marca).

```html
<div class="market-card">
  <img class="m-img" src="energia.jpg" alt="Setor de Energia">
  <div class="m-body">
    <div class="icon-badge"><svg class="icon" ...></svg></div>
    <div class="name">Energia</div>
  </div>
</div>
```

### Cabeçalho de seção
`pill` (etiqueta) + `h2` + `p.sub` (opcional). Reutilize sempre este padrão em seções novas.

```html
<div class="head center">
  <span class="pill pill-blue">Etiqueta</span>
  <h2>Título da seção</h2>
  <p class="sub">Subtítulo opcional</p>
</div>
```

---

## Regras (do / don't)

- ✅ Use as classes existentes (`.icon-badge`, `.market-card`, `.h-stat`, `.pill`, `.head`) — o design aplica sozinho.
- ✅ Cores sempre via token (`var(--ds-icon)`, `var(--ds-brand)`…).
- ❌ Não coloque hex/valores fixos de cor/efeito no HTML ou em `style=` — o lint barra.
- ❌ Não altere texto/seções pra "encaixar" no design — o design se adapta ao conteúdo, não o contrário.
- ❌ Não remova seções existentes.

---

## Como funciona: CSS vs Agente

São **duas camadas** com papéis diferentes. Entender isso é o que torna o sistema confiável:

| | O que é | Quando age | Garantia |
|---|---|---|---|
| **Camada 1 — CSS** (`design-system.css`) | Uma folha de estilo. **Não é agente.** | **Sempre**, ao carregar a página no navegador. Instantâneo. | **Determinística.** Todo conteúdo que usa as classes padrão já sai estilizado, sem ninguém rodar nada. É o "motor". |
| **Camada 2 — Agente** (GitHub Action) | Assistente de IA no CI. | **Automaticamente a cada Pull Request** (ver abaixo). | Assistida por IA (probabilística). É a "rede de segurança" que ajeita/sinaliza markup fora do padrão. |

Analogia: o **CSS é a fôrma** (todo bolo que cai nela sai no formato); o **agente é o confeiteiro** que, quando chega uma massa em formato errado, ajeita antes de assar — e avisa se faltou ingrediente.

> **Sem comando.** Ninguém precisa digitar `@claude` nem barra-comando. O agente dispara **pelo próprio evento do PR** (o workflow não define `trigger_phrase`). A única ação humana é o **merge** — que é governança, não comando pro agente.

---

## O agente (aplicação automática)

Roda no GitHub Actions **automaticamente a cada Pull Request** (`.github/workflows/design-system.yml`), sem comando humano. Papel:

1. **Garante** que `design-system.css` está linkado nas páginas.
2. **Aplica o design a conteúdo novo**: quando aparece markup novo, normaliza para as classes/padrões do design system (ex.: envelopa ícone em `.icon-badge`, aplica `.market-card`, troca hex por token).
3. **Nunca altera conteúdo**: não muda texto, não remove seções. Mudanças de conteúdo são só sinalizadas no PR.
4. **Roda o lint** (`.stylelintrc.json`) e comenta/sugere correções.

> É um **aplicador/revisor** (assistido por IA), não uma garantia absoluta. A proteção real vem do fluxo de PR + branch protection: conteúdo publicado só muda via PR revisado.

**Ativação (do lado de vocês — passar pela segurança/SGSI):**
1. Habilitar GitHub Actions no repo `4Asset-Technologies/specifor-site`.
2. Adicionar secret `ANTHROPIC_API_KEY` (Settings → Secrets → Actions).
3. Dar permissão de escrita/PR ao workflow (Settings → Actions → Workflow permissions).
4. Ativar branch protection na branch publicada (exigir PR + checks verdes antes do merge).
