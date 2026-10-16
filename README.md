# ImagineUP

Site público do ImagineUP, o app de fãs dos artistas da Imagine Music. O painel administrativo do app vai ser construído neste mesmo repositório.

## Site

HTML, CSS e JavaScript puros, sem etapa de build. Tudo fica na pasta `site/`:

| Endereço | Página |
| --- | --- |
| `/` | Página inicial |
| `/baixar/` | Download do app, com código QR |
| `/sobre/` | Sobre |
| `/novidades/` | Novidades |
| `/faq/` | Perguntas frequentes |
| `/contato/` | Fale conosco |
| `/privacidade/` | Política de Privacidade |
| `/termos/` | Termos de Uso |

Para abrir no computador, com o Node instalado:

```bash
npx serve site
```

Qualquer hospedagem de arquivos estáticos serve para publicar: basta apontar para a pasta `site/`. O código QR da página Baixar aponta para a própria página, então funciona em qualquer domínio.

Na Vercel, `site/vercel.json` faz cada página ter um endereço só (com barra no fim) e guarda em cache as fontes e as telas do app.

Os links que o app compartilha (`/post/...`, `/artista/...` e `/agenda`, todos com `?ref=CODIGO`) ainda não abrem o app: isso depende do domínio próprio e da versão das lojas. Até lá, o `site/vercel.json` manda esses endereços para a página Baixar, com o `?ref` junto, num redirecionamento temporário. A mesma regra já vale para `/fa-clube/...`, o link do fã-clube que ainda vai entrar no app. Com o código no endereço, a página Baixar mostra o código de convite, com o botão de copiar e a dica de digitar no cadastro, põe o código no QR (e o texto do QR passa a dizer isso) e não pula direto para a loja. O código só aparece no formato que o app aceita: de 3 a 64 letras, números ou `_`.

## Antes de publicar

- Os textos da Política de Privacidade e dos Termos de Uso passam pela revisão do jurídico da Imagine Music.
- Quando o app estiver nas lojas, preencher os links da App Store e do Google Play em `LOJAS`, no script de `site/baixar/index.html`, e nos links iOS e Android do rodapé de cada página. Com os links preenchidos, quem abre a página Baixar no celular vai direto para a loja certa.
