# Dados

Todo projeto minimamente sério precisa pensar em dados, mesmo quando parece ser apenas um site simples.

---

## Perguntas essenciais

```txt
Quais dados existem?
Onde ficam?
Quem pode acessar?
Tem backup?
Tem exportação?
Tem retenção?
Tem dado pessoal?
```

Em sistemas como plataformas financeiras, acadêmicas ou canais privados, esse pilar é central.
Em sites públicos, ele aparece em formulários de contato, analytics, newsletter e cookies — ver [privacidade-lgpd.md](../02-seguranca-appsec/privacidade-lgpd.md) para a parte legal/consentimento desses dados.

---

## Modelagem

- entidades principais mapeadas antes de criar tabelas;
- relacionamentos e cardinalidade definidos;
- escolha de banco (relacional, documento, chave-valor) justificada pelo caso de uso, não por modismo;
- migrações versionadas e reversíveis.

---

## Checklist

- [ ] Os dados coletados foram listados.
- [ ] As entidades principais foram mapeadas.
- [ ] Foi definido onde os dados serão armazenados.
- [ ] Foi definido quem pode acessar os dados.
- [ ] Existe política de backup.
- [ ] Existe política de retenção ou exclusão.
- [ ] Foi verificado se há dados pessoais ou sensíveis.
- [ ] Existe possibilidade de exportar ou migrar os dados.
- [ ] Migrações são versionadas.
