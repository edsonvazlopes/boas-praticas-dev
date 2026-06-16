# OWASP Básico para Projetos Web

OWASP é uma referência importante para segurança em aplicações web.

Este guia resume pontos essenciais para projetos pequenos e médios.

---

## Riscos comuns

```txt
controle de acesso quebrado
falhas criptográficas
injeção
configuração insegura
componentes vulneráveis
falhas de autenticação
logs insuficientes
```

---

## Práticas mínimas

- validar dados de entrada;
- escapar ou codificar saída quando necessário;
- proteger rotas privadas;
- conferir autorização no servidor;
- usar HTTPS;
- armazenar senhas com hash forte;
- manter dependências atualizadas;
- configurar headers de segurança;
- não expor stack trace ao usuário.

---

## Checklist

- [ ] Há validação de entrada?
- [ ] Há controle de acesso?
- [ ] Permissões são testadas?
- [ ] Senhas usam hash adequado?
- [ ] Dependências foram verificadas?
- [ ] Variáveis sensíveis estão protegidas?
- [ ] Ambientes de teste não são públicos indevidamente?

