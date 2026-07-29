# Site 4Asset — Instruções para o time de Marketing

Este pacote contém o site institucional da **4Asset** pronto para você navegar e ajustar **textos** e **fotos**. Nada precisa ser instalado — basta abrir o arquivo no navegador.

---

## 🚀 Como abrir o site

1. **Abrir no navegador:** dê duplo clique em `index.html`. Vai abrir no seu navegador padrão (Chrome/Edge recomendados).

2. **Política de Privacidade:** abra `privacidade.html` da mesma forma.

3. **Se algum recurso falhar no `file://`** (algumas versões de navegador bloqueiam), use um servidor local rápido:
   - Tendo o Python instalado, abra o Prompt na pasta e rode: `python -m http.server 8080`
   - Acesse: `http://localhost:8080/`

---

## 🗺️ Estrutura das dobras (ordem do scroll)

| # | Dobra | O que mostra |
|---|---|---|
| 1 | **Hero** | "A empresa por trás de 77% da transmissão de energia do Brasil." + foto profissionais |
| 2 | **Sobre** | "A 4Asset é a empresa especializada..." + foto trabalhador + 4 cards de estatística + carrossel de clientes no rodapé |
| 3 | **Setores** ("Quem busca a 4Asset.") | 6 segmentos em grid 3×2 (Energia, Parques, Construção, Telecom, Governo, Agronegócio) |
| 4 | **Pilares** ("Três pilares que definem como operamos.") | 3 pilares (Especialização, Integração, Rastreabilidade) |
| 5 | **Produtos** ("Dois produtos. Uma plataforma.") | 2 cards (Specifor SaaS + OnPremise) com **espaço para vídeo** no topo |
| 6 | **CTA "Não sabe qual solução..."** | Convite para entender diferenças |
| 7 | **Cases** ("Resultados que falam por si.") | 3 cases (Vale, Echoenergia, Axia) |
| 8 | **CTA Final** | "A 4Asset é a empresa certa para o seu projeto" |
| 9 | **Footer** | Newsletter, colunas Empresa/Produtos/Contato, marca-d'água SPECIFOR |

---

## ✏️ Como editar textos

Abra `index.html` no **VS Code**, **Sublime Text** ou até no **Bloco de Notas**.

### Buscar e substituir
Use `Ctrl+F` para localizar o texto que quer alterar. Cada dobra está marcada por um comentário grande no código, por exemplo:

```
<!-- ============================================================
     SEÇÃO PILARES — "Três pilares" (5ª dobra)
============================================================ -->
```

Edite o texto entre as tags HTML (`<h2>...</h2>`, `<p>...</p>`) e salve.

### Exemplos rápidos
- **Título do Hero:** procure "A empresa por trás de 77%" — está perto do início do arquivo
- **Subtítulo do Hero:** "Transformamos patrimônios complexos..."
- **Textos dos cards de Pilares:** procure por "Especialização setorial"
- **Textos dos cards de Produtos:** procure por "Implantação em 90 dias"

---

## 🖼️ Como trocar fotos

As imagens estão na **raiz da pasta** (mesmo nível do `index.html`):

| Arquivo | Onde aparece | Recomendação |
|---|---|---|
| `imagem 01.png` | Hero — homem e mulher com tablet | PNG com **fundo transparente** (recorte) |
| `imagem 02.png` | Sobre — homem de uniforme laranja | JPG/PNG, 800×600px ou similar |
| `card 01 e 06.jpg` | Cards "Energia" e "Agronegócio" | 800×500px |
| `card 02 e 04.png` | Cards "Parques Eólicos" e "Telecom" | 800×500px |
| `card 03 e 05.png` | Cards "Construção" e "Governo" | 800×500px |
| `bg002.png` | Fundo do Hero (mapa + degradê) | Não trocar (asset oficial) |
| `bg0032.png` | Brand mark gigante decorativo | Não trocar (asset oficial) |
| `4ASSET_BRAND-MARK-1-1.svg` | Logo do header | Não trocar |
| `WhatsApp-Logo.wine.svg` | Botão flutuante | Não trocar |

**Para trocar uma foto:** substitua o arquivo da pasta mantendo o **mesmo nome** e a mesma extensão. Recarregue a página.

### Logos dos clientes (carrossel)
Estão em `clientes/image 13.png` até `clientes/image 40.png` (28 logos). Mantenha o mesmo padrão (PNG com fundo transparente, logos em **branco/cinza claro** para combinar com o fundo escuro do carrossel).

### Fotos dos Cases (Vale, Echoenergia, Axia)
**Atualmente são placeholders** (reutilizamos imagens). Quando tiver as fotos reais, substitua os arquivos correspondentes (`card 01 e 06.jpg`, `card 02 e 04.png`, `card 03 e 05.png`) ou me passe os arquivos novos.

### Logos das empresas (V, E, A nos cards de Cases)
Hoje são marcas coloridas com a inicial. Se tiver os logos oficiais coloridos, me passa para substituir.

---

## 🎬 Vídeos dos produtos (placeholders)

A área de mídia no topo dos cards de **Produtos** está pronta para receber vídeo (sem áudio, autoplay, loop). Basta colocar os arquivos na pasta:

- **`specifor-saas.mp4`** → card SaaS (esquerda)
- **`specifor-onpremise.mp4`** → card OnPremise (direita)

Recomendado: vídeos curtos (10–30s), 1280×720 ou 1920×1080, sem áudio, looping natural.

---

## 🔗 Links importantes (já configurados)

- **Blog:** `https://www.4asset.com.br/blog/` (abre em nova aba)
- **WhatsApp:** `https://wa.me/5548984360428?text=...` (todos os botões de WhatsApp/conversa)
- **RD Station — Falar com especialista:** `https://4asset.rds.land/fale-com-um-consultor`

---

## ⚙️ Comportamentos do site

- **Scroll-snap fullpage:** cada dobra ocupa 1 tela inteira; a página "imanta" na próxima ao rolar.
- **Menu fixo:** o header acompanha o scroll e fica mais opaco quando você desce.
- **Animações de entrada:** os elementos da 2ª dobra surgem em fade quando você chega nela.
- **Esteira de clientes:** roda automaticamente em loop infinito no rodapé da 2ª dobra.
- **Luzes pulsando:** pequenos pontos azuis brilham no mapa do Hero (efeito de alertas).
- **Hero transition:** ao rolar, o texto e as pessoas dão zoom + blur (sai de cena com classe).

---

## 🆘 Precisa ajustar algo além do texto/imagem?

Para mudanças de estrutura, cores, animações, novas seções ou ajustes técnicos, fale com o dev responsável.

— Site gerado com Claude Code
