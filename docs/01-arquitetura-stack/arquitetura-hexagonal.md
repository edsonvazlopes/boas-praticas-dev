# Arquitetura Hexagonal

Arquitetura Hexagonal, também chamada de Ports and Adapters, organiza o sistema em torno do domínio.

O núcleo do sistema define portas. Adaptadores externos conectam banco, APIs, interface, filas e outros serviços.

---

## Componentes

```txt
Domínio: regra central.
Portas: contratos que o domínio usa ou expõe.
Adaptadores: implementações concretas para banco, HTTP, e-mail, fila etc.
```

---

## Exemplo

```txt
Caso de uso: CriarUsuario
Porta: UsuarioRepository
Adaptador: PostgresUsuarioRepository
Interface: rota POST /usuarios
```

---

## Quando usar

- sistemas com regra de negócio relevante;
- aplicações que precisam ser testáveis;
- projetos que podem trocar infraestrutura;
- sistemas que integram muitos serviços externos.

---

## Checklist

- [ ] O domínio está no centro?
- [ ] Banco, HTTP e serviços externos estão fora do domínio?
- [ ] Existem contratos claros?
- [ ] Adaptadores podem ser trocados?
- [ ] Testes podem usar implementações falsas?

