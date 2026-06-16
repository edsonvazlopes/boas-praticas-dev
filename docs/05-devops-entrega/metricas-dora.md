# Métricas DORA

As métricas DORA (DevOps Research and Assessment) medem a performance de entrega de software com dados, não opinião. É o jeito mais usado hoje para saber objetivamente se o processo de entrega está bom ou ruim.

---

## As 4 métricas

```txt
Lead time for changes: tempo entre o commit e ele estar rodando em produção.
Deployment frequency: com que frequência o time publica em produção.
Change failure rate: % de deploys que causam incidente/rollback.
Time to restore service (MTTR): tempo para recuperar de um incidente.
```

---

## Referência de patamares

```txt
Elite:  lead time < 1 hora     | deploy várias vezes ao dia | falha < 5%   | MTTR < 1 hora
Alto:   lead time 1 dia-1 sem. | deploy 1x/semana-1x/mês    | falha 5-10%  | MTTR < 1 dia
Médio:  lead time 1 sem.-1 mês | deploy 1x/mês-1x/6 meses   | falha 10-15% | MTTR < 1 semana
Baixo:  lead time > 1 mês      | deploy < 1x/6 meses        | falha > 15%  | MTTR > 1 semana
```

Esses números são referência (Google DORA / State of DevOps), não meta a perseguir cegamente — o objetivo é melhorar a tendência do seu próprio time ao longo do tempo.

---

## Como começar a medir

- **lead time**: timestamp do commit + timestamp do deploy já dá para calcular;
- **deployment frequency**: contar deploys de produção no período;
- **change failure rate**: contar deploys que geraram rollback/hotfix/incidente;
- **MTTR**: timestamp de início do incidente até confirmação de resolução.

---

## Checklist

- [ ] É possível saber quando um commit específico chegou em produção?
- [ ] Deploys de produção são registrados automaticamente?
- [ ] Incidentes/rollbacks causados por deploy são registrados como tal?
- [ ] As 4 métricas são revisadas periodicamente pelo time, não só calculadas uma vez?

Ver também: [entrega-progressiva.md](entrega-progressiva.md), [deploy-rollback.md](deploy-rollback.md).
