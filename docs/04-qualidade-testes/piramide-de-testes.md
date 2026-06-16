# Pirâmide de Testes

A pirâmide de testes ajuda a equilibrar custo, velocidade e confiança.

---

## Camadas

```txt
Base: muitos testes unitários.
Meio: alguns testes de integração.
Topo: poucos testes end-to-end.
```

---

## Testes unitários

Testam pequenas partes isoladas, como funções, regras e serviços.

São rápidos e ajudam a localizar erro com precisão.

---

## Testes de integração

Testam a comunicação entre partes, como API e banco.

São mais lentos, mas verificam cenários mais reais.

---

## Testes end-to-end

Simulam o uso real do sistema.

São úteis para fluxos críticos, mas não devem cobrir tudo.

---

## Checklist

- [ ] Regras importantes têm teste unitário?
- [ ] Integrações críticas foram testadas?
- [ ] Fluxos principais têm teste E2E ou checklist manual?
- [ ] Testes são executáveis por comando?
- [ ] Testes não dependem de ordem escondida?

Ver também: [testes-contrato-resiliencia.md](testes-contrato-resiliencia.md) e [testabilidade.md](testabilidade.md).

