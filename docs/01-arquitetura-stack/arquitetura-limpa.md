# Arquitetura Limpa

Arquitetura Limpa busca separar regras de negócio de detalhes externos como banco de dados, framework, interface, fila, API e provedor de autenticação.

---

## Ideia central

```txt
Regra de negócio não deve depender de detalhe técnico.
Detalhe técnico deve depender da regra ou de contratos definidos por ela.
```

---

## Camadas comuns

```txt
Entidades: conceitos centrais do domínio.
Casos de uso: ações importantes do sistema.
Interfaces/contratos: portas usadas pelos casos de uso.
Infraestrutura: banco, e-mail, storage, APIs externas.
Interface: telas, controllers, rotas, handlers.
```

---

## Benefícios

- facilita testes;
- reduz dependência de framework;
- protege regra de negócio;
- melhora manutenção;
- permite trocar infraestrutura com menos impacto.

---

## Checklist

- [ ] Regras de negócio estão separadas de framework?
- [ ] Casos de uso são fáceis de localizar?
- [ ] Banco e APIs externas estão isolados?
- [ ] Testes podem rodar sem infraestrutura real?
- [ ] A arquitetura não está complexa demais para o tamanho do projeto?

