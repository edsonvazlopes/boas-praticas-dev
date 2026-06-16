# Checklist de Fechamento SEO, Performance e Publicação de Sistema Web

> Use este checklist antes de considerar um site, sistema web, landing page ou aplicação institucional como pronto para publicação.
> A ideia é verificar **SEO técnico**, **metadata**, **performance**, **acessibilidade**, **segurança**, **conteúdo**, **indexação** e **qualidade de entrega**.

---

## 0. Identificação do projeto

- [ ] Nome do projeto definido.
- [ ] Domínio principal definido.
- [ ] Ambiente de produção definido.
- [ ] Ambiente de homologação/teste definido, se aplicável.
- [ ] Responsável técnico definido.
- [ ] Responsável pelo conteúdo definido.
- [ ] Data da revisão registrada.
- [ ] Versão/release registrado.

```txt
Projeto:
Domínio:
Repositório:
Ambiente de produção:
Responsável técnico:
Data da revisão:
Versão:
```

---

# 1. Domínio, HTTPS e canonicalização

## 1.1 Domínio principal

- [ ] O domínio principal está funcionando.
- [ ] Foi decidido se o site usará `www` ou sem `www`.
- [ ] A versão não escolhida redireciona para a versão principal.
- [ ] O domínio antigo, se existir, redireciona para o domínio novo.
- [ ] Não existem múltiplas versões públicas concorrendo entre si.

Exemplo de decisão:

```txt
Canonical do domínio:
https://www.exemplo.com.br
```

ou

```txt
Canonical do domínio:
https://exemplo.com.br
```

## 1.2 HTTPS

- [ ] O site abre corretamente em HTTPS.
- [ ] HTTP redireciona para HTTPS.
- [ ] O certificado SSL/TLS está válido.
- [ ] Não há aviso de conteúdo inseguro no navegador.
- [ ] Imagens, scripts, fontes e CSS também são carregados via HTTPS.

## 1.3 Redirecionamentos importantes

- [ ] `http://dominio.com` redireciona para HTTPS.
- [ ] `http://www.dominio.com` redireciona para HTTPS.
- [ ] A versão com `www` ou sem `www` está padronizada.
- [ ] URLs antigas relevantes possuem redirect 301 para URLs novas.
- [ ] Não há cadeia longa de redirects.
- [ ] Não há loop de redirects.

---

# 2. Arquivos essenciais na raiz ou equivalentes no framework

## 2.1 Arquivos públicos básicos

- [ ] `robots.txt` criado.
- [ ] `sitemap.xml` criado.
- [ ] Página 404 personalizada criada.
- [ ] Favicon configurado.
- [ ] Ícones para dispositivos configurados.
- [ ] Imagem padrão de compartilhamento configurada.
- [ ] Manifest configurado, se o projeto justificar.
- [ ] Política de privacidade publicada.
- [ ] Termos de uso publicados, se houver cadastro, login, venda, assinatura ou área restrita.

## 2.2 Em projetos tradicionais

Verificar se existem:

```txt
/public/robots.txt
/public/sitemap.xml
/public/favicon.ico
/public/404.html
/public/manifest.webmanifest
```

## 2.3 Em Next.js App Router

Verificar se existem, quando aplicável:

```txt
app/robots.ts
app/sitemap.ts
app/not-found.tsx
app/icon.png
app/apple-icon.png
app/opengraph-image.png
app/twitter-image.png
app/manifest.ts
```

---

# 3. `robots.txt`

## 3.1 Regras básicas

- [ ] O arquivo `robots.txt` está acessível em `/robots.txt`.
- [ ] O arquivo não bloqueia páginas importantes.
- [ ] O arquivo aponta para o sitemap.
- [ ] Áreas administrativas são bloqueadas quando necessário.
- [ ] Páginas que devem ser removidas do Google usam `noindex`, não apenas bloqueio por `robots.txt`.

Exemplo básico:

```txt
User-agent: *
Allow: /

Sitemap: https://www.exemplo.com.br/sitemap.xml
```

Exemplo com área administrativa:

```txt
User-agent: *
Allow: /
Disallow: /admin/
Disallow: /dashboard/
Disallow: /api/

Sitemap: https://www.exemplo.com.br/sitemap.xml
```

## 3.2 Atenção

- [ ] Não usar `robots.txt` como mecanismo de segurança.
- [ ] Não colocar URLs sensíveis achando que isso as protege.
- [ ] Não bloquear CSS, JS ou imagens necessários para o Google renderizar a página.
- [ ] Testar se o `robots.txt` não está impedindo indexação do site inteiro.

---

# 4. `sitemap.xml`

## 4.1 Conteúdo

- [ ] O sitemap contém as páginas públicas importantes.
- [ ] O sitemap não contém páginas privadas.
- [ ] O sitemap não contém páginas de teste.
- [ ] O sitemap não contém páginas com erro 404.
- [ ] O sitemap não contém URLs redirecionadas.
- [ ] O sitemap usa URLs absolutas.
- [ ] O sitemap usa o domínio canônico correto.
- [ ] O sitemap está acessível em `/sitemap.xml`.

Exemplo:

