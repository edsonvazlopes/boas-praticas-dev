# Health Check

Health check é um endpoint ou mecanismo para verificar se o sistema está funcionando.

---

## Exemplo

```txt
GET /api/health
```

Resposta esperada:

```json
{
  "status": "ok",
  "database": "ok",
  "version": "1.0.0"
}
```

---

## O que verificar

- aplicação responde;
- banco está acessível;
- serviços essenciais estão disponíveis;
- versão atual está identificada;
- tempo de resposta está aceitável.

---

## Checklist

- [ ] Existe health check quando o sistema justifica?
- [ ] O health check não expõe dados sensíveis?
- [ ] Banco ou dependências críticas são verificadas?
- [ ] Monitoramento pode usar esse endpoint?
- [ ] A resposta é simples e estável?

