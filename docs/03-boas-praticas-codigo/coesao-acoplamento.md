# Coesão e Acoplamento

Coesão e acoplamento são conceitos centrais para avaliar a qualidade estrutural de um código.

---

## Coesão

Coesão mede o quanto as partes de um módulo pertencem ao mesmo assunto.

Alta coesão:

```txt
Um módulo de autenticação cuida de login, logout, sessão e senha.
```

Baixa coesão:

```txt
Um módulo de autenticação também gera relatório financeiro e envia newsletter.
```

---

## Acoplamento

Acoplamento mede o quanto uma parte depende de outra.

Baixo acoplamento permite trocar implementação com menos impacto.

Alto acoplamento faz uma mudança pequena quebrar várias áreas do sistema.

---

## Checklist

- [ ] O módulo tem um tema claro?
- [ ] O módulo mistura responsabilidades distantes?
- [ ] Há dependência direta de detalhes que poderiam ser abstraídos?
- [ ] Uma mudança pequena exige alterar muitos arquivos?
- [ ] A regra de negócio está presa a framework, banco ou interface?