```xml
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://www.exemplo.com.br/</loc>
    <lastmod>2026-05-31</lastmod>
  </url>
  <url>
    <loc>https://www.exemplo.com.br/sobre</loc>
    <lastmod>2026-05-31</lastmod>
  </url>
</urlset>
```

## 4.2 Submissão

- [ ] Sitemap enviado ao Google Search Console.
- [ ] Sitemap enviado ao Bing Webmaster Tools, se aplicável.
- [ ] Sitemap referenciado no `robots.txt`.
- [ ] Sitemap validado após publicação.

---

# 5. Página 404

## 5.1 Conteúdo mínimo

- [ ] Página 404 personalizada criada.
- [ ] A página explica que o conteúdo não foi encontrado.
- [ ] A página possui link para a home.
- [ ] A página possui link para áreas importantes.
- [ ] A página mantém identidade visual do site.
- [ ] A página retorna status HTTP 404 real.
- [ ] A página não redireciona automaticamente para a home.

## 5.2 Sugestão de estrutura

```txt
Título: Página não encontrada
Texto: O endereço pode ter mudado ou não existir mais.
Ações:
- Voltar para a página inicial
- Ver principais conteúdos
- Entrar em contato
```

---

# 6. Metadata essencial por página

Cada página pública importante precisa ter metadata própria.

## 6.1 Title

- [ ] Cada página tem `<title>` único.
- [ ] O título descreve claramente a página.
- [ ] O título contém a palavra-chave principal quando fizer sentido.
- [ ] O título não é genérico.
- [ ] O título não é excessivamente longo.
- [ ] O nome da marca aparece quando fizer sentido.

Exemplo:

```html
<title>Sobre Dhinho Vaz | Música, Tecnologia e Criação</title>
```

## 6.2 Meta description

- [ ] Cada página tem `meta description` única.
- [ ] A descrição resume bem o conteúdo.
- [ ] A descrição incentiva o clique sem sensacionalismo.
- [ ] A descrição usa linguagem natural.
- [ ] A descrição não é duplicada em todas as páginas.

Exemplo:

```html
<meta name="description" content="Conheça a trajetória de Dhinho Vaz, artista, músico e criador que une música, tecnologia e experimentação sonora.">
```

## 6.3 Viewport

- [ ] O viewport está configurado.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

## 6.4 Canonical

- [ ] Cada página possui canonical correta.
- [ ] A canonical aponta para a própria URL principal.
- [ ] Não aponta para ambiente de teste.
- [ ] Não aponta para domínio antigo.
- [ ] Não aponta para URL com parâmetros desnecessários.

Exemplo:

```html
<link rel="canonical" href="https://www.exemplo.com.br/sobre">
```

## 6.5 Robots por página

- [ ] Páginas públicas importantes usam `index, follow`.
- [ ] Páginas privadas, duplicadas ou irrelevantes usam `noindex` quando necessário.
- [ ] Páginas de login, painel e administração não são indexáveis.
- [ ] Ambientes de homologação não são indexáveis.

Exemplo:

```html
<meta name="robots" content="index, follow">
```

Exemplo para página que não deve aparecer no Google:

```html
<meta name="robots" content="noindex, nofollow">
```

---

# 7. Open Graph

Open Graph melhora a aparência do link quando compartilhado em redes sociais, WhatsApp, LinkedIn, Facebook, Discord e outros ambientes.

## 7.1 Tags essenciais

- [ ] `og:title` configurado.
- [ ] `og:description` configurado.
- [ ] `og:image` configurado.
- [ ] `og:url` configurado.
- [ ] `og:type` configurado.
- [ ] `og:site_name` configurado, se aplicável.
- [ ] `og:locale` configurado, se aplicável.

Exemplo:

```html
<meta property="og:title" content="Dhinho Vaz | Música, Tecnologia e Criação">
<meta property="og:description" content="Site oficial de Dhinho Vaz: músicas, projetos, agenda, bastidores e contato profissional.">
<meta property="og:image" content="https://www.exemplo.com.br/og-image.jpg">
<meta property="og:url" content="https://www.exemplo.com.br">
<meta property="og:type" content="website">
<meta property="og:site_name" content="Dhinho Vaz">
<meta property="og:locale" content="pt_BR">
```

## 7.2 Imagem Open Graph

- [ ] Existe imagem específica para compartilhamento.
- [ ] A imagem tem boa leitura em miniatura.
- [ ] A imagem tem identidade visual do projeto.
- [ ] A imagem usa URL absoluta.
- [ ] A imagem está acessível publicamente.
- [ ] A imagem não é pesada demais.
- [ ] A imagem não depende de autenticação.

Sugestão comum:

```txt
1200 x 630 px
Formato: JPG, PNG ou WebP
```

---

# 8. Twitter/X Cards

## 8.1 Tags essenciais

- [ ] `twitter:card` configurado.
- [ ] `twitter:title` configurado.
- [ ] `twitter:description` configurado.
- [ ] `twitter:image` configurado.

Exemplo:

```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Dhinho Vaz | Música, Tecnologia e Criação">
<meta name="twitter:description" content="Músicas, projetos, agenda, bastidores e contato profissional.">
<meta name="twitter:image" content="https://www.exemplo.com.br/twitter-image.jpg">
```

