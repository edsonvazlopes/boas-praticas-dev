# Testes de Contrato e Resiliência

A pirâmide de testes clássica (unitário/integração/E2E) testa se o sistema funciona como esperado. Testes de contrato e resiliência testam o que acontece quando as integrações mudam ou falham — essencial em qualquer sistema com mais de um serviço.

---

## Testes de contrato

Garantem que dois serviços (ou frontend e API) continuam compatíveis sem precisar de um ambiente E2E completo rodando os dois juntos.

```txt
consumidor define o contrato esperado (schema, campos, tipos)
provedor roda esse contrato no próprio pipeline antes de publicar
quebra de contrato falha o build do provedor, antes de chegar em produção
```

Ferramentas comuns: Pact, schemas OpenAPI/JSON Schema validados em CI.

---

## Testes de resiliência (chaos engineering)

Verificam se o sistema se comporta de forma aceitável quando uma dependência falha — em vez de descobrir isso durante um incidente real.

```txt
o que acontece se o banco ficar lento?
o que acontece se uma API externa cair?
o que acontece se a fila travar?
o sistema degrada graciosamente ou quebra tudo?
```

Não precisa começar com ferramentas sofisticadas de chaos engineering em produção — começa testando timeout, retry e fallback em ambiente controlado, e evolui a partir daí.

---

## Checklist

- [ ] Mudança de contrato entre serviços/API é detectada antes de produção?
- [ ] Toda chamada externa tem timeout definido?
- [ ] Existe retry com backoff para falhas transitórias?
- [ ] Existe fallback definido para quando uma dependência externa cai?
- [ ] Já foi testado o que acontece se uma dependência crítica ficar indisponível?

Ver também: [piramide-de-testes.md](piramide-de-testes.md), [testabilidade.md](testabilidade.md).
