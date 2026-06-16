# Infraestrutura como Código (IaC) e GitOps

Configurar infraestrutura manualmente (clicar no console do provedor) não escala, não é auditável e não é reproduzível. Infraestrutura como código trata infra do mesmo jeito que código de aplicação: versionada, revisada e aplicada por pipeline.

---

## O que entra

```txt
Terraform, Pulumi, CloudFormation, wrangler.jsonc
ambientes declarados em arquivo, não criados manualmente
state versionado e com lock (evita aplicação concorrente)
revisão de mudança de infra como revisão de código (plan antes de apply)
```

---

## GitOps

GitOps é a prática de usar o repositório Git como única fonte da verdade para o estado desejado da infraestrutura — uma ferramenta automatizada aplica o que está no repositório, em vez de alguém rodar comandos manualmente.

```txt
mudança de infra = pull request
merge no branch principal = trigger de aplicação automática
estado real é comparado ao declarado (drift detection)
```

---

## Práticas

- nunca alterar recurso de produção fora do código declarado (evita "drift" entre o real e o documentado);
- `plan`/dry-run antes de `apply`, revisado por outra pessoa quando a mudança é sensível;
- state remoto com lock, nunca local sem trava de concorrência;
- segredos não ficam em texto plano no código de infra — referenciam um cofre (ver [gestao-de-segredos.md](../02-seguranca-appsec/gestao-de-segredos.md));
- ambientes (dev/staging/produção) usam o mesmo código de infra com parâmetros diferentes, não código duplicado e divergente.

---

## Checklist

- [ ] A infraestrutura está declarada em código, versionado em Git?
- [ ] Existe revisão (plan/dry-run) antes de aplicar mudança em produção?
- [ ] O state é remoto e tem lock contra aplicação concorrente?
- [ ] Produção não foi alterada manualmente fora do código (sem drift não documentado)?
- [ ] Segredos de infra não estão em texto plano no repositório?
