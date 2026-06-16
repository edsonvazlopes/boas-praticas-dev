# Code Review

Code review é uma prática de colaboração para melhorar qualidade, segurança e manutenção.

Não é caça ao erro pessoal. É revisão técnica do produto.

---

## O que observar

- clareza;
- escopo;
- segurança;
- testes;
- impacto em produção;
- aderência ao padrão do projeto;
- documentação necessária;
- simplicidade da solução.

---

## Boas perguntas

```txt
Essa alteração resolve o problema certo?
Existe caso de erro não tratado?
O código ficou mais difícil de manter?
Há risco de segurança?
Há teste suficiente para o risco?
```

---

## Checklist

### Clareza

- [ ] O objetivo da alteração está claro.
- [ ] Os nomes de variáveis, funções e arquivos são compreensíveis.
- [ ] O código evita lógica desnecessariamente complexa.
- [ ] Comentários existem apenas onde ajudam.

### Estrutura

- [ ] A responsabilidade está no lugar correto.
- [ ] Não há duplicação relevante.
- [ ] A alteração respeita o padrão do projeto.
- [ ] Não foram feitos refactors fora do escopo sem necessidade.

### Segurança

- [ ] Entradas de usuário são validadas.
- [ ] Permissões são verificadas no servidor.
- [ ] Segredos não aparecem no código.
- [ ] Logs não expõem dados sensíveis.
- [ ] Erros não vazam detalhes internos.

### Testes

- [ ] O comportamento principal foi testado.
- [ ] Casos de erro foram considerados.
- [ ] O build continua funcionando.
- [ ] O lint ou verificação equivalente foi executado.

### Entrega

- [ ] README ou documentação foram atualizados, se necessário.
- [ ] Variáveis de ambiente novas aparecem no `.env.example`.
- [ ] Migrações de banco foram revisadas, se houver.
- [ ] O impacto em produção foi considerado.

