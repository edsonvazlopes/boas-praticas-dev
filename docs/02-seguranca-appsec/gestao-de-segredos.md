# Gestão de Segredos

`.env` fora do Git é o mínimo, não o ideal. Em sistemas com mais de um ambiente, mais de uma pessoa ou exigência de compliance, segredos precisam de um ciclo de vida gerenciado.

---

## Problemas do `.env` puro

```txt
segredo de longa duração, raramente rotacionado
acesso ao segredo = acesso ao arquivo, sem trilha de quem usou
revogação exige redeploy manual em todo lugar que usa o valor
```

---

## Prática mais madura

```txt
cofre de segredos (Vault, AWS Secrets Manager, Cloudflare Secrets Store, Doppler...)
segredos de curta duração quando o provedor suporta (credenciais que expiram em horas)
rotação automática programada, não só "quando vaza"
acesso por identidade (IAM/serviço), não por arquivo compartilhado
trilha de auditoria: quem/o que acessou qual segredo e quando
```

---

## Hierarquia de risco

```txt
Baixo:  chave de API de serviço não crítico, sem custo se exposta.
Médio:  credencial de banco de dados, chave de serviço de e-mail.
Alto:   chave de assinatura, credencial de produção com escrita,
        chave que dá acesso a dados pessoais ou financeiros.
```

Segredos de risco alto merecem cofre dedicado e rotação ativa, não só `.env`.

---

## Checklist

- [ ] Segredos de produção não circulam por chat, e-mail ou arquivo compartilhado sem controle.
- [ ] Existe plano de rotação para segredos de risco alto/médio.
- [ ] Ao revogar um segredo, dá para saber tudo que precisa ser atualizado.
- [ ] Segredos diferem entre ambientes (dev ≠ staging ≠ produção).
- [ ] Há registro de quem/o que acessa segredos de produção.

Ver também: [checklist-appsec.md](checklist-appsec.md), [supply-chain-security.md](supply-chain-security.md).
