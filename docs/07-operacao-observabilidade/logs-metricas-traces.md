# Logs, Métricas e Traces

Observabilidade ajuda a entender o que acontece no sistema em produção.

---

## Logs

Logs registram eventos.

Exemplos:

```txt
usuário autenticado
erro ao salvar pedido
falha em integração externa
tentativa de acesso negado
```

Evite registrar senhas, tokens, documentos, dados sensíveis e conteúdo privado.

---

## Métricas

Métricas mostram números ao longo do tempo.

Exemplos:

```txt
quantidade de acessos
tempo de resposta
taxa de erro
uso de CPU/memória
fila pendente
```

---

## Traces

Traces ajudam a acompanhar uma requisição passando por vários serviços.

São úteis em sistemas distribuídos.

---

## Checklist

- [ ] Erros importantes geram logs?
- [ ] Logs não vazam dados sensíveis?
- [ ] Existem métricas mínimas?
- [ ] Tempo de resposta é observável?
- [ ] Falhas externas são rastreáveis?

