# Checklist Pré-Deploy

Use antes de publicar uma nova versão.

---

## Código

- [ ] Build executa sem erro.
- [ ] Lint executa sem erro crítico.
- [ ] Testes importantes passaram.
- [ ] Código foi revisado.

---

## Configuração

- [ ] Variáveis de ambiente estão corretas.
- [ ] `.env.example` está atualizado.
- [ ] Segredos não estão versionados.
- [ ] Configuração de produção foi conferida.

---

## Banco e dados

- [ ] Migrações foram revisadas.
- [ ] Backup foi feito quando necessário.
- [ ] Dados de teste não vão para produção.

---

## Publicação

- [ ] Domínio está correto.
- [ ] HTTPS está ativo.
- [ ] Página 404 existe.
- [ ] Logs podem ser acessados.
- [ ] Rollback foi planejado.

