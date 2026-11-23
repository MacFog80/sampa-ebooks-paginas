# Como publicar na Cloudflare Pages (5 livros, 1 repositório)

Pense no repositório como um prédio com 5 apartamentos: cada livro é um apartamento (pasta), e na Cloudflare cada um ganha sua própria porta (projeto + subdomínio).

## 1. Criar os 5 projetos (repita para cada livro)

1. Cloudflare → **Workers & Pages** → **Create** → aba **Pages** → **Connect to Git**.
2. Autorize o GitHub (perfil dos e-books) e escolha o repositório `sampa-ebooks-paginas`.
3. Preencha:

| Campo | Valor |
|---|---|
| Project name | ver tabela abaixo |
| Production branch | `main` |
| Framework preset | None |
| Build command | (deixe vazio) |
| Build output directory | pasta do livro |

4. **Save and Deploy**. Em ~1 minuto o site abre em `<project-name>.pages.dev`.

| Livro | Project name | Build output directory | Subdomínio |
|---|---|---|---|
| Protocolo 13º Blindado | `protocolo-13-blindado` | `protocolo-13-blindado` | protocolo.sampa.group |
| Operação Caixa Recuperado | `operacao-caixa-recuperado` | `operacao-caixa-recuperado` | caixa.sampa.group |
| O Natal dos Sonhos sem Dívidas | `natal-dos-sonhos` | `natal-dos-sonhos-sem-dividas` | natal.sampa.group |
| Vida, Me Surpreenda em 2027 | `vida-me-surpreenda-2027` | `vida-me-surpreenda-2027` | vida2027.sampa.group |
| O Reencontro | `o-reencontro` | `o-reencontro` | reencontro.sampa.group |

Dica: para que um projeto só republique quando a pasta dele mudar, em **Settings → Builds → Build watch paths** coloque `<pasta-do-livro>/*` em "Include paths".

## 2. Ligar o subdomínio

1. Abra o projeto → **Custom domains** → **Set up a custom domain**.
2. Digite o subdomínio (ex.: `protocolo.sampa.group`) → **Continue** → **Activate domain**.
3. Como o DNS do sampa.group já está na Cloudflare, o registro CNAME é criado sozinho. O certificado HTTPS fica pronto em poucos minutos.

O Email Routing do sampa.group não é afetado: ele usa registros MX/TXT do domínio raiz, e os subdomínios usam CNAME.

## 3. Depois de publicar

- Teste cada subdomínio no celular e clique no botão de compra.
- Na Hotmart, atualize a URL da página de vendas de cada produto para o novo subdomínio.
- Troque os links nas bios/posts (ex.: protocolo13blindado.netlify.app → protocolo.sampa.group). Mantenha o Netlify no ar alguns dias até a troca terminar.
- O script que sobe a barra fixa quando aparece o selo do Netlify não faz nada fora do Netlify; pode ficar.

## 4. Para atualizar uma página

Edite o `index.html` da pasta no GitHub (ou envie um commit) → a Cloudflare republica sozinha em ~1 minuto.

---
Conteúdo de caráter estritamente educacional; não constitui consultoria financeira ou recomendação de investimentos (CVM).
