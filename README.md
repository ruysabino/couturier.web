# Couturier Web — Mesclador de PDFs no navegador

> Reimplementação web independente, 100% client-side, de um utilitário de mesclagem de PDFs.
> Inspirada conceitualmente no projeto [Couturier](https://github.com/cemmanouilidis/couturier)
> de C. Emmanouilidis (2010) — **sem qualquer afiliação, código compartilhado ou endosso**.
> Não é uma continuação nem uma versão oficial daquele projeto.

![Couturier Web Screenshot](https://github.com/ruysabino/couturier.web/blob/main/screenshot.png)

## ✨ Funcionalidades

- **Mesclar PDFs** — combine quantos arquivos quiser em um único documento
- **Adicionar imagens** — PNG, JPG, WEBP, TIFF, BMP convertidas para PDF
- **Reordenar arquivos** — arraste para reorganizar ou use os botões ↑↓
- **Orientação de página** — mantenha original, force retrato ou paisagem
- **Criptografia AES-256** — proteja o PDF resultante com senha (requerida para abrir)
- **100% client-side** — nenhum arquivo é enviado a servidores externos
- **Fontes auto-hospedadas** — nenhuma requisição a servidores de fontes de terceiros
- **Multi-idioma** — interface em Português, English, Español, Français e Deutsch

## 🚀 Deploy no GitHub Pages

1. **Settings → Pages**
2. Em **Source**, selecione **Deploy from a branch**
3. Branch: `main` / Folder: `/ (root)` → **Save**
4. Acesse `https://seu-usuario.github.io/couturier.web/`

> Publique o repositório inteiro (não apenas `index.html`): a pasta `fonts/`
> precisa acompanhar a página para que a tipografia carregue localmente.

## 📂 Estrutura do projeto

```
couturier.web/
├── index.html              # Aplicação completa
├── fonts/                  # Fontes DM auto-hospedadas (.woff2) + OFL.txt
├── LICENSE                 # MIT (código deste projeto)
├── NOTICE                  # Atribuições de terceiros e nota de não afiliação
└── README.md
```

## 🛠 Tecnologias e licenças

| Componente | Versão | Licença | Uso |
|-----------|--------|---------|-----|
| [@cantoo/pdf-lib](https://github.com/Cantoo/pdf-lib) | 2.9.1 | MIT | Criação, mesclagem e criptografia AES-256 de PDFs (via CDN unpkg) |
| [downloadjs](https://github.com/rndme/download) | 1.4.7 | MIT | Download do arquivo gerado (via CDN unpkg) |
| [DM Sans / DM Serif Display / DM Mono](https://github.com/googlefonts/dm-fonts) | — | SIL OFL 1.1 | Tipografia (auto-hospedada em `fonts/`) |

Todas as licenças de terceiros são compatíveis com a MIT deste projeto.
Detalhes e textos de aviso em [`NOTICE`](NOTICE) e [`fonts/OFL.txt`](fonts/OFL.txt).

## 🔒 Privacidade

Todo o processamento ocorre **localmente no browser**. Nenhum PDF ou imagem é
enviado a qualquer servidor. As fontes são servidas pelo próprio site (sem
`fonts.googleapis.com` / `fonts.gstatic.com`), evitando transferência de IP dos
visitantes a terceiros — ponto relevante para conformidade com o RGPD/GDPR.
A biblioteca `@cantoo/pdf-lib` e `downloadjs` ainda são carregadas do CDN público
unpkg.com; para eliminar qualquer chamada externa, basta baixar os dois arquivos
`.js` para o repositório e ajustar os `<script src>` em `index.html`.

## 📋 Formatos suportados

**Entrada:** PDF, PNG, JPG/JPEG, WEBP, TIFF/TIF, BMP
**Saída:** PDF (com ou sem criptografia AES-256)

## 🌐 Compatibilidade

Chrome 90+ · Firefox 88+ · Safari 14+ · Edge 90+

## 📜 Créditos

- **Inspiração conceitual**: Couturier, de Charalampos Emmanouilidis (2010) — projeto sem licença publicada; nenhum código seu é usado ou redistribuído aqui
- **@cantoo/pdf-lib**: Cantoo / Andrew Dillon
- **downloadjs**: dandavis
- **Fontes DM**: The DM Fonts Project Authors
- **Desenvolvimento desta versão web**: Ruy Sabino Pereira, com auxílio de assistentes de IA

## 📄 Licença

[MIT](LICENSE) © 2026 Ruy Sabino Pereira. Consulte [`NOTICE`](NOTICE) para as
atribuições obrigatórias de componentes de terceiros.
