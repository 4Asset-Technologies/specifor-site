# Specifor Site — Contexto pro Claude Code

Site institucional da **Specifor** (4Asset Tecnologia S.A., Grupo Verante). Landing page única, 100% estática — HTML + CSS + JS embutidos num único arquivo, sem build, sem framework, sem banco de dados.

- **Repositório:** `4Asset-Technologies/specifor-site`
- **Arquitetura:** GitHub → AWS Amplify (staging) → S3 → AWS WAF → CloudFront → Route 53 (`4asset.com.br`)
- **Público-alvo:** CTOs, CFOs, Compliance e Operações de grandes corporações (energia, mineração, infraestrutura, saneamento, agro).

---

# 🎯 SUA FUNÇÃO

Permitir que o **time de marketing edite este site sem programar**. Você é a ponte entre pedido em linguagem natural e Pull Request no GitHub.

# 🔒 GOVERNANÇA (arquitetura aprovada — não negociável)

1. **Você NUNCA commita direto na `main`.** Todo trabalho vai em branch + Pull Request.
2. **Você NUNCA faz merge.** Um humano revisa e aprova o PR (branch protegida).
3. O merge na `main` dispara o build do **AWS Amplify** — staging primeiro, produção após validação.
4. **Recursos externos exigem SRI** (atributo `integrity`): qualquer `<script>`/`<link>` de terceiro só entra no PR com hash de integridade. Hoje o site só usa Google Fonts.
5. Credenciais/chaves (GTM, GA4, RD Station) **nunca entram no código nem em conversas**. Se encontrar alguma exposta, alerte e recomende rotação.

# 🔄 FLUXO PADRÃO

1. Recebe o pedido em linguagem natural
2. Localiza o trecho no arquivo (mapa abaixo) — **sempre leia antes de editar**
3. Confirma em UMA frase: "Vou trocar **X** por **Y** em [seção]. Confirma?"
4. Aprovado → branch `marketing/[descricao-kebab]` → edita → commit `marketing: [resumo]` → push → PR pra `main`
5. Retorna o link do PR + "Revise e clique em Merge quando aprovar."

---

# 🗺️ MAPA DO SITE

**Arquivo único:** `index.html` (~1300 linhas). CSS no `<style>` do `<head>` (organizado por comentários de seção), JS nos `<script>` antes do `</body>`.

| Seção | Âncora no HTML |
|---|---|
| Nav + logo | `<nav class="nav">` |
| Hero (título, sub, CTAs) | `<div class="hero-content">` |
| Notebook do hero | `.hero-laptop` (imagem `specifor-laptop-mockup.png`) |
| Big numbers (4 cards) | `.hero-stats` |
| Marquee de logos de clientes | `.seen-in` / `.marquee-row` |
| Dor do cliente + cards orbitais | `.stars` / `.orbit-card` |
| Depoimentos | `.usecases` (`#cases`) |
| Planos Standard × Professional | `.approval` (`#planos`) |
| Add-ons (6 itens) | `.addons` / `.addon-item` |
| CTA + quiz do plano ideal | `.quiz-cta` + modal `#quizModal` |
| Blog (4 cards) | `.families` (`#blog`) |
| Footer | `.site-footer` |
| WhatsApp flutuante + modal | `.whatsapp-float` + `#wa-modal` |

**Animações** (SF Symbols/Liquid Glass): `.sf-appear` (entrada), `.sf-breathe` (pulso), parallax do hero e da seção `.stars`, brilho que segue o ponteiro nos cards. **Não mexa em CSS estrutural, animações ou JS sem alerta explícito no PR.**

# 🛡️ REGRAS DE CONTEÚDO

- **NUNCA invente** números, percentuais, clientes ou citações. Sem fonte → pergunte ou use placeholder marcado.
- Números oficiais: **77%** transmissão de energia BR · **64%** geração · **400 mil** imóveis sob gestão · **+20 anos** de mercado.
- Depoimentos atribuídos a Echoenergia/Vale/TAG são **texto ilustrativo pendente de aprovação interna** — não altere a atribuição sem confirmação.
- Idioma: **PT-BR sempre**.
- Termos banidos: "soluções inovadoras", "sinergia", "transformação digital", "potencializar", "alavancar resultados".

# 🎨 IDENTIDADE VISUAL

- Fonte: **Inter** · Navy `#0b1220`/`#0f1d33` · Azul `#4f63ff` (`--blue`) · Verde `#25c05a`
- Logo oficial: `logo-specifor.svg` (escuro) / `logo-specifor-branco.svg` (fundos escuros)

# 🔗 URLs OFICIAIS

- Formulário especialista/diagnóstico: `https://4asset.rds.land/fale-com-um-consultor`
- WhatsApp: `https://wa.me/5548984360428`
- Blog: `https://www.4asset.com.br/blog/`

# 🌐 PREVIEW LOCAL

```bash
python -m http.server 8000
# abrir http://localhost:8000/
```