---

# 9. Dados estruturados / Schema JSON-LD

## 9.1 Verificações gerais

- [ ] Existe JSON-LD quando fizer sentido.
- [ ] O JSON-LD está válido.
- [ ] As informações são verdadeiras.
- [ ] O Schema corresponde ao conteúdo real da página.
- [ ] O Schema não inventa avaliação, preço, autor, evento ou produto.
- [ ] O Schema foi validado no Rich Results Test.

## 9.2 Tipos comuns de Schema

- [ ] `WebSite` para o site principal.
- [ ] `WebPage` para páginas institucionais.
- [ ] `Person` para site pessoal/profissional/artístico.
- [ ] `Organization` para empresas, marcas, instituições ou projetos.
- [ ] `Article` para posts, notícias, textos e artigos.
- [ ] `FAQPage` para páginas de perguntas frequentes.
- [ ] `BreadcrumbList` para estrutura de navegação.
- [ ] `Product` para produtos.
- [ ] `Event` para eventos.
- [ ] `LocalBusiness` para negócios locais.
- [ ] `MusicGroup`, `MusicAlbum` ou `MusicRecording` para projetos musicais, quando aplicável.

## 9.3 Exemplo: WebSite

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "name": "Nome do Site",
  "url": "https://www.exemplo.com.br"
}
</script>
```

## 9.4 Exemplo: Person

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Nome da Pessoa",
  "url": "https://www.exemplo.com.br",
  "sameAs": [
    "https://www.instagram.com/perfil",
    "https://www.youtube.com/@canal",
    "https://open.spotify.com/artist/id"
  ]
}
</script>
```

## 9.5 Exemplo: FAQPage

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Qual serviço é oferecido?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Oferecemos informações, atendimento e serviços relacionados ao projeto."
      }
    }
  ]
}
</script>
```

---

# 10. Estrutura semântica do HTML

## 10.1 Elementos principais

- [ ] A página usa `<header>`.
- [ ] A página usa `<nav>`.
- [ ] A página usa `<main>`.
- [ ] A página usa `<section>` quando necessário.
- [ ] A página usa `<article>` para conteúdo independente.
- [ ] A página usa `<footer>`.
- [ ] Evita excesso de `<div>` sem necessidade semântica.
- [ ] Elementos interativos são botões ou links reais, não apenas `div` clicável.

## 10.2 Headings

- [ ] Existe um único `h1` principal por página.
- [ ] O `h1` descreve claramente a página.
- [ ] `h2` divide as seções principais.
- [ ] `h3` subdivide seções quando necessário.
- [ ] Não há salto ilógico de hierarquia.
- [ ] Headings não são usados apenas por aparência visual.

Exemplo:

```html
<main>
  <h1>Serviços de Produção Musical</h1>

  <section>
    <h2>Mixagem</h2>
    <p>...</p>
  </section>

  <section>
    <h2>Masterização</h2>
    <p>...</p>
  </section>
</main>
```

---

# 11. URLs amigáveis

## 11.1 Regras

- [ ] URLs são curtas.
- [ ] URLs são legíveis.
- [ ] URLs usam palavras reais.
- [ ] URLs evitam códigos desnecessários.
- [ ] URLs evitam parâmetros quando não são necessários.
- [ ] URLs usam hífen para separar palavras.
- [ ] URLs seguem hierarquia lógica.
- [ ] URLs antigas redirecionam para as novas.

Ruim:

```txt
/prod?id=123&cat=5
/page.php?x=abc
```

Bom:

```txt
/produtos/tenis-nike-air-max
/sobre
/contato
/blog/como-publicar-site
```

---

# 12. Conteúdo e intenção de busca

## 12.1 Conteúdo mínimo por página importante

- [ ] A página responde claramente a uma intenção.
- [ ] O conteúdo é original.
- [ ] O conteúdo é útil para o usuário.
- [ ] O conteúdo não é apenas decorativo.
- [ ] O conteúdo principal não está escondido atrás de imagem.
- [ ] O conteúdo principal não depende exclusivamente de JavaScript.
- [ ] A página tem início claro, desenvolvimento e chamada de ação.
- [ ] A página possui links internos úteis.
- [ ] A página evita texto genérico como “em breve”, “lorem ipsum” ou “clique aqui” sem contexto.

## 12.2 Palavras-chave

- [ ] Cada página tem uma intenção principal.
- [ ] Cada página tem uma palavra-chave ou tema principal.
- [ ] A palavra-chave aparece naturalmente no título.
- [ ] A palavra-chave aparece naturalmente no `h1`.
- [ ] A palavra-chave aparece naturalmente no texto.
- [ ] Sinônimos e variações são usados naturalmente.
- [ ] Não há repetição artificial de palavras-chave.
- [ ] Páginas diferentes não competem pela mesma palavra-chave sem necessidade.

## 12.3 Conteúdo duplicado

- [ ] Não há páginas públicas com conteúdo praticamente igual.
- [ ] Páginas duplicadas usam canonical quando necessário.
- [ ] Páginas de filtros ou parâmetros não geram indexação indevida.
- [ ] Conteúdo copiado de terceiros não é usado como base principal.

---

# 13. Linkagem interna

## 13.1 Navegação

- [ ] Menu principal contém páginas importantes.
- [ ] Rodapé contém links importantes.
- [ ] Breadcrumbs existem em sites com hierarquia mais profunda.
- [ ] Nenhuma página importante fica órfã.
- [ ] Links internos usam textos descritivos.
- [ ] Evita-se texto genérico como “clique aqui” sem contexto.

Exemplo ruim:

```html
<a href="/servicos">Clique aqui</a>
```

Exemplo melhor:

```html
<a href="/servicos">Conheça nossos serviços de produção musical</a>
```

## 13.2 Links quebrados

- [ ] Links internos testados.
- [ ] Links externos testados.
- [ ] Imagens quebradas corrigidas.
- [ ] Botões com link vazio corrigidos.
- [ ] Links antigos redirecionados.

---

# 14. Imagens

## 14.1 Otimização

- [ ] Imagens foram comprimidas.
- [ ] Imagens estão no tamanho adequado.
- [ ] Imagens não foram enviadas em resolução absurda sem necessidade.
- [ ] Imagens usam formatos modernos quando possível.
- [ ] Imagens importantes possuem `alt`.
- [ ] Imagens decorativas usam `alt=""`.
- [ ] Imagens possuem `width` e `height`.
- [ ] Imagens abaixo da primeira dobra usam lazy loading.
- [ ] Imagem principal da primeira dobra não usa lazy loading indevido.
- [ ] Nome dos arquivos é descritivo.

Exemplo:

```html
<img
  src="/imagens/dhinho-vaz-show-acustico.webp"
  alt="Dhinho Vaz cantando em apresentação acústica"
  width="1200"
  height="800"
  loading="lazy"
