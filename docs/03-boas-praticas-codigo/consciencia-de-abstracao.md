# Consciência de Abstração

Toda dependência ou framework que você adota é um contrato que você não escreveu e não controla totalmente. Isso não é motivo para evitar frameworks — é motivo para saber exatamente o que está sendo delegado antes de confiar nele.

Diferença em relação a KISS: KISS é sobre *a sua solução* ser simples. Consciência de abstração é sobre não delegar controle sem entender o que está sendo delegado — mesmo usando uma ferramenta complexa por baixo.

---

## Perguntas antes de confiar numa abstração

```txt
O que essa biblioteca/ORM/middleware faz de fato, por baixo?
Quais são os valores padrão (timeout, retry, pool de conexão, cache)?
O que acontece quando ela falha — falha silenciosa ou explícita?
Dá para ver o que ela gera (SQL, request, log) quando preciso depurar?
Existe uma saída de emergência (raw query, fetch direto) se a abstração travar?
```

Se a resposta para "dá para ver o que ela gera" for não, isso é um risco conhecido, não um detalhe menor.

---

## Antes de adicionar uma dependência nova

```txt
O problema é grande o suficiente para justificar uma dependência,
  ou a plataforma/linguagem já resolve isso nativamente?
Quantas dependências transitivas ela traz junto?
Ela é mantida ativamente? Quando foi o último release?
O que acontece se ela for descontinuada — dá para trocar sem reescrever tudo?
```

Preferir a biblioteca padrão ou um recurso nativo da plataforma quando o problema é pequeno reduz superfície de risco — tanto de bug quanto de segurança (ver [supply-chain-security.md](../02-seguranca-appsec/supply-chain-security.md)).

---

## Na prática

- ler a documentação do que um ORM gera (não assumir que a query está otimizada);
- saber o timeout e a política de retry padrão de qualquer cliente HTTP/banco usado;
- não copiar boilerplate de um tutorial sem entender cada linha;
- testar o comportamento de falha de uma dependência crítica, não só o caminho feliz (ver [testes-contrato-resiliencia.md](../04-qualidade-testes/testes-contrato-resiliencia.md));
- documentar decisões de framework/biblioteca relevantes como ADR (ver [adr-decisoes-arquiteturais.md](../01-arquitetura-stack/adr-decisoes-arquiteturais.md)), incluindo o que se abriu mão de controlar.

---

## Checklist

- [ ] Para as dependências centrais do projeto, sei o que elas fazem por baixo, não só a API que exponho?
- [ ] Sei os valores padrão (timeout, retry, cache) das integrações críticas?
- [ ] Existe uma saída de emergência se a abstração principal falhar ou for descontinuada?
- [ ] Dependências novas foram avaliadas quanto a necessidade real, não só conveniência?
- [ ] As decisões de adotar uma abstração complexa estão documentadas (ADR), com o trade-off explícito?
