# Pilares para começar um projeto de software do jeito certo

Este documento é o ponto de entrada do repositório: um mapa dos 13 pilares que sustentam um projeto profissional, do planejamento à operação em produção.

Cada pilar tem uma explicação curta aqui e um link para o documento detalhado (com checklist completo) na pasta correspondente. Não é para ler tudo de uma vez — é para saber onde procurar quando o projeto chegar naquela etapa.

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

## 1. Produto e propósito

Antes de começar pelo código, banco de dados, tela ou framework, o projeto precisa responder:

```txt
O que o sistema resolve?
Para quem?
Qual é o fluxo principal?
Qual é o MVP?
O que fica para depois?
```

Esse pilar evita o erro clássico de começar a implementar sem entender claramente o problema.

### Checklist

- [ ] O problema foi definido claramente.
- [ ] O público-alvo foi identificado.
- [ ] O fluxo principal foi descrito.
- [ ] O MVP foi separado das funcionalidades futuras.
- [ ] Existem critérios mínimos para considerar a primeira versão pronta.

---

## 2. Arquitetura

Arquitetura é o conjunto de decisões estruturais que sustenta o projeto: stack, pastas, camadas, rotas, APIs, banco de dados, serviços externos, deploy e domínios. Esse pilar evita que o sistema vire um amontoado de arquivos sem padrão.

📄 Detalhes: [01-arquitetura-stack/checklist-arquitetura.md](../01-arquitetura-stack/checklist-arquitetura.md), [arquitetura-limpa.md](../01-arquitetura-stack/arquitetura-limpa.md), [arquitetura-hexagonal.md](../01-arquitetura-stack/arquitetura-hexagonal.md), [ddd.md](../01-arquitetura-stack/ddd.md), [adr-decisoes-arquiteturais.md](../01-arquitetura-stack/adr-decisoes-arquiteturais.md)

---

## 3. Dados

Todo projeto minimamente sério precisa pensar em dados, mesmo quando parece ser apenas um site simples: quais dados existem, onde ficam, quem acessa, backup, retenção e dado pessoal.

📄 Detalhes: [01-arquitetura-stack/modelagem-de-dados.md](../01-arquitetura-stack/modelagem-de-dados.md)

---

## 4. Segurança / AppSec

AppSec é a segurança aplicada ao desenvolvimento: autenticação, autorização, validação de entrada, segredos, headers de segurança e proteção contra XSS/CSRF/injection. Para um site público simples tende a ser mais leve; para sistemas com login, pagamento ou dados sensíveis, vira pilar central.

📄 Detalhes: [02-seguranca-appsec/checklist-appsec.md](../02-seguranca-appsec/checklist-appsec.md), [owasp-basico.md](../02-seguranca-appsec/owasp-basico.md), [secure-by-design.md](../02-seguranca-appsec/secure-by-design.md), [validacao-entrada.md](../02-seguranca-appsec/validacao-entrada.md), [autenticacao-autorizacao.md](../02-seguranca-appsec/autenticacao-autorizacao.md)

---

## 5. Privacidade / LGPD

Próxima de segurança, mas não é a mesma coisa: segurança impede acesso indevido, privacidade questiona se o dado precisa ser coletado, por quanto tempo e com qual base legal. Para qualquer site público profissional, deve existir desde o início.

📄 Detalhes: [02-seguranca-appsec/privacidade-lgpd.md](../02-seguranca-appsec/privacidade-lgpd.md)

---

## 6. Qualidade e testes

Um projeto bem começado já nasce com uma forma de verificar se não quebrou: lint, type checking, testes unitários, integração, E2E e checklist antes do deploy.

📄 Detalhes: [04-qualidade-testes/checklist-qualidade.md](../04-qualidade-testes/checklist-qualidade.md), [piramide-de-testes.md](../04-qualidade-testes/piramide-de-testes.md), [testabilidade.md](../04-qualidade-testes/testabilidade.md), [code-review.md](../04-qualidade-testes/code-review.md)

---

## 7. DevOps e entrega

Responde: como o código sai da minha máquina e chega em produção? Git, branches, commits, CI/CD, ambientes, rollback e variáveis de ambiente.

📄 Detalhes: [05-devops-entrega/checklist-pre-deploy.md](../05-devops-entrega/checklist-pre-deploy.md), [ci-cd.md](../05-devops-entrega/ci-cd.md), [deploy-rollback.md](../05-devops-entrega/deploy-rollback.md), [git-commits-branches.md](../05-devops-entrega/git-commits-branches.md), [ambientes-env.md](../05-devops-entrega/ambientes-env.md)

---

## 8. Infraestrutura e operação

Mesmo com deploy em Cloudflare Pages, Vercel ou Netlify, ainda existe operação: DNS, SSL/TLS, cache, backup, monitoramento, alertas e custos. Evita que o projeto funcione apenas "por sorte".

📄 Detalhes: [07-operacao-observabilidade/checklist-operacao.md](../07-operacao-observabilidade/checklist-operacao.md), [health-check.md](../07-operacao-observabilidade/health-check.md)

---

## 9. Observabilidade

Responde: como vou saber que deu problema, como vou investigar, como vou saber se alguém está usando? Logs, métricas, health check e alertas.

📄 Detalhes: [07-operacao-observabilidade/logs-metricas-traces.md](../07-operacao-observabilidade/logs-metricas-traces.md)

---

## 10. Performance

Não é só "site rápido" — é projeto pensado para não desperdiçar recursos: imagens otimizadas, cache, CDN, bundle pequeno, Core Web Vitals.

📄 Detalhes: [06-publicacao-seo-performance/checklist-seo-performance-publicacao.md](../06-publicacao-seo-performance/checklist-seo-performance-publicacao.md) (seção 15)

---

## 11. UX, acessibilidade e responsividade

Responde: a pessoa consegue usar? No celular funciona? Dá para navegar pelo teclado? O visitante decide em poucos segundos se fica ou sai.

📄 Detalhes: [06-publicacao-seo-performance/acessibilidade-ux-responsividade.md](../06-publicacao-seo-performance/acessibilidade-ux-responsividade.md)

---

## 12. SEO e presença pública

Para site público, esse pilar é obrigatório: title, description, Open Graph, sitemap.xml, robots.txt, 404, URLs amigáveis e conteúdo indexável.

📄 Detalhes: [06-publicacao-seo-performance/checklist-seo-performance-publicacao.md](../06-publicacao-seo-performance/checklist-seo-performance-publicacao.md)

---

## 13. Documentação

Documentação boa não é burocracia, é economia de tempo futuro: README, como rodar localmente, como fazer deploy, decisões importantes registradas.

📄 Detalhes: [00-visao-geral/documentacao-de-projeto.md](documentacao-de-projeto.md)

---

## Checklist rápido para iniciar um projeto

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

## Conclusão

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