/>
```

## 14.2 Imagens sociais

- [ ] Imagem Open Graph criada.
- [ ] Imagem Twitter Card criada.
- [ ] Imagem de favicon criada.
- [ ] Ícone para mobile criado.
- [ ] Imagens não estão bloqueadas por autenticação.

---

# 15. Performance

## 15.1 Core Web Vitals

- [ ] LCP verificado.
- [ ] INP verificado.
- [ ] CLS verificado.
- [ ] Página principal testada.
- [ ] Páginas internas importantes testadas.
- [ ] Teste feito em modo mobile.
- [ ] Teste feito em modo desktop.

## 15.2 LCP

- [ ] Imagem principal otimizada.
- [ ] Hero não carrega imagem pesada demais.
- [ ] Fonte principal não atrasa renderização.
- [ ] Servidor/CDN responde rapidamente.
- [ ] Conteúdo principal aparece rápido.

## 15.3 INP

- [ ] JavaScript desnecessário removido.
- [ ] Componentes client-side reduzidos.
- [ ] Eventos de clique não executam tarefas pesadas.
- [ ] Bibliotecas pesadas foram avaliadas.
- [ ] Scripts de terceiros foram reduzidos.

## 15.4 CLS

- [ ] Imagens têm dimensões definidas.
- [ ] Banners não empurram conteúdo inesperadamente.
- [ ] Fontes não causam grande mudança visual.
- [ ] Espaços de embeds são reservados.
- [ ] Componentes carregados dinamicamente não quebram layout.

## 15.5 CSS

- [ ] CSS não usado removido.
- [ ] CSS está minificado em produção.
- [ ] Não há bibliotecas visuais gigantes sem necessidade.
- [ ] CSS crítico aparece rapidamente.
- [ ] Página não depende de JavaScript para receber estilo essencial.

## 15.6 JavaScript

- [ ] JavaScript está minificado em produção.
- [ ] Scripts não essenciais usam `defer` ou `async`.
- [ ] Scripts externos foram avaliados.
- [ ] Analytics não bloqueia a renderização.
- [ ] Widgets externos foram evitados ou adiados.
- [ ] Não há console.log em produção.
- [ ] Não há código morto evidente.

## 15.7 Fontes

- [ ] Fontes usadas são realmente necessárias.
- [ ] Número de famílias de fonte é baixo.
- [ ] Pesos não usados foram removidos.
- [ ] Fontes externas foram avaliadas.
- [ ] Fallback de fonte está definido.
- [ ] Não há carregamento de fonte que cause grande atraso visual.

---

# 16. Responsividade e mobile-first

## 16.1 Layout

- [ ] Site funciona bem em celular.
- [ ] Site funciona bem em tablet.
- [ ] Site funciona bem em desktop.
- [ ] Menu mobile funciona.
- [ ] Botões são fáceis de tocar.
- [ ] Textos têm tamanho confortável.
- [ ] Cards não estouram a tela.
- [ ] Tabelas são responsivas.
- [ ] Imagens não causam rolagem horizontal.
- [ ] Não existe overflow horizontal indesejado.

## 16.2 Conteúdo mobile

- [ ] Conteúdo importante aparece também no mobile.
- [ ] Metadata é a mesma no mobile e no desktop.
- [ ] Dados estruturados existem também na versão mobile.
- [ ] Imagens e vídeos são acessíveis no mobile.
- [ ] Formulários funcionam no mobile.

---

# 17. Acessibilidade

## 17.1 HTML e navegação

- [ ] Página navegável por teclado.
- [ ] Foco visível nos elementos interativos.
- [ ] Links têm texto compreensível.
- [ ] Botões são botões reais.
- [ ] Campos de formulário possuem label.
- [ ] Imagens possuem `alt` adequado.
- [ ] Ícones clicáveis possuem nome acessível.
- [ ] Landmarks semânticos estão corretos.
- [ ] Não há armadilha de foco em modal/menu.

## 17.2 Visual

- [ ] Contraste de texto adequado.
- [ ] Texto não depende apenas de cor.
- [ ] Tamanho de fonte confortável.
- [ ] Espaçamento adequado em mobile.
- [ ] Animações não são excessivas.
- [ ] Preferências de movimento reduzido são respeitadas, quando aplicável.

Exemplo CSS:

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms;
    animation-iteration-count: 1;
    scroll-behavior: auto;
    transition-duration: 0.01ms;
  }
}
```

