# Pilares para começar um projeto de software do jeito certo

Este documento serve como um guia prático para iniciar projetos de software com mais clareza, segurança e profissionalismo.  
A ideia é usar os pilares abaixo como norte antes e durante a construção de um sistema, site, aplicativo ou plataforma.

---

## Visão geral dos pilares

1. Produto e propósito  
2. Arquitetura  
3. Dados  
4. Segurança / AppSec  
5. Privacidade / LGPD  
6. Qualidade e testes  
7. DevOps e entrega  
8. Infraestrutura e operação  
9. Observabilidade  
10. Performance  
11. UX, acessibilidade e responsividade  
12. SEO e presença pública  
13. Documentação  

---

# 1. Produto e propósito

Antes de começar pelo código, banco de dados, tela ou framework, o projeto precisa responder:

```txt
O que o sistema resolve?
Para quem?
Qual é o fluxo principal?
Qual é o MVP?
O que fica para depois?
```

Esse pilar evita o erro clássico de começar a implementar sem entender claramente o problema.

## Exemplo para um site de músico

```txt
Objetivo: apresentar artista, músicas, agenda, links, contato e SEO.
MVP: home, bio, músicas, vídeos, contato, política de privacidade.
Depois: área de fãs, newsletter, loja, painel administrativo.
```

## Checklist

- [ ] O problema foi definido claramente.
- [ ] O público-alvo foi identificado.
- [ ] O fluxo principal foi descrito.
- [ ] O MVP foi separado das funcionalidades futuras.
- [ ] Existem critérios mínimos para considerar a primeira versão pronta.

---

# 2. Arquitetura

Arquitetura é o conjunto de decisões estruturais que sustenta o projeto.

Inclui:

```txt
Stack
pastas
camadas
rotas
APIs
banco de dados
serviços externos
deploy
domínios
```

Para projetos em Next.js, por exemplo, vale decidir cedo:

```txt
App Router ou Pages Router
site estático ou aplicação dinâmica
Cloudflare Pages, Vercel ou VPS
API interna ou serviço externo
banco próprio ou backend externo
```

Esse pilar evita que o sistema vire um amontoado de arquivos sem padrão.

## Checklist

- [ ] A stack principal foi definida.
- [ ] A estrutura de pastas tem lógica clara.
- [ ] As rotas principais foram planejadas.
- [ ] A separação entre front-end, back-end e serviços externos está clara.
- [ ] O destino de deploy foi escolhido.
- [ ] As decisões importantes foram documentadas.

---

# 3. Dados

Todo projeto minimamente sério precisa pensar em dados, mesmo quando parece ser apenas um site simples.

Perguntas essenciais:

```txt
Quais dados existem?
Onde ficam?
Quem pode acessar?
Tem backup?
Tem exportação?
Tem retenção?
Tem dado pessoal?
```

Em sistemas como plataformas financeiras, acadêmicas ou canais privados, esse pilar é central.  
Em sites públicos, ele aparece em formulários de contato, analytics, newsletter, cookies e LGPD.

## Checklist

- [ ] Os dados coletados foram listados.
- [ ] Foi definido onde os dados serão armazenados.
- [ ] Foi definido quem pode acessar os dados.
- [ ] Existe política de backup.
- [ ] Existe política de retenção ou exclusão.
- [ ] Foi verificado se há dados pessoais ou sensíveis.
- [ ] Existe possibilidade de exportar ou migrar os dados.

---

# 4. Segurança / AppSec

AppSec é a segurança aplicada ao desenvolvimento da aplicação.

Inclui:

```txt
autenticação
autorização
validação de entrada
proteção contra abuso
rate limit
segredos em .env
headers de segurança
CSP
dependências atualizadas
proteção contra XSS, CSRF, injection
logs sem vazar dados sensíveis
```

Para um site público simples, AppSec tende a ser mais leve.  
Para sistemas com login, pagamento, dados acadêmicos, mensagens privadas ou informações sensíveis, vira pilar central.

## Checklist

- [ ] Segredos não estão no código.
- [ ] Existe `.env.example`.
- [ ] Entradas de usuário são validadas.
- [ ] Rotas protegidas exigem autenticação.
- [ ] Permissões são verificadas no servidor.
- [ ] Dependências são mantidas atualizadas.
- [ ] Logs não expõem dados sensíveis.
- [ ] Headers de segurança foram considerados.
- [ ] Existe proteção contra abuso ou spam quando necessário.

---

# 5. Privacidade e conformidade

Privacidade é próxima de segurança, mas não é a mesma coisa.

Segurança pergunta:

```txt
Como impedir acesso indevido?
```

Privacidade pergunta:

```txt
Eu realmente preciso coletar esse dado?
Por quanto tempo?
Com qual base legal?
O usuário sabe disso?
```

Aqui entram:

```txt
LGPD
política de privacidade
termos de uso
cookies
analytics
formulários
retenção de dados
exclusão de conta
consentimento
```

Para qualquer site público profissional, esse pilar deve existir desde o início.

## Checklist

- [ ] O projeto coleta apenas dados necessários.
- [ ] Há política de privacidade.
- [ ] Há termos de uso quando necessário.
- [ ] Cookies e analytics foram avaliados.
- [ ] Formulários deixam claro o destino dos dados.
- [ ] Existe política de retenção.
- [ ] Existe caminho para exclusão ou correção de dados quando aplicável.

---

# 6. Qualidade e testes

Um projeto bem começado já nasce com uma forma de verificar se não quebrou.

Inclui:

```txt
lint
type checking
testes unitários
testes de integração
testes de API
testes E2E
testes manuais guiados
checklist antes do deploy
```

Para um site estático, talvez baste:

```txt
npm run build
npm run lint
testar responsividade
testar links
testar SEO básico
testar 404
```

Para sistemas com regras de negócio, entram testes automatizados com ferramentas como Vitest, Supertest e Playwright.

## Checklist

- [ ] O projeto tem comando de build.
- [ ] O projeto tem lint ou verificação equivalente.
- [ ] O TypeScript ou validação equivalente está funcionando, quando aplicável.
- [ ] Existem testes para regras importantes.
- [ ] Existe checklist manual antes do deploy.
- [ ] Links, formulários e páginas principais foram testados.
- [ ] O erro 404 foi testado.

---

# 7. DevOps e entrega

Esse pilar responde:

```txt
Como o código sai da minha máquina e chega em produção?
```

Inclui:

```txt
Git
branches
commits
CI/CD
ambientes
preview deploy
produção
rollback
variáveis de ambiente
logs de build
versionamento
```

Para um projeto moderno, o mínimo saudável é:

```txt
repositório Git
README
.env.example
.gitignore correto
deploy documentado
build funcionando
rollback minimamente possível
```

## Checklist

- [ ] O projeto está em um repositório Git.
- [ ] O `.gitignore` está correto.
- [ ] O `.env` real não está versionado.
- [ ] O `.env.example` existe.
- [ ] Existe README com instruções básicas.
- [ ] O deploy está documentado.
- [ ] Existe ambiente de preview, quando aplicável.
- [ ] Existe caminho de rollback ou restauração.

---

# 8. Infraestrutura e operação

Mesmo quando o deploy está em Cloudflare Pages, Vercel ou Netlify, ainda existe operação.

Inclui:

```txt
DNS
SSL/TLS
cache
domínios
subdomínios
e-mail transacional
backup
monitoramento
alertas
limites do plano
custos
```

Esse pilar evita que o projeto funcione apenas “por sorte” e sem controle.

## Checklist

- [ ] DNS está limpo e documentado.
- [ ] SSL/TLS está ativo.
- [ ] HTTPS é obrigatório.
- [ ] Cache foi configurado com cuidado.
- [ ] Domínio principal foi escolhido.
- [ ] Redirecionamento entre `www` e sem `www` foi definido.
- [ ] Custos e limites do plano foram verificados.
- [ ] Há plano de backup quando o projeto envolve dados.
- [ ] Serviços externos importantes foram listados.

---

# 9. Observabilidade

Observabilidade responde:

```txt
Como vou saber que deu problema?
Como vou investigar?
Como vou saber se alguém está usando?
```

Inclui:

```txt
logs
métricas
analytics
health check
alertas
monitoramento de erro
auditoria
status do deploy
```

Para sistemas maiores, um endpoint simples já ajuda:

```txt
/api/health
```

## Checklist

- [ ] Existe alguma forma de medir acessos ou uso.
- [ ] Existe alguma forma de ver erros.
- [ ] Logs importantes estão disponíveis.
- [ ] Logs não expõem dados sensíveis.
- [ ] Existe health check quando aplicável.
- [ ] Alertas foram configurados para serviços importantes.
- [ ] Status de deploy pode ser consultado.

---

# 10. Performance

Performance não é só “site rápido”. É projeto pensado para não desperdiçar recursos.

Inclui:

```txt
imagens otimizadas
cache
CDN
lazy loading
bundle pequeno
Core Web Vitals
compressão
fontes bem carregadas
consultas eficientes
paginação
```

Para site de músico, isso é especialmente importante porque normalmente há:

```txt
fotos grandes
capas de álbum
vídeos
embeds
players
animações
```

Se não cuidar, o site fica bonito, mas pesado.

## Checklist

