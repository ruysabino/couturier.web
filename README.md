# Couturier v2.0 — PDF Merger Web App

> Inspirado no Couturier original de C. Emmanouilidis (2010)  
> Reescrito como aplicação web moderna, 100% client-side.

![Couturier Screenshot](https://github.com/ruysabino/couturier.web/blob/main/screenshot.png)

## ✨ Funcionalidades

- **Mesclar PDFs** — combine quantos arquivos quiser em um único documento
- **Adicionar imagens** — suporte a PNG, JPG, WEBP, TIFF, BMP convertidas para PDF
- **Reordenar arquivos** — arraste para reorganizar ou use os botões ↑↓
- **Criptografar** — proteja o PDF final com senha de usuário e proprietário
- **Orientação de página** — mantenha original, force retrato ou paisagem
- **100% client-side** — nenhum arquivo é enviado a servidores externos

## 🚀 Deploy no GitHub Pages

### Opção 1 — Repositório simples (mais fácil)

1. Crie um repositório no GitHub (ex: `couturier`)
2. Faça upload do `index.html` na raiz do repositório
3. Vá em **Settings → Pages**
4. Em **Source**, selecione **Deploy from a branch**
5. Branch: `main` / Folder: `/ (root)`
6. Clique em **Save**
7. Aguarde ~1 minuto e acesse: `https://seu-usuario.github.io/couturier/`

### Opção 2 — Via GitHub CLI

```bash
# Clone ou crie o repositório
git clone https://github.com/seu-usuario/couturier.git
cd couturier

# Copie o index.html
cp /caminho/para/index.html .

# Commit e push
git add index.html
git commit -m "feat: Couturier v2.0 web app"
git push origin main

# Ative o GitHub Pages nas configurações do repositório
```

### Opção 3 — GitHub Actions (deploy automático)

Crie o arquivo `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/configure-pages@v4
      - uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
      - id: deployment
        uses: actions/deploy-pages@v4
```

## 📂 Estrutura do projeto

```
couturier/
└── index.html          # Aplicação completa (self-contained)
└── README.md           # Este arquivo
└── .github/
    └── workflows/
        └── deploy.yml  # (opcional) CI/CD automático
```

## 🛠 Tecnologias

| Biblioteca | Versão | Uso |
|-----------|--------|-----|
| [pdf-lib](https://pdf-lib.js.org/) | 1.17.1 | Criação, mesclagem e criptografia de PDFs |
| [downloadjs](https://github.com/rndme/download) | 1.4.7 | Download do arquivo gerado |
| [DM Serif Display / DM Mono / DM Sans](https://fonts.google.com) | — | Tipografia |

Todas as dependências são carregadas via CDN — nenhum `npm install` necessário.

## 🔒 Privacidade

Todo o processamento ocorre **localmente no browser do usuário**.  
Nenhum arquivo PDF ou imagem é enviado a qualquer servidor.

## 📋 Formatos suportados

**Entrada:**
- PDF (`.pdf`)
- Imagens: PNG, JPG/JPEG, WEBP, TIFF/TIF, BMP

**Saída:**
- PDF (com ou sem criptografia)

## 🌐 Compatibilidade de browsers

| Browser | Suporte |
|---------|---------|
| Chrome 90+ | ✅ |
| Firefox 88+ | ✅ |
| Safari 14+ | ✅ |
| Edge 90+ | ✅ |

## 📜 Créditos

- **Couturier original**: Charalampos Emmanouilidis (2010) — [GitHub](https://github.com/cemmanouilidis/couturier)
- **pdf-lib**: Andrew Dillon — [pdf-lib.js.org](https://pdf-lib.js.org)
- **Redesign web v2.0**: gerado com Claude (Anthropic)

## 📄 Licença

MIT License — livre para usar, modificar e distribuir.
