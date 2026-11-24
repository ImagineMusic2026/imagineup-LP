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

O `site/google9c4e0fd5f33df08f.html` prova ao Google Search Console que o endereço `https://imagineup-painel.vercel.app/` é da Imagine Music, e é por ele que o Play Console verifica o site da organização. Não apague nem mude esse arquivo: sem ele, a verificação cai. Como o arquivo tem extensão, a regra da barra no fim não o redireciona, e ele abre direto na raiz. Quando o site mudar para o domínio próprio, a verificação precisa ser refeita no Search Console e no Play Console.

Os links que o app compartilha (o do Convidar, `/?ref=CODIGO`, e os de `/post/...`, `/artista/...` e `/agenda`, também com `?ref=CODIGO`) ainda não abrem o app: isso depende do domínio próprio e da versão das lojas. Até lá, o `site/vercel.json` manda esses endereços para a página Baixar, com o `?ref` junto, num redirecionamento temporário. A página inicial só vai para a Baixar quando o endereço traz o `?ref`; sem ele, abre normalmente. A mesma regra já vale para `/fa-clube/...`, o link do fã-clube que ainda vai entrar no app. Com o código no endereço, a página Baixar mostra o código de convite, com o botão de copiar e a dica de digitar no cadastro, põe o código no QR (e o texto do QR passa a dizer isso) e não pula direto para a loja. O código só aparece no formato que o app aceita: de 3 a 64 letras, números ou `_`.

## Antes de publicar

- Os textos da Política de Privacidade e dos Termos de Uso passam pela revisão do jurídico da Imagine Music.
- Os links do Google Play e da App Store (https://apps.apple.com/br/app/imagineup/id6838384976, no ar desde 24/11/2026) estão em `LOJAS`, no script de `site/baixar/index.html`, nos links Android e iPhone do rodapé de cada página e nas páginas que citam as lojas (início, Sobre, Novidades, FAQ e Baixar). Quem abre a página Baixar no iPhone ou no Android vai direto para a loja, menos quando o endereço traz um código de convite.
- No iPhone não há o botão Continuar com Google. O FAQ (login com Google, Esqueci minha senha e exclusão) e as Novidades dizem como entra lá quem só entra com o Google no Android (quem criou a conta com o Google ou ficou sem a senha ao entrar com o Google pelo Gmail): criando uma senha pelo Esqueci minha senha. A seção 9 da Política ganhou o mesmo caminho para excluir a conta. A seção 2 da Política e a seção 3 dos Termos ainda não falam do iPhone e ficam para a revisão do jurídico.
- Os botões das lojas são só texto, sem ícone nem desenho de selo: como imagem, as regras de marca do Google Play e da Apple só aceitam o selo oficial (o do Google, baixado do Partner Marketing Hub e sujeito à revisão do Google). O rodapé de cada página e a página Baixar trazem a frase de marca do Google, que cobre Android, Google e Google Play, e a da Apple, na forma que a Apple pede fora dos EUA (Apple e iPhone como marcas comerciais registradas nos EUA e em outros países e regiões, e App Store como marca de serviço). A primeira menção do Android nas páginas que divulgam o app (início, Sobre, Novidades e Baixar) leva o ™, como pedem as regras de marca do Android.
- O site cita o Google, o Google Play e o Android só em texto simples e em links, usos que o Brand Resource Center do Google libera sem pedido. As páginas de marca do Android e do Google Play pedem a revisão de toda peça que cite as marcas: se o dono quiser essa revisão, ou antes de usar o selo, enviar as páginas pelo formulário de marca do Google (https://support.google.com/contact/partner_brand_approval), que costuma responder em uma semana ou mais.
