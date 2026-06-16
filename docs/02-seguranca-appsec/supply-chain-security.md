# Supply Chain Security

Segurança da cadeia de suprimentos de software protege contra comprometimento via dependências, ferramentas de build e pipeline — não só código próprio. Incidentes como SolarWinds e o backdoor no xz-utils mostraram que o elo mais fraco geralmente não é o seu código.

---

## O que entra

```txt
dependências diretas e transitivas
integridade do lockfile
proveniência do build (de onde veio o artefato)
assinatura de pacotes e imagens
permissões do CI/CD
tokens e credenciais usados no pipeline
```

---

## Práticas

- lockfile sempre commitado e respeitado (`npm ci`, não `npm install`) — instala exatamente o que foi testado;
- auditoria automática de vulnerabilidades conhecidas (Dependabot, Snyk, `npm audit`) rodando no CI, não só localmente;
- gerar SBOM (Software Bill of Materials) do build para saber exatamente o que está em produção;
- assinar artefatos de build (imagens de container, releases) e verificar assinatura antes de deploy;
- restringir permissões de tokens do CI/CD ao mínimo necessário;
- revisar pull requests que adicionam novas dependências, não só código próprio;
- fixar versão sem range automático (`^`/`~`) em dependências críticas quando o risco de update silencioso for relevante.

---

## Checklist

- [ ] Lockfile está commitado e é respeitado no CI.
- [ ] Há auditoria automática de vulnerabilidades no pipeline.
- [ ] SBOM é gerado para builds de produção, quando aplicável.
- [ ] Artefatos de build/release são assinados e verificados.
- [ ] Tokens de CI/CD têm permissão mínima necessária.
- [ ] Novas dependências passam por revisão antes de merge.

Referência: SLSA (Supply-chain Levels for Software Artifacts). Ver também: [gestao-de-segredos.md](gestao-de-segredos.md).
