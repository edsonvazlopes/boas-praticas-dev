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

Traces ajudam a acompanhar uma requisição passando por vários serviços — essencial em sistemas distribuídos, onde um log isolado não mostra o caminho completo de uma falha.

### Na prática (OpenTelemetry)

```txt
um trace ID único é gerado na entrada da requisição
esse ID é propagado entre serviços via header (ex.: traceparent)
cada serviço cria spans (etapas) dentro do mesmo trace
logs e métricas referenciam o trace ID, permitindo correlacionar os 3 pilares
```

OpenTelemetry é o padrão vendor-neutral para instrumentar logs, métricas e traces — evita prender a instrumentação a um fornecedor específico (a ferramenta que recebe os dados pode trocar sem reescrever a instrumentação no código).

---

## Checklist

- [ ] Erros importantes geram logs?
- [ ] Logs não vazam dados sensíveis?
- [ ] Existem métricas mínimas?
- [ ] Tempo de resposta é observável?
- [ ] Falhas externas são rastreáveis?
- [ ] Uma requisição pode ser seguida de ponta a ponta por um trace ID, mesmo passando por mais de um serviço?
- [ ] Logs e traces podem ser correlacionados (mesmo ID em ambos)?

