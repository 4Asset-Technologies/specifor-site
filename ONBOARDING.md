# Bem-vindo(a) ao site Specifor 👋

Este é o guia rápido para **qualquer equipe da 4Asset editar o site institucional da Specifor sem precisar programar** — usando o Claude Code como ponte entre o pedido em português e a publicação.

O objetivo deste guia: você conseguir propor mudanças no site **sem risco de quebrar o que já está no ar**.

---

## 🌐 O que é este projeto

- **Site:** landing page institucional da Specifor (4Asset / Grupo Verante).
- **No ar:** https://4asset-technologies.github.io/specifor-site/
- **Repositório:** `4Asset-Technologies/specifor-site`
- **Como funciona:** é um site estático (um único arquivo `index.html` + imagens). Sem banco de dados, sem servidor. Isso é proposital — faz parte da arquitetura de segurança aprovada.

---

## 🔒 A regra de ouro: nada vai pro ar sem revisão

**O que está publicado (a branch `main`) é intocável diretamente.** Toda mudança segue este caminho:

1. Você descreve o ajuste em português para o Claude.
2. O Claude cria uma **branch** separada e abre um **Pull Request (PR)** no GitHub.
3. Uma pessoa responsável **revisa e aprova** o PR.
4. Só então a mudança é publicada — o site atualiza sozinho em ~1 minuto.

👉 Enquanto o PR não é aprovado, **o site no ar continua exatamente como está.** É impossível quebrar a versão publicada só por experimentar. Pode testar à vontade.

**O Claude nunca faz merge sozinho** e **nunca commita direto na `main`.** Sempre espera um humano aprovar.

---

## ✍️ Como pedir uma mudança

Fale naturalmente. Exemplos que funcionam:

- *"Troca o título do hero por 'Gestão territorial sem planilhas'."*
- *"Adiciona o logo da Neoenergia na faixa de clientes."*
- *"Muda o texto do primeiro depoimento para..."*
- *"Deixa o botão verde um pouco maior."*

O Claude vai:
1. Confirmar em uma frase o que entendeu.
2. Fazer a alteração.
3. Abrir o PR e te mandar o link.

Você revisa, e quando estiver ok, clica em **Merge** no GitHub.

---

## 🛡️ Regras de conteúdo (valem para todos)

- **Nunca inventar** números, percentuais, clientes ou citações. Sem fonte confirmada → o Claude pergunta ou marca como pendente.
- **Números oficiais:** 77% do mercado de transmissão de energia do Brasil · 64% de geração · 400 mil imóveis sob gestão · +20 anos de mercado.
- **Depoimentos** atribuídos a clientes reais (Echoenergia, TAG, BMTE) já foram aprovados. Não altere a atribuição sem confirmar com marketing.
- **Idioma:** sempre PT-BR.
- **Termos banidos** (jargão de venda): "soluções inovadoras", "sinergia", "transformação digital", "alavancar resultados". Evite.

---

## 🎨 Identidade visual

- **Fonte:** Inter
- **Cores:** Navy `#0b1220` / `#0f1d33` · Azul `#4f63ff` · Verde `#25c05a`
- **Logo oficial:** `logo-specifor.svg` (fundo claro) / `logo-specifor-branco.svg` (fundo escuro)
- **Logos de clientes:** ficam em `clientes-cor/` — sempre recortados (sem margem) e normalizados por altura na faixa.

Não mexa em CSS estrutural, animações ou JavaScript sem avisar no PR — peça ao Claude para sinalizar quando um pedido mexer nessas partes.

---

## 👀 Ver antes de publicar

Para ver o site rodando na sua máquina antes de abrir o PR, peça ao Claude para iniciar o preview, ou rode:

```bash
python -m http.server 8000
```

E abra `http://localhost:8000/`.

O Pull Request também gera uma pré-visualização que a pessoa que aprova pode conferir.

---

## 🗺️ Onde fica cada parte do site

Tudo em `index.html`. O mapa completo de seções (hero, faixa de clientes, depoimentos, planos, add-ons, quiz, blog, rodapé) está documentado em **`CLAUDE.md`** — o Claude lê esse arquivo automaticamente e sabe onde editar. Você não precisa decorar nada.

---

## ✅ Resumo em uma linha

**Descreva o ajuste → o Claude abre um PR → alguém aprova → o site atualiza.** O que está no ar nunca quebra, porque nada é publicado sem revisão humana.

Dúvidas? Fale com o time de marketing da 4Asset.
