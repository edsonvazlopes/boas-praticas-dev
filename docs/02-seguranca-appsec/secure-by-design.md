# Secure by Design

Secure by Design significa pensar segurança desde a concepção do sistema, não apenas no final.

---

## Ideia central

```txt
Segurança é requisito de projeto.
Não é acabamento.
```

---

## Práticas

- mapear dados sensíveis;
- definir quem pode acessar o quê;
- validar entradas;
- proteger rotas no servidor;
- usar autenticação confiável;
- aplicar mínimo privilégio;
- registrar eventos importantes;
- evitar vazamento em logs;
- planejar recuperação em caso de incidente.

---

## Perguntas úteis

```txt
Quais dados o sistema coleta?
Quem pode ver esses dados?
Que ação exige autenticação?
Que ação exige permissão?
O que acontece se uma API for chamada diretamente?
O que acontece se um usuário malicioso alterar o front-end?
```

---

## Checklist

- [ ] Dados sensíveis foram identificados?
- [ ] Permissões foram definidas?
- [ ] Regras são verificadas no servidor?
- [ ] Entradas são validadas?
- [ ] Segredos estão fora do código?
- [ ] Logs não expõem dados sensíveis?
- [ ] Existe plano mínimo de resposta a erro ou incidente?