- [ ] Imagens foram comprimidas e dimensionadas.
- [ ] Imagens usam formatos modernos quando possível.
- [ ] Vídeos pesados não carregam sem necessidade.
- [ ] Embeds foram usados com cuidado.
- [ ] Fontes foram otimizadas.
- [ ] Cache/CDN foi considerado.
- [ ] O site foi testado em celular.
- [ ] O desempenho foi verificado com ferramenta como Lighthouse ou PageSpeed.

---

# 11. UX, acessibilidade e responsividade

Esse pilar responde:

```txt
A pessoa consegue usar?
No celular funciona?
O texto é legível?
O contraste é bom?
Dá para navegar pelo teclado?
Os botões são claros?
```

Inclui:

```txt
layout mobile
hierarquia visual
contraste
semântica HTML
alt em imagens
formulários claros
feedback de erro
estados de loading
navegação simples
```

Para site artístico, esse pilar é essencial porque o visitante decide em poucos segundos se fica ou sai.

## Checklist

- [ ] O site funciona bem no celular.
- [ ] A navegação é clara.
- [ ] Os botões principais são visíveis.
- [ ] O contraste é adequado.
- [ ] Imagens relevantes têm texto alternativo.
- [ ] O HTML usa semântica adequada.
- [ ] Formulários têm mensagens claras.
- [ ] Estados de carregamento e erro foram considerados.

---

# 12. SEO e presença pública

Para site público, esse pilar é obrigatório.

Inclui:

```txt
title
description
Open Graph
Twitter Cards
canonical
sitemap.xml
robots.txt
404
favicon
manifest
schema.org
URLs amigáveis
conteúdo indexável
performance
redirecionamento www/sem www
```

Para músico, vale adicionar:

```txt
schema MusicGroup ou Person
links oficiais
páginas de músicas
letras, quando fizer sentido
agenda
release
imagens sociais bem definidas
```

## Checklist

- [ ] Cada página tem `title`.
- [ ] Cada página importante tem `description`.
- [ ] Open Graph foi configurado.
- [ ] Imagem de compartilhamento foi definida.
- [ ] Existe `sitemap.xml`.
- [ ] Existe `robots.txt`.
- [ ] Existe página 404.
- [ ] Favicon está configurado.
- [ ] URLs são amigáveis.
- [ ] Há canonical quando necessário.
- [ ] O domínio principal foi definido.
- [ ] SEO local/artístico foi considerado.

---

# 13. Documentação

Documentação boa não é burocracia. É economia de tempo futuro.

Mínimo saudável:

```txt
README.md
como rodar localmente
como configurar .env
como fazer deploy
estrutura de pastas
decisões importantes
checklist de publicação
```

Em projeto mais sério, vale criar:

```txt
docs/arquitetura.md
docs/deploy.md
docs/seguranca.md
docs/backup.md
docs/decisoes/ADR-001.md
```

## Checklist

- [ ] Existe README.
- [ ] O README explica como rodar localmente.
- [ ] O README explica como configurar ambiente.
- [ ] O deploy está documentado.
- [ ] Decisões importantes foram registradas.
- [ ] Existe documentação de segurança quando aplicável.
- [ ] Existe documentação de backup quando aplicável.

---

# Checklist rápido para iniciar um projeto

Use esta lista antes de iniciar ou publicar a primeira versão.

```txt
[ ] Definir objetivo do projeto
[ ] Definir público-alvo
[ ] Definir MVP
[ ] Escolher stack
[ ] Criar estrutura de pastas
[ ] Criar repositório Git
[ ] Criar README.md
[ ] Criar .gitignore
[ ] Criar .env.example
[ ] Planejar dados
[ ] Planejar privacidade/LGPD
[ ] Planejar segurança/AppSec
[ ] Configurar lint/build
[ ] Definir estratégia de testes
[ ] Definir deploy
[ ] Configurar DNS
[ ] Configurar SSL/TLS
[ ] Configurar domínio principal
[ ] Configurar SEO básico
[ ] Configurar sitemap.xml
[ ] Configurar robots.txt
[ ] Configurar 404
[ ] Testar responsividade
[ ] Testar performance
[ ] Testar links e formulários
[ ] Documentar decisões importantes
```

---

# Conclusão

AppSec é essencial, mas não é o único pilar.

Para começar um projeto do jeito certo, o ideal é pensar como produto, sistema e operação desde o início. Isso não significa implementar tudo no primeiro dia, mas significa começar com consciência das áreas que sustentam um projeto profissional.

Em vez de pensar apenas:

```txt
Vou fazer umas telas.
```

O ideal é pensar:

```txt
Estou construindo um produto, com arquitetura, dados, segurança, privacidade, entrega, operação, qualidade, experiência e presença pública.
```
