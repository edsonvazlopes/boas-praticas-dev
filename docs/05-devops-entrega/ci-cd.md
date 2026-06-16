# CI/CD

CI/CD automatiza verificações e entrega de software.

CI significa integração contínua.

CD pode significar entrega contínua ou deploy contínuo.

---

## O que automatizar

```txt
instalação de dependências
lint
testes
build
verificação de tipos
auditoria básica de dependências
deploy
```

---

## Benefícios

- reduz erro manual;
- detecta quebra cedo;
- melhora confiança no deploy;
- cria histórico de entregas;
- facilita rollback e diagnóstico.

---

## Checklist

- [ ] Existe pipeline de verificação?
- [ ] O build roda automaticamente?
- [ ] Testes rodam automaticamente?
- [ ] Deploy exige aprovação quando necessário?
- [ ] Falhas bloqueiam publicação?
- [ ] Variáveis de ambiente estão configuradas no ambiente correto?

Ver também: [supply-chain-security.md](../02-seguranca-appsec/supply-chain-security.md) (auditoria de dependências, SBOM, assinatura de build).

