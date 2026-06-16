# DDD - Domain-Driven Design

DDD é uma abordagem para construir software a partir do entendimento profundo do domínio do negócio.

Não é apenas uma arquitetura. É uma forma de alinhar linguagem, regra e implementação.

---

## Conceitos essenciais

```txt
Domínio: área de problema que o sistema resolve.
Entidade: objeto com identidade.
Value Object: objeto definido por valor.
Agregado: grupo de objetos tratados como unidade.
Repositório: abstração para persistência.
Serviço de domínio: regra que não pertence naturalmente a uma entidade.
Linguagem ubíqua: vocabulário compartilhado entre equipe e negócio.
Bounded Context: limite onde um modelo faz sentido.
```

---

## Quando vale a pena

- quando há regra de negócio rica;
- quando os termos do negócio importam;
- quando há muitos fluxos e exceções;
- quando diferentes áreas usam conceitos parecidos com sentidos diferentes.

---

## Quando pode ser exagero

- site simples;
- CRUD muito básico;
- projeto pequeno sem regra complexa;
- equipe sem maturidade para manter os conceitos.

---

## Checklist

- [ ] Os nomes do código refletem o vocabulário do negócio?
- [ ] As regras importantes estão explícitas?
- [ ] Existem limites claros entre contextos?
- [ ] O modelo evita depender de detalhes técnicos?
- [ ] O domínio é compreensível por alguém do negócio?

