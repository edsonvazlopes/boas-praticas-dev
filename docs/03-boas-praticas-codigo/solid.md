# SOLID

SOLID é um conjunto de cinco princípios usados para criar código mais organizado, flexível e fácil de manter.

Ele não resolve todos os problemas de arquitetura, mas ajuda a evitar classes gigantes, dependências confusas e código difícil de testar.

---

## S - Single Responsibility Principle

Uma unidade de código deve ter um motivo principal para mudar.

Exemplo de violação:

```txt
Uma classe UsuarioService valida dados, salva no banco, envia e-mail e gera relatório.
```

Melhor:

```txt
UsuarioService coordena o caso de uso.
UsuarioRepository salva dados.
EmailService envia e-mail.
RelatorioUsuario gera relatório.
```

Checklist:

- [ ] A classe ou função tem uma responsabilidade clara?
- [ ] Ela muda por muitos motivos diferentes?
- [ ] Ela mistura regra de negócio com infraestrutura?

---

## O - Open/Closed Principle

O código deve estar aberto para extensão e fechado para modificação.

Isso significa que novas variações devem poder ser adicionadas sem quebrar código já validado.

Exemplo comum:

```txt
Trocar vários ifs por estratégias quando existem comportamentos intercambiáveis.
```

Use com cuidado: nem todo if precisa virar padrão de projeto.

---

## L - Liskov Substitution Principle

Uma implementação derivada deve poder substituir a base sem quebrar o comportamento esperado.

Violação típica:

```txt
Uma subclasse sobrescreve um método e passa a lançar erro em um caso que a classe base prometia suportar.
```

Checklist:

- [ ] A implementação respeita o contrato esperado?
- [ ] Quem usa a abstração precisa saber qual classe concreta está por trás?

---

## I - Interface Segregation Principle

Clientes não devem depender de métodos que não usam.

Prefira interfaces pequenas e específicas.

Ruim:

```txt
interface ImpressoraCompleta: imprimir, digitalizar, grampear, enviarFax
```

Melhor:

```txt
interface Impressora
interface Scanner
interface EnviadorDeFax
```

---

## D - Dependency Inversion Principle

Módulos de alto nível não devem depender diretamente de detalhes de baixo nível.

Regras de negócio devem depender de abstrações, não de detalhes como banco, framework ou API externa.

Exemplo:

```txt
CasoDeUso depende de UsuarioRepository.
PostgresUsuarioRepository implementa UsuarioRepository.
```

---

## Checklist SOLID

- [ ] Cada módulo tem responsabilidade clara?
- [ ] Existem abstrações úteis onde há variação real?
- [ ] As abstrações não estão exageradas?
- [ ] Implementações respeitam contratos?
- [ ] Interfaces são pequenas?
- [ ] Regras de negócio não dependem diretamente de framework?

