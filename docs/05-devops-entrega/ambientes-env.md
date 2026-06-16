# Ambientes e Variáveis de Ambiente

Projetos profissionais separam configuração de código.

Variáveis de ambiente permitem adaptar o mesmo código para desenvolvimento, teste, homologação e produção.

---

## Ambientes comuns

```txt
development: ambiente local
test: testes automatizados
staging: homologação
production: produção
```

---

## Boas práticas

- não versionar `.env`;
- criar `.env.example`;
- documentar cada variável;
- usar nomes claros;
- separar segredos por ambiente;
- rotacionar chaves expostas;
- não reutilizar segredos de produção localmente.

---

## Checklist

- [ ] `.env` está fora do Git?
- [ ] `.env.example` existe?
- [ ] Variáveis novas foram documentadas?
- [ ] Produção e desenvolvimento usam chaves diferentes?
- [ ] Segredos foram configurados no provedor de deploy?

