# Padrões de Projeto

Padrões de projeto são soluções recorrentes para problemas comuns de design de software.

Eles não devem ser usados para enfeitar o código. Devem ser usados quando resolvem um problema real de organização, extensão ou manutenção.

---

## Padrões úteis

```txt
Factory: cria objetos sem espalhar lógica de criação.
Strategy: troca comportamento sem vários ifs.
Adapter: adapta uma interface externa ao formato do sistema.
Repository: isola acesso a dados.
Observer: reage a eventos.
Decorator: adiciona comportamento sem alterar a classe principal.
Facade: simplifica acesso a um subsistema complexo.
```

---

## Quando usar

- quando existe variação real de comportamento;
- quando detalhes externos precisam ser isolados;
- quando uma responsabilidade está se repetindo;
- quando o código começa a depender demais de implementações concretas.

---

## Quando evitar

- quando o problema é simples;
- quando o padrão cria mais arquivos que clareza;
- quando a equipe não entende a abstração;
- quando o padrão foi usado apenas "porque é bonito".

---

## Checklist

- [ ] O padrão resolve um problema real?
- [ ] O código ficou mais claro?
- [ ] A abstração tem nome compreensível?
- [ ] O padrão não esconde regra importante?
- [ ] A equipe consegue manter essa estrutura?

