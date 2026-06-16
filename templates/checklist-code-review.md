# Checklist de Code Review

> Versão condensada para colar em um PR. Versão completa com contexto: [docs/04-qualidade-testes/code-review.md](../docs/04-qualidade-testes/code-review.md).

- [ ] O objetivo da alteração está claro.
- [ ] O código é legível e os nomes são claros.
- [ ] A responsabilidade está no lugar certo, sem duplicação relevante.
- [ ] Entradas de usuário são validadas.
- [ ] Permissões são verificadas no servidor.
- [ ] Segredos não aparecem no código; logs não vazam dados sensíveis.
- [ ] Há teste para o comportamento principal e para os casos de erro.
- [ ] Build e lint continuam passando.
- [ ] README/documentação e `.env.example` foram atualizados quando necessário.
- [ ] O impacto em produção foi considerado.
