# Autenticação e Autorização

Autenticação responde: quem é você?

Autorização responde: o que você pode fazer?

Confundir as duas é uma fonte comum de falhas de segurança.

---

## Autenticação

Cuida de login, senha, sessão, token, recuperação de senha e identidade.

Boas práticas:

- usar bibliotecas confiáveis;
- armazenar senha com hash forte;
- proteger sessão;
- limitar tentativas abusivas;
- não revelar se e-mail existe em recuperação de senha;
- usar HTTPS.

---

## Autorização

Cuida de permissões.

Boas práticas:

- verificar permissão no servidor;
- nunca confiar apenas no front-end;
- aplicar mínimo privilégio;
- registrar ações sensíveis;
- testar acesso negado.

---

## Checklist

- [ ] Rotas privadas exigem login?
- [ ] A permissão é conferida no servidor?
- [ ] Usuário comum não acessa área administrativa?
- [ ] Tokens e sessões expiram?
- [ ] Senhas não são armazenadas em texto puro?
- [ ] Recuperação de senha é segura?