## 17.3 Formulários

- [ ] Inputs possuem label visível ou acessível.
- [ ] Erros são claros.
- [ ] Mensagens de erro não dependem apenas de cor.
- [ ] Campos obrigatórios são indicados.
- [ ] Autocomplete configurado quando útil.
- [ ] Formulário funciona no mobile.
- [ ] Estado de envio é indicado.
- [ ] Sucesso ou falha são comunicados claramente.

---

# 18. Segurança básica

## 18.1 Exposição de dados

- [ ] `.env` não está versionado.
- [ ] Chaves, tokens e senhas não estão no repositório.
- [ ] Logs não expõem senha, token ou dados pessoais.
- [ ] Erros em produção não exibem stack trace sensível.
- [ ] Dados privados não aparecem no HTML público.
- [ ] Dados privados não aparecem no JavaScript enviado ao cliente.

## 18.2 Headers e proteção

- [ ] HTTPS ativo.
- [ ] Redirecionamento para HTTPS.
- [ ] Cookies sensíveis usam `HttpOnly`.
- [ ] Cookies sensíveis usam `Secure`.
- [ ] Cookies sensíveis usam `SameSite`.
- [ ] CORS configurado sem permissividade desnecessária.
- [ ] Uploads, se existirem, possuem validação.
- [ ] APIs privadas exigem autenticação.
- [ ] Rotas administrativas exigem autorização.
- [ ] Rate limit configurado onde fizer sentido.

## 18.3 Páginas e ambientes

- [ ] Ambiente de teste não está indexável.
- [ ] Ambiente de teste não usa dados reais sem necessidade.
- [ ] Painel administrativo não está indexável.
- [ ] Rotas internas não aparecem no sitemap.
- [ ] Backups não estão acessíveis publicamente.

---

# 19. Privacidade, LGPD e confiança

## 19.1 Páginas legais

- [ ] Política de privacidade publicada.
- [ ] Termos de uso publicados, se aplicável.
- [ ] Informações de contato disponíveis.
- [ ] Informações sobre cookies, se aplicável.
- [ ] Informações sobre analytics, se aplicável.
- [ ] Informações sobre formulários e tratamento de dados, se aplicável.

## 19.2 Coleta de dados

- [ ] Coleta apenas dados necessários.
- [ ] Formulários explicam finalidade.
- [ ] Dados sensíveis são evitados quando não necessários.
- [ ] Consentimento é tratado quando necessário.
- [ ] Existe forma de contato para solicitações relacionadas a dados.

---

# 20. Formulários e conversão

## 20.1 Formulários

- [ ] Formulários enviam corretamente.
- [ ] Validação client-side implementada.
- [ ] Validação server-side implementada.
- [ ] Mensagem de sucesso clara.
- [ ] Mensagem de erro clara.
- [ ] Proteção contra spam avaliada.
- [ ] Campos obrigatórios indicados.
- [ ] E-mail de confirmação configurado, se aplicável.
- [ ] Logs de erro existem sem expor dados sensíveis.

## 20.2 Chamadas para ação

- [ ] Página principal tem chamada para ação clara.
- [ ] Botões principais são visíveis.
- [ ] Contato é fácil de encontrar.
- [ ] Links para redes ou canais externos funcionam.
- [ ] WhatsApp, e-mail ou formulário estão corretos.
- [ ] Não há excesso de CTAs concorrendo entre si.

---

# 21. SEO local, quando aplicável

Use esta seção se o projeto depende de região, endereço, atendimento local, loja física, escola, clínica, escritório, evento presencial ou serviço local.

- [ ] Nome, endereço e contato estão consistentes.
- [ ] Página menciona cidade/região de atuação.
- [ ] Google Business Profile configurado, se aplicável.
- [ ] Links para mapas configurados, se aplicável.
- [ ] Horário de atendimento informado, se aplicável.
- [ ] Schema `LocalBusiness` avaliado.
- [ ] Avaliações e reputação local avaliadas.
- [ ] Páginas locais não usam texto artificial ou duplicado.

---

# 22. E-commerce, produto ou pagamento, quando aplicável

