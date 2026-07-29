# Site 4Asset — Marketing

Site institucional B2B da **4Asset Tecnologia S.A.** (Grupo Verante).
🌐 Ao vivo em: **https://4asset-technologies.github.io/4asset-website/**

---

## ✏️ Editar o site direto pelo GitHub (time de marketing)

Você **não precisa instalar nada** nem saber programar. Todas as edições são feitas no próprio site do GitHub, pelo navegador.

### Passo a passo

1. Abra o arquivo que quer mudar aqui no GitHub (quase sempre **`index.html`**).
2. Clique no ícone de **lápis** (✏️ *Edit this file*), no canto superior direito do arquivo.
3. Faça a alteração no texto.
4. Desça até o fim e clique em **Commit changes** (botão verde).
5. Pronto — em **~30 segundos** o site no ar já mostra a mudança.

> 💡 O mapa de "onde mora cada trecho" (headline, stats, CTAs, rodapé…) está no arquivo [`CLAUDE.md`](./CLAUDE.md), na tabela **Mapa do site**.

### Trocar uma imagem

1. Entre na pasta da imagem (ex.: raiz do repositório ou `clientes/`).
2. Clique em **Add file → Upload files** e suba a nova imagem **com o mesmo nome** da antiga (ela substitui direto).
3. Commit → site atualiza sozinho.

---

## 📚 Números e regras de conteúdo

Antes de editar textos, confira os números oficiais e termos banidos em [`CLAUDE.md`](./CLAUDE.md) (seções *Regras de conteúdo* e *Identidade visual*). Resumo:

- **77%** do mercado de transmissão · **64%** de geração · **400 mil** imóveis · **+20 anos**
- Clientes citados no site: **Vale**, **TAG**, **Echoenergia**
- Idioma: **PT-BR** sempre

---

## 🛠 Pro time técnico

### Estrutura

```
.
├── index.html              ← site principal (single-page, scroll snap)
├── privacidade.html        ← política LGPD
├── *.png, *.jpg, *.svg     ← assets de imagem
├── clientes/               ← logos de clientes
├── .devcontainer/          ← config do Codespace (Claude Code + Node + Python)
├── .claude/                ← slash commands e permissions
├── .vscode/                ← tasks (preview)
├── CLAUDE.md               ← contexto que o Claude carrega automaticamente
└── agente-claude/          ← documentação legacy do fluxo via claude.ai
```

### Hosting

- **GitHub Pages** (branch `main`, root)
- Build: nenhum (HTML estático puro)
- Deploy: automático a cada commit em `main`
- TTL: ~30 segundos pra propagar

### Rodar localmente

```bash
python -m http.server 8000
# abre http://localhost:8000
```

### Stack

HTML5 + CSS3 + JavaScript vanilla. Sem build, sem framework, sem dependência runtime. Compatibilidade alvo: Chrome/Edge/Safari/Firefox modernos.

---

## 📞 Contato

- Hercules — gestão técnica do site
- Time de marketing — autores das mudanças
