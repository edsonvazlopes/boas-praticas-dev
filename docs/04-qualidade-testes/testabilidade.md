# Testabilidade

Código bom costuma ser mais fácil de testar — testabilidade é uma consequência de bom design, não uma camada extra.

---

## Sinais de código difícil de testar

```txt
depende diretamente de banco
depende diretamente de API externa
usa data/hora global sem controle
mistura regra de negócio com interface
usa variáveis globais demais
```

Prefira injetar dependências, separar regras puras (sem efeito colateral) de código de borda (banco, API, UI), e criar testes para os comportamentos importantes — não para tudo, mas para o que tem risco real de quebrar.

Ver também: [coesão e acoplamento](../03-boas-praticas-codigo/coesao-acoplamento.md) e [pirâmide de testes](piramide-de-testes.md).

---

## Checklist

- [ ] Regras de negócio estão separadas de banco, API externa e UI?
- [ ] Dependências externas podem ser substituídas em teste (injeção)?
- [ ] O comportamento principal tem teste?
- [ ] Casos de erro foram considerados em teste?
- [ ] Datas, IDs e aleatoriedade são controláveis em teste?
