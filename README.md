# Specifor Site

Site institucional da Specifor (4Asset Tecnologia S.A. — Grupo Verante).

- **Stack:** HTML/CSS/JS estático, arquivo único (`index.html`), sem build.
- **Publicação:** Pull Request → revisão humana → merge na `main` → build AWS Amplify (staging → produção via S3 + WAF + CloudFront).
- **Edição:** o time de marketing edita via agente Claude, que abre PRs — nunca publica direto. Ver `CLAUDE.md`.

## Preview local

```bash
python -m http.server 8000
```

Abra `http://localhost:8000/`.
