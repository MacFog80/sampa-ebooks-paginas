# Sampa Group • Páginas de vendas dos e-books (Edição 2026 • 2027)

Uma pasta por livro. Cada pasta é um site estático (sem build) publicado na Cloudflare Pages.

| Pasta | Livro | Subdomínio planejado |
|---|---|---|
| `protocolo-13-blindado/` | Protocolo 13º Blindado | protocolo.sampa.group |
| `operacao-caixa-recuperado/` | Operação Caixa Recuperado | caixa.sampa.group |
| `natal-dos-sonhos-sem-dividas/` | O Natal dos Sonhos sem Dívidas | natal.sampa.group |
| `vida-me-surpreenda-2027/` | Vida, Me Surpreenda em 2027 | vida2027.sampa.group |
| `o-reencontro/` | O Reencontro | reencontro.sampa.group |

Configuração na Cloudflare (cada livro = 1 projeto Pages, mesmo repositório):
- Framework preset: None
- Build command: (vazio)
- Build output directory: nome da pasta do livro

Os favicons já estão embutidos no `index.html`; os arquivos `favicon.svg`, `favicon-32.png` e `apple-touch-icon.png` ficam na pasta só para quem pedir o arquivo direto.

Preços, data da promoção e link de checkout ficam nas variáveis no fim de cada `index.html` (PRECO, PRECO_ANTIGO, PROMO_ATE, CHECKOUT_URL).