- [ ] Páginas de produto têm title específico.
- [ ] Páginas de produto têm description específica.
- [ ] Produto tem imagem otimizada.
- [ ] Produto tem descrição real.
- [ ] Preço está correto.
- [ ] Disponibilidade está clara.
- [ ] Frete/prazo está claro.
- [ ] Política de troca/devolução publicada.
- [ ] Checkout funciona.
- [ ] Página de sucesso funciona.
- [ ] Página de erro no pagamento funciona.
- [ ] Schema `Product` avaliado.
- [ ] Schema `Offer` avaliado.
- [ ] Produtos indisponíveis são tratados corretamente.

---

# 23. Blog, notícias ou artigos, quando aplicável

- [ ] Cada artigo tem URL amigável.
- [ ] Cada artigo tem title único.
- [ ] Cada artigo tem description única.
- [ ] Cada artigo tem data de publicação.
- [ ] Cada artigo tem autor.
- [ ] Cada artigo tem imagem principal.
- [ ] Cada artigo tem Open Graph próprio.
- [ ] Cada artigo tem Schema `Article`.
- [ ] Artigos relacionados são linkados.
- [ ] Categorias e tags não geram páginas duplicadas inúteis.
- [ ] Conteúdo antigo importante é atualizado.

---

# 24. Música, artista, portfólio ou site pessoal, quando aplicável

- [ ] Página “Sobre” com biografia curta, média ou completa.
- [ ] Página de contato profissional.
- [ ] Links para plataformas oficiais.
- [ ] Links para redes sociais oficiais.
- [ ] Release ou apresentação institucional.
- [ ] Página de músicas/projetos.
- [ ] Página individual para músicas importantes.
- [ ] Capa/imagem de cada música otimizada.
- [ ] Letra, ficha técnica ou descrição disponíveis quando fizer sentido.
- [ ] Schema `Person`, `MusicGroup`, `MusicRecording` ou similar avaliado.
- [ ] Imagem OG com boa identidade visual.
- [ ] Nome artístico consistente em todo o site.
- [ ] Dados de contato para shows, parcerias ou imprensa.

---

# 25. Build, ambiente e deploy

## 25.1 Antes do build

- [ ] Dependências instaladas corretamente.
- [ ] Arquivo `.env.example` atualizado.
- [ ] `.env` real não está versionado.
- [ ] Variáveis de produção configuradas.
- [ ] Variáveis de teste separadas.
- [ ] URLs de API apontam para produção.
- [ ] Ambiente de staging não aponta para produção por engano.
- [ ] Banco de dados correto configurado.

## 25.2 Build

- [ ] Build roda sem erro.
- [ ] TypeScript passa sem erro, se aplicável.
- [ ] Lint passa ou pendências foram justificadas.
- [ ] Testes passam, se existirem.
- [ ] Não há warnings graves ignorados.
- [ ] Bundle analisado, se o projeto for pesado.
- [ ] Arquivos finais foram gerados corretamente.

Comandos comuns:

```bash
npm install
npm run lint
npm run test
npm run build
npm run start
```

## 25.3 Deploy

- [ ] Deploy publicado no ambiente correto.
- [ ] Variáveis de ambiente configuradas no provedor.
- [ ] Logs de deploy verificados.
- [ ] Site abre após publicação.
- [ ] Rotas internas funcionam após refresh.
- [ ] Formulários funcionam em produção.
- [ ] APIs funcionam em produção.
- [ ] Banco de dados de produção funciona.
- [ ] Uploads, se existirem, funcionam.
- [ ] E-mails transacionais funcionam, se existirem.

---

# 26. Banco de dados, autenticação e sistema, quando aplicável

## 26.1 Banco de dados

- [ ] Migrations aplicadas.
- [ ] Seed inicial revisado.
- [ ] Dados de teste removidos da produção.
- [ ] Backup configurado.
- [ ] Restauração testada ou documentada.
- [ ] Permissões do banco revisadas.
- [ ] Conexão usa variáveis de ambiente.
- [ ] Logs não expõem dados sensíveis.

## 26.2 Autenticação

- [ ] Login funciona.
- [ ] Logout funciona.
- [ ] Recuperação de senha funciona, se existir.
- [ ] Confirmação de e-mail funciona, se existir.
- [ ] Sessão expira corretamente.
- [ ] Rotas protegidas exigem login.
- [ ] Usuário sem permissão não acessa área restrita.
- [ ] Mensagens de erro não revelam informação sensível.
- [ ] Senhas são armazenadas com hash adequado, quando aplicável.

## 26.3 Autorização

- [ ] Perfis de usuário foram testados.
- [ ] Usuário comum não acessa painel admin.
- [ ] Admin acessa o que precisa.
- [ ] Professor/gestor/cliente acessa apenas o que deve, se aplicável.
- [ ] APIs validam autorização no servidor.
- [ ] UI não é a única barreira de segurança.

---

# 27. E-mail, notificações e integrações

