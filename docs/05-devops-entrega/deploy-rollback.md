# Deploy e Rollback

Deploy é o processo de publicar uma versão.

Rollback é o caminho para voltar quando algo dá errado.

---

## Antes do deploy

- executar build;
- executar testes;
- conferir variáveis;
- revisar migrações;
- verificar domínio e HTTPS;
- registrar versão;
- preparar rollback.

---

## Estratégias de rollback

```txt
voltar para commit anterior
restaurar build anterior
reverter migração, quando seguro
desativar feature flag
restaurar backup
```

---

## Checklist

- [ ] Existe versão identificável?
- [ ] Existe backup quando há dados?
- [ ] O deploy é reproduzível?
- [ ] Existe caminho de rollback?
- [ ] A equipe sabe como reverter?
- [ ] Logs podem ser consultados após publicação?

Ver também: [entrega-progressiva.md](entrega-progressiva.md) (canary, blue-green, feature flag) e [metricas-dora.md](metricas-dora.md).

