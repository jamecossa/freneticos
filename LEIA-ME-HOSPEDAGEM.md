# Website Efeitos Frenéticos – pacote para hospedagem

## O que está neste pacote
- `index.html` – a página (todo o conteúdo e textos)
- `css/style.css` – o aspecto do site
- `js/main.js` – slideshow, menus, filtros da galeria e formulário
- `img/` – logotipo, ícone do separador, fotos do slideshow e da galeria
- `.htaccess` – cabeçalhos de segurança para Apache/cPanel
- `_headers` – os mesmos cabeçalhos para Netlify e Cloudflare Pages
- `robots.txt`

## Como publicar
**Hospedagem com cPanel (a mais comum):**
1. Entre no cPanel > Gestor de Ficheiros > pasta `public_html`.
2. Carregue o ficheiro .zip e extraia-o.
3. Mova o conteúdo da pasta extraída para dentro de `public_html`, de modo que `index.html` fique directamente lá (inclua o `.htaccess`, que é um ficheiro escondido: active "Mostrar ficheiros escondidos").
4. Active o certificado SSL gratuito (Let's Encrypt/AutoSSL) e, depois de o site abrir com https, tire os `#` do redirecionamento e do HSTS no `.htaccess`.

**Netlify ou Cloudflare Pages:** arraste a pasta para o painel. O ficheiro `_headers` aplica a segurança automaticamente e o HTTPS é activado sozinho.

## Dados que pode alterar
- Telefone/WhatsApp (913 397 139): procurar `351913397139` em `index.html` e `js/main.js`.
- Facebook: procurar `efeitosfreneticosunip` em `index.html`.
- Textos: directamente em `index.html`.
- Fotos: substitua o ficheiro em `img/` mantendo o mesmo nome (formato JPG, até 1000 px de largura).

## Verificação de segurança feita
- Sem scripts, estilos ou imagens de outros sites: tudo vem do próprio site.
- Sem estilos nem eventos dentro das tags HTML, o que permite uma política de segurança (CSP) rigorosa.
- Sem `innerHTML`, `eval` ou `document.write`; o texto do formulário é limpo, limitado em tamanho e codificado antes de seguir para o WhatsApp.
- O formulário não envia dados para nenhum servidor: abre o WhatsApp da empresa. Não há base de dados, login nem PHP para atacar.
- Links externos com `noopener noreferrer`.
- Fotos sem metadados (sem GPS, data nem dados da câmara).
- Cabeçalhos: CSP, `X-Frame-Options`, `nosniff`, `Referrer-Policy`, `Permissions-Policy` e HSTS.

## O que o pacote não cobre (depende de si)
- Segurança total não existe: um site estático tem poucas hipóteses de ser atacado, mas a conta de hospedagem e o domínio são o ponto fraco. Use palavras-passe fortes e verificação em dois passos no painel e no registo do domínio.
- Mantenha cópia de segurança do pacote.
- O site mostra o NIF, a morada e o telefone da empresa. São dados já públicos, mas confirme que a empresa os quer exibir.