- [ ] SMTP ou serviço de e-mail configurado.
- [ ] Remetente correto configurado.
- [ ] E-mail não cai imediatamente em spam nos testes básicos.
- [ ] Templates revisados.
- [ ] Links dos e-mails apontam para produção.
- [ ] E-mails não vazam tokens em logs.
- [ ] Webhooks configurados, se existirem.
- [ ] Integrações externas testadas.
- [ ] Chaves de API estão em variáveis de ambiente.
- [ ] Integrações têm tratamento de erro.

---

# 28. Analytics e monitoramento

## 28.1 Analytics

- [ ] Ferramenta de analytics escolhida.
- [ ] Script de analytics instalado sem bloquear renderização.
- [ ] Eventos importantes configurados.
- [ ] Conversões configuradas, se aplicável.
- [ ] Analytics respeita política de privacidade.
- [ ] Ambiente de teste não polui dados de produção.

Ferramentas possíveis:

```txt
Google Analytics
Plausible
Cloudflare Web Analytics
Matomo
```

## 28.2 Monitoramento técnico

- [ ] Logs de erro disponíveis.
- [ ] Monitoramento de uptime configurado, se aplicável.
- [ ] Alertas configurados, se aplicável.
- [ ] Métricas de servidor avaliadas.
- [ ] Espaço em disco monitorado.
- [ ] Backups monitorados.
- [ ] Renovação de certificado automática validada.

---

# 29. Validação final de SEO e qualidade

## 29.1 Ferramentas

- [ ] Google Search Console configurado.
- [ ] Sitemap enviado ao Search Console.
- [ ] PageSpeed Insights executado.
- [ ] Lighthouse executado.
- [ ] Rich Results Test executado.
- [ ] W3C Validator executado.
- [ ] WAVE ou ferramenta de acessibilidade executada.
- [ ] Teste de compartilhamento de link feito no WhatsApp/LinkedIn/Facebook, se aplicável.
- [ ] Bing Webmaster Tools configurado, se aplicável.

## 29.2 Itens a verificar manualmente

- [ ] O título aparece corretamente no navegador.
- [ ] O título aparece corretamente no Google ou preview.
- [ ] A descrição está correta.
- [ ] A imagem de compartilhamento aparece corretamente.
- [ ] O favicon aparece corretamente.
- [ ] A home carrega rápido.
- [ ] As principais páginas carregam rápido.
- [ ] O site funciona no celular.
- [ ] Não há erro visual evidente.
- [ ] Não há erro no console do navegador.
- [ ] Não há link quebrado evidente.
- [ ] Não há conteúdo de teste ou placeholder.

---

# 30. Checklist de páginas essenciais

Marque as páginas que fazem sentido para o projeto.

## 30.1 Páginas institucionais

- [ ] Home
- [ ] Sobre
- [ ] Serviços
- [ ] Projetos/Portfólio
- [ ] Blog/Conteúdos
- [ ] Contato
- [ ] Política de Privacidade
- [ ] Termos de Uso
- [ ] Página 404
- [ ] Página de obrigado/sucesso
- [ ] Página de erro

## 30.2 Sistemas com login

- [ ] Login
- [ ] Cadastro
- [ ] Recuperação de senha
- [ ] Confirmação de e-mail
- [ ] Dashboard
- [ ] Perfil do usuário
- [ ] Configurações
- [ ] Administração
- [ ] Logs/auditoria, se aplicável
- [ ] Ajuda/suporte

---

# 31. Checklist específico para Next.js

## 31.1 App Router

- [ ] `app/layout.tsx` revisado.
- [ ] `metadata` global configurado.
- [ ] Metadata específica configurada por página importante.
- [ ] `app/robots.ts` criado.
- [ ] `app/sitemap.ts` criado.
- [ ] `app/not-found.tsx` criado.
- [ ] `app/error.tsx` criado, se necessário.
- [ ] `app/loading.tsx` criado, se necessário.
- [ ] Imagens usam `next/image` quando adequado.
- [ ] Componentes server/client revisados.
- [ ] `"use client"` usado apenas quando necessário.
- [ ] Rotas dinâmicas geram metadata correta.
- [ ] Canonical correta em rotas dinâmicas.
- [ ] Páginas privadas não entram no sitemap.

## 31.2 Exemplo de metadata base

```ts
export const metadata = {
  title: {
    default: "Nome do Site",
    template: "%s | Nome do Site",
  },
  description: "Descrição padrão do site.",
  metadataBase: new URL("https://www.exemplo.com.br"),
  openGraph: {
    title: "Nome do Site",
    description: "Descrição padrão do site.",
    url: "https://www.exemplo.com.br",
    siteName: "Nome do Site",
    images: [
      {
        url: "/opengraph-image.png",
        width: 1200,
        height: 630,
      },
    ],
    locale: "pt_BR",
    type: "website",
  },
  twitter: {
    card: "summary_large_image",
    title: "Nome do Site",
    description: "Descrição padrão do site.",
    images: ["/twitter-image.png"],
  },
};
```

---

# 32. Checklist específico para sites estáticos simples

