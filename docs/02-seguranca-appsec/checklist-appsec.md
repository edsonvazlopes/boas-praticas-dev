# Checklist AppSec

Use este checklist em projetos com login, formulários, banco de dados, integrações ou dados pessoais.

---

## Segredos

- [ ] `.env` não está versionado.
- [ ] `.env.example` existe.
- [ ] Chaves foram rotacionadas quando expostas.
- [ ] Tokens têm permissões mínimas.

---

## Entrada e saída

- [ ] Entradas são validadas no servidor.
- [ ] Saídas são escapadas quando necessário.
- [ ] Uploads são controlados.
- [ ] Tamanho de payload é limitado.

---

## Acesso

- [ ] Autenticação foi implementada corretamente.
- [ ] Autorização é verificada no servidor.
- [ ] Rotas privadas não são indexáveis.
- [ ] Usuários não acessam dados de outros usuários.

---

## Operação

- [ ] Logs não vazam dados sensíveis.
- [ ] Erros não mostram stack trace em produção.
- [ ] Dependências foram verificadas.
- [ ] HTTPS está ativo.
- [ ] Headers de segurança foram considerados.

Ver também: [gestao-de-segredos.md](gestao-de-segredos.md) e [supply-chain-security.md](supply-chain-security.md) para um nível mais maduro de segredos e dependências.

