# Documentação

Documentação boa não é burocracia. É economia de tempo futuro — tanto para quem volta ao projeto depois quanto para quem nunca o viu.

---

## Mínimo saudável

```txt
README.md
como rodar localmente
como configurar .env
como fazer deploy
estrutura de pastas
decisões importantes
checklist de publicação
```

## Em projetos mais sérios, vale criar

```txt
docs/arquitetura.md
docs/deploy.md
docs/seguranca.md
docs/backup.md
docs/decisoes/ADR-001.md
```

Use o [modelo de README](../../templates/README-projeto.md) e o [modelo de ADR](../../templates/modelo-adr.md) em `templates/` como ponto de partida.

---

## Checklist

- [ ] Existe README.
- [ ] O README explica como rodar localmente.
- [ ] O README explica como configurar ambiente.
- [ ] O deploy está documentado.
- [ ] Decisões importantes foram registradas (ADR).
- [ ] Existe documentação de segurança quando aplicável.
- [ ] Existe documentação de backup quando aplicável.
