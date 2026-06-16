# Validação de Entrada

Toda entrada externa deve ser tratada como não confiável.

Entradas incluem:

```txt
formulários
query params
body JSON
headers
cookies
uploads
webhooks
dados vindos de APIs externas
```

---

## Boas práticas

- validar tipo;
- validar formato;
- validar tamanho;
- validar faixa de valor;
- normalizar dados quando necessário;
- rejeitar campos inesperados;
- usar schemas de validação;
- validar também no servidor.

---

## Exemplo

```txt
E-mail deve ter formato de e-mail.
Senha deve ter tamanho mínimo.
Valor monetário deve ser número positivo.
ID deve pertencer ao usuário autorizado.
Arquivo enviado deve ter tipo e tamanho permitidos.
```

---

## Checklist

- [ ] Todas as entradas externas são validadas?
- [ ] O servidor valida mesmo que o front-end valide?
- [ ] Campos extras são rejeitados?
- [ ] Uploads têm limite de tamanho e tipo?
- [ ] IDs recebidos são conferidos contra permissão do usuário?

