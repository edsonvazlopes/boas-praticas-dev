# Entrega Progressiva

Publicar uma versão para 100% dos usuários de uma vez é a forma mais arriscada de fazer deploy. Entrega progressiva reduz o impacto de um problema, liberando a mudança aos poucos e observando antes de continuar.

---

## Estratégias

```txt
feature flag: liga/desliga funcionalidade sem novo deploy
canary release: nova versão recebe uma fatia pequena do tráfego primeiro
blue-green: dois ambientes idênticos, troca de tráfego é instantânea
rolling update: substitui instâncias antigas gradualmente
dark launch: funcionalidade ativa em produção, mas invisível ao usuário
```

---

## Quando usar o quê

- **feature flag**: mudanças de comportamento que precisam ser ligadas/desligadas rápido, sem depender de pipeline;
- **canary**: mudanças de infraestrutura/runtime onde vale validar com tráfego real antes de liberar geral;
- **blue-green**: quando rollback instantâneo é prioridade e manter dois ambientes é viável;
- **rolling update**: padrão em orquestradores (Kubernetes) para evitar downtime.

---

## Critério para avançar a liberação

```txt
taxa de erro não subiu
tempo de resposta não degradou
métricas de negócio (conversão, etc.) não pioraram
nenhum alerta crítico disparou
```

Se qualquer critério falhar, reverte automaticamente ou trava a expansão — não espera alguém perceber manualmente.

---

## Checklist

- [ ] Mudanças de comportamento relevantes podem ser desligadas sem novo deploy?
- [ ] Existe critério objetivo (métrica) para expandir um rollout, não só "parece que está ok"?
- [ ] Rollback é mais rápido que esperar o próximo deploy corrigir?
- [ ] Feature flags antigas são removidas depois que a funcionalidade estabiliza?

Ver também: [deploy-rollback.md](deploy-rollback.md), [metricas-dora.md](metricas-dora.md).
