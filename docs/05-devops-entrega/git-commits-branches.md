# Git, Commits e Branches

Git é a base do versionamento e da colaboração em projetos de software.

---

## Boas práticas

- fazer commits pequenos e coerentes;
- escrever mensagens claras;
- evitar misturar assuntos no mesmo commit;
- revisar alterações antes de enviar;
- manter `.gitignore` correto;
- não versionar `.env`, senhas ou arquivos temporários.

---

## Commits

Mensagem simples:

```txt
Adiciona checklist inicial de AppSec
Corrige validação do formulário de contato
Atualiza documentação de deploy
```

Formato convencional, quando desejado:

```txt
feat: adiciona autenticação
fix: corrige erro no login
docs: atualiza README
refactor: reorganiza serviço de usuários
test: adiciona teste de permissão
```

---

## Branches

Estratégia simples:

```txt
main: produção ou versão estável
dev: integração, quando necessário
feature/nome: nova funcionalidade
fix/nome: correção
```

---

## Checklist

- [ ] O `.gitignore` está correto?
- [ ] O commit tem apenas um assunto principal?
- [ ] A mensagem explica a mudança?
- [ ] Segredos não foram versionados?
- [ ] README foi atualizado quando necessário?

