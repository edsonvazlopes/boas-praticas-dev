# Clean Code

Clean Code é a prática de escrever código claro, simples, direto e fácil de manter.

O objetivo não é seguir estética pessoal. O objetivo é reduzir ambiguidade e custo de manutenção.

---

## Princípios

- nomes devem revelar intenção;
- funções devem ser pequenas;
- comentários devem explicar decisões, não repetir o óbvio;
- código duplicado deve ser analisado;
- erros devem ser tratados explicitamente;
- regras de negócio devem ser fáceis de localizar;
- dependências devem ser claras.

---

## Exemplo ruim

```js
function calc(x, y, z) {
  if (z === 1) return x + y;
  if (z === 2) return x - y;
  return 0;
}
```

## Exemplo melhor

```js
function calcularTotal(valorBase, taxa) {
  return valorBase + taxa;
}

function calcularDesconto(valorBase, desconto) {
  return valorBase - desconto;
}
```

---

## Nomes

Nomes devem explicar intenção, sem depender de comentário para isso.

- [ ] O nome revela o propósito?
- [ ] Evita abreviações desnecessárias?
- [ ] Está coerente com o vocabulário do projeto?

---

## Funções pequenas

Uma função deve fazer uma coisa principal e fazer bem. Sinais de alerta:

```txt
função longa demais
muitos níveis de if
muitos parâmetros
mistura validação, regra, banco e resposta
nome genérico como processar(), executar(), handle()
```

---

## Tratamento de erros

- validar entradas cedo;
- retornar mensagens úteis;
- não vazar detalhes internos para o usuário;
- registrar informações suficientes para diagnóstico;
- diferenciar erro esperado de erro inesperado.

---

## Refatoração

Refatorar é melhorar a estrutura sem alterar o comportamento externo. Antes de refatorar:

- tenha testes ou checklist manual;
- entenda o comportamento atual;
- faça mudanças pequenas;
- valide depois de cada etapa.

---

## Checklist

- [ ] O código pode ser lido sem decifração?
- [ ] Os nomes são específicos e revelam intenção?
- [ ] Funções fazem uma coisa principal?
- [ ] Não há comentários óbvios?
- [ ] Não há duplicação perigosa?
- [ ] O fluxo principal é visível?
- [ ] Entradas são validadas e erros são tratados de forma previsível?
- [ ] O código pode ser mantido por outra pessoa?

