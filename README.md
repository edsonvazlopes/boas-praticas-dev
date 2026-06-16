# Guia de Desenvolvimento de Sistemas

Repositório pessoal de boas práticas e padrões de mercado para desenvolvimento de software: do planejamento (arquitetura, stack, segurança) até a publicação e operação em produção.

Não é um framework nem um curso. É uma base de consulta para não esquecer o que importa em cada etapa de um projeto.

---

## Como usar

1. Comece por [`docs/00-visao-geral/pilares-para-comecar-um-projeto.md`](docs/00-visao-geral/pilares-para-comecar-um-projeto.md) — mapa dos 13 pilares, com link para o detalhe de cada um.
2. Durante o desenvolvimento, consulte a pasta do tema conforme a necessidade (arquitetura, segurança, código, testes, devops...).
3. Antes de publicar, rode o [`checklist de SEO, performance e publicação`](docs/06-publicacao-seo-performance/checklist-seo-performance-publicacao.md).
4. Para começar um projeto novo, copie os modelos de [`templates/`](templates/).

---

## Estrutura

```txt
docs/
├── 00-visao-geral/                  pilares do projeto e documentação
├── 01-arquitetura-stack/            arquitetura, ADR, DDD, dados
├── 02-seguranca-appsec/             AppSec, OWASP, privacidade/LGPD
├── 03-boas-praticas-codigo/         clean code, SOLID, DRY/KISS/YAGNI
├── 04-qualidade-testes/             pirâmide de testes, testabilidade, code review
├── 05-devops-entrega/               git, CI/CD, ambientes, deploy/rollback
├── 06-publicacao-seo-performance/   SEO, performance, acessibilidade, UX
├── 07-operacao-observabilidade/     health check, logs, métricas
└── 08-ia-no-desenvolvimento/        uso responsável de IA

templates/                           modelos copy-paste para projetos novos
```

A ordem das pastas segue o ciclo de vida de um projeto: decisões de arquitetura e segurança vêm antes de código, testes, entrega e publicação.

---

## O que este repositório não é

Não é uma regra única para todo projeto, nem substitui análise técnica do caso concreto. Cada projeto tem escala, risco e contexto próprios — os documentos aqui são ponto de partida, não lei.

---

## Ideia central

```txt
Desenvolver bem não é apenas fazer funcionar.
É planejar, construir, proteger, testar, publicar, documentar e manter.
```