- [ ] `index.html` criado.
- [ ] `style.css` externo criado.
- [ ] JS separado, se houver.
- [ ] Imagens organizadas em pasta.
- [ ] `robots.txt` criado.
- [ ] `sitemap.xml` criado.
- [ ] `404.html` criado, se a hospedagem permitir.
- [ ] `favicon.ico` configurado.
- [ ] Todas as páginas linkam o mesmo CSS.
- [ ] Caminhos relativos funcionam após deploy.
- [ ] Site funciona ao abrir diretamente cada HTML.
- [ ] Site funciona hospedado em GitHub Pages/Cloudflare Pages.
- [ ] Não há referência a caminho local do computador.

---

# 33. Revisão visual e editorial

## 33.1 Texto

- [ ] Ortografia revisada.
- [ ] Títulos revisados.
- [ ] Botões revisados.
- [ ] Mensagens de erro revisadas.
- [ ] Mensagens de sucesso revisadas.
- [ ] Informações de contato revisadas.
- [ ] Datas, preços e horários revisados.
- [ ] Nome da marca escrito de forma consistente.
- [ ] Não há texto provisório.
- [ ] Não há “lorem ipsum”.

## 33.2 Visual

- [ ] Cores consistentes.
- [ ] Tipografia consistente.
- [ ] Espaçamentos consistentes.
- [ ] Componentes visuais alinhados.
- [ ] Imagens têm qualidade adequada.
- [ ] Logo aparece corretamente.
- [ ] Rodapé aparece corretamente.
- [ ] Menu aparece corretamente.
- [ ] Layout não quebra em telas pequenas.
- [ ] Layout não quebra em telas grandes.

---

# 34. Teste manual de navegação

- [ ] Abrir a home.
- [ ] Clicar em todos os itens do menu.
- [ ] Clicar em todos os botões principais.
- [ ] Testar formulário de contato.
- [ ] Testar links externos.
- [ ] Testar links de redes sociais.
- [ ] Testar navegação pelo rodapé.
- [ ] Testar página 404 com URL inexistente.
- [ ] Testar em janela anônima.
- [ ] Testar em celular real, se possível.
- [ ] Testar em navegador diferente, se possível.

---

# 35. Checklist de publicação

## 35.1 Antes de publicar

- [ ] Branch correta selecionada.
- [ ] Último commit feito.
- [ ] Repositório remoto atualizado.
- [ ] Build local testado.
- [ ] Variáveis de produção conferidas.
- [ ] Banco de produção conferido.
- [ ] Backup feito, se for atualização de sistema existente.
- [ ] Plano de rollback definido, se necessário.

## 35.2 Depois de publicar

- [ ] Site abre em produção.
- [ ] Console do navegador sem erro grave.
- [ ] Logs do servidor sem erro grave.
- [ ] Search Console configurado.
- [ ] Sitemap enviado.
- [ ] PageSpeed executado.
- [ ] Links principais testados.
- [ ] Formulários testados.
- [ ] Login testado, se existir.
- [ ] E-mail testado, se existir.
- [ ] Imagem de compartilhamento testada.

---

# 36. Registro final de validação

Use esta área para registrar o fechamento do projeto.

```txt
Projeto:
Domínio:
Data da validação:
Responsável:
Versão:
Commit/Tag:
Hospedagem:
Banco de dados:
Observações:
Pendências aceitas:
```

## Resultado final

- [ ] Aprovado para publicação.
- [ ] Aprovado com pendências leves.
- [ ] Reprovado para publicação.

## Pendências

```txt
1.
2.
3.
```

---

# 37. Checklist resumido para revisão rápida

Use este bloco quando precisar de uma revisão mais rápida.

- [ ] HTTPS funcionando.
- [ ] Domínio canônico definido.
- [ ] Redirects corretos.
- [ ] `robots.txt` funcionando.
- [ ] `sitemap.xml` funcionando.
- [ ] Página 404 funcionando.
- [ ] Favicon configurado.
- [ ] Title único por página.
- [ ] Description única por página.
- [ ] Canonical correta.
- [ ] Open Graph completo.
- [ ] Twitter Card completo.
- [ ] Schema JSON-LD validado, se aplicável.
- [ ] HTML semântico.
- [ ] Um H1 por página.
- [ ] URLs amigáveis.
- [ ] Imagens otimizadas.
- [ ] Imagens com `alt`.
- [ ] Performance mobile testada.
- [ ] Core Web Vitals verificados.
- [ ] Site responsivo.
- [ ] Acessibilidade básica validada.
- [ ] Política de privacidade publicada.
- [ ] Formulários testados.
- [ ] Login testado, se existir.
- [ ] Banco e backups revisados, se existir.
- [ ] Analytics configurado, se aplicável.
- [ ] Search Console configurado.
- [ ] Sitemap enviado.
- [ ] Links testados.
- [ ] Conteúdo revisado.
- [ ] Deploy final validado.

---

# 38. Observação final

SEO e performance não são uma etapa única no fim do projeto. O ideal é usar este checklist em três momentos:

1. **Antes de desenvolver**, para planejar estrutura, URLs e conteúdo.
2. **Antes de publicar**, para corrigir problemas técnicos.
3. **Depois de publicar**, para validar indexação, performance e comportamento real.

Um sistema bem finalizado não é apenas o que “funciona”. É o que pode ser encontrado, carregado rápido, usado com clareza, compartilhado corretamente, monitorado e mantido com segurança.