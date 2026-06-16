# Uso Responsável de IA no Desenvolvimento

IA hoje não é só autocomplete. Existem pelo menos três níveis de uso, e cada um exige um tipo de supervisão diferente:

```txt
1. Autocomplete: sugestão de linha/trecho, aceita ou não na hora.
2. Assistente de chat: você pergunta, copia, cola e adapta manualmente.
3. Agente autônomo: a IA planeja, executa múltiplos passos, roda comandos,
   edita vários arquivos, usa ferramentas (terminal, git, browser, MCP)
   e só reporta o resultado — sem você ler cada linha antes de rodar.
```

A maior parte dos riscos relevantes hoje está no nível 3. Esse documento foca nele, mas as práticas de revisão valem para os três.

---

## Desenvolvimento agêntico

Um agente que executa código, comandos e mudanças em múltiplos arquivos precisa ser tratado como um colaborador júnior com acesso amplo: produtivo, mas que precisa de limites claros e checagem proporcional ao risco da ação.

### Reversibilidade decide o nível de supervisão

```txt
Baixo risco (deixe agir e revise depois):
  editar arquivo local, rodar testes, ler código, criar branch.

Alto risco (peça plano antes e confirme antes de executar):
  git push --force, deletar branch/tabela, rodar migration em produção,
  alterar permissões/infra compartilhada, enviar mensagem/e-mail,
  instalar ou remover dependências, mexer em CI/CD.
```

### Boas práticas

- peça um plano antes de mudanças grandes ou de múltiplos arquivos, e aprove o plano antes da execução;
- dê ao agente o menor escopo de permissão necessário (arquivos, comandos, credenciais) — não rode com acesso total "porque é mais prático";
- revise o diff final como revisaria um PR de humano, não apenas leia o resumo que o agente escreveu sobre o que fez;
- exija testes (existentes ou novos) como rede de segurança para mudanças autônomas — é o que permite confiar em execução rápida;
- mantenha instruções de projeto atualizadas (ex.: `CLAUDE.md`, regras de contribuição) — é o contexto que guia decisões do agente quando você não está olhando;
- audite ações irreversíveis: se o agente rodou um comando destrutivo, deve ter pedido confirmação antes;
- desconfie de "deu tudo certo" sem evidência — peça para o agente mostrar o que rodou e o resultado, não só afirmar sucesso.

---

## IA no pipeline (além do uso manual no editor)

```txt
geração de testes a partir de especificação
revisão de PR assistida por IA (sinaliza, não aprova sozinha)
geração de documentação a partir do código
triagem inicial de bugs/issues
resumo de mudanças para changelog
```

Em todos os casos: IA assina sugestão, humano assina merge. Gate de CI automatizado por IA nunca deve ser o único revisor antes de produção.

---

## AppSec de IA (quando o produto usa LLM como funcionalidade)

Diferente de "usar IA para programar" — isso é para quando seu sistema integra um LLM como parte do produto (chat, agente, RAG, function calling).

```txt
Prompt injection direto: usuário tenta manipular o comportamento via input.
Prompt injection indireto: instrução maliciosa escondida em um documento,
  e-mail, página web ou resultado de busca que o LLM processa.
Insecure output handling: tratar a resposta do LLM como segura por padrão
  e usá-la direto em SQL, shell, HTML ou chamada de API.
Excessive agency: dar ao agente ferramentas/permissões além do necessário
  para a tarefa (ex.: acesso de escrita quando só precisa de leitura).
Vazamento de dados sensíveis via prompt, contexto recuperado (RAG) ou logs.
Negação de serviço por uso de tokens/custo descontrolado.
```

Referência: OWASP Top 10 for LLM Applications.

### Checklist AppSec de IA

- [ ] Toda saída do LLM que vira ação (SQL, comando, chamada de API, HTML) é validada/sanitizada antes de executar.
- [ ] Ferramentas expostas ao agente seguem privilégio mínimo (ex.: leitura em vez de escrita quando possível).
- [ ] Conteúdo externo (documentos, páginas, e-mails) processado pelo LLM é tratado como entrada não confiável, igual a input de usuário.
- [ ] Dados sensíveis não entram no prompt/contexto sem necessidade.
- [ ] Há limite de custo/uso (rate limit, orçamento de tokens) para evitar abuso.
- [ ] Ações irreversíveis disparadas pelo agente exigem confirmação humana.

---

## Riscos gerais (qualquer nível de uso)

```txt
código inseguro
dependência inexistente ou desatualizada (hallucination de pacote)
solução mais complexa do que o problema exige
confiança excessiva sem verificação
vazamento de dados em prompt ou log
```

---

## Checklist geral

- [ ] Entendi o que foi gerado/executado, não só aceitei?
- [ ] O comportamento foi testado, não só lido?
- [ ] Segurança foi revisada (entrada, saída, permissões)?
- [ ] Dados sensíveis não foram expostos no prompt, contexto ou log?
- [ ] Mudanças irreversíveis tiveram plano e confirmação antes de rodar?
- [ ] O agente operou com o menor escopo de permissão necessário?
- [ ] O resultado combina com o padrão do projeto?
