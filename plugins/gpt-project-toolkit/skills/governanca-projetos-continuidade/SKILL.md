---
name: governanca-projetos-continuidade
description: Governe trabalho material em repositórios e projetos existentes usando fonte da verdade, estado macro/local, owners, contratos, continuidade, propagação e handoff. Use ao continuar, modificar, implementar, analisar, documentar, organizar ou entregar trabalho que dependa do estado de um projeto/repositório, inclusive em novos chats sem memória; coordene outras skills sem substituir suas competências de domínio. Não use para perguntas soltas ou tarefas independentes que não dependam do contexto do projeto.
---

# Governança de Projetos e Continuidade

Use esta skill para **orientar trabalho material dentro de um repositório/projeto existente antes de aprofundar ou alterar uma frente**.

## Escopo de ativação

Considere esta skill quando a tarefa depender materialmente do estado existente do projeto, por exemplo:

- continuar trabalho anterior;
- modificar código, documentação, dados, análises ou arquitetura já pertencentes ao projeto;
- implementar nova funcionalidade dentro de um repositório existente;
- produzir entregável que deva respeitar owners, contrato, estado ou estrutura do projeto;
- investigar bug, blocker, resultado ou inconsistência existente;
- organizar/reconciliar artefatos do projeto;
- preparar entrega, handoff ou próxima ação;
- coordenar skills de domínio dentro do mesmo projeto.

Não a force em pergunta factual isolada, brainstorming independente, texto avulso ou tarefa que não dependa do estado/cânone de um projeto.

```text
PROJECT_CONTEXT_MATERIAL?
YES -> GOVERNANCE_CONTEXT_REQUIRED
NO  -> DO_NOT_FORCE_GOVERNANCE
```

## Regra de autoridade

Leia `references/COORDENACAO_SKILLS.md`. Instrução explícita, contrato, owners e evidência do projeto prevalecem sobre esta skill.

## Gate epistemológico

Antes de aceitar diagnóstico, causa, prioridade ou NEXT:

```text
WHAT_MATERIAL_CLAIMS_DRIVE_THIS?
STATUS = UNKNOWN | HYPOTHESIS | SUPPORTED | VERIFIED | FALSIFIED | CONFLICT
WHAT_EVIDENCE?
WHAT_SOURCE_OR_TEST?
IF_FALSE_DOES_THE_DECISION_CHANGE?
```

Se uma claim material não validada muda a decisão, a investigação dessa claim precede o trabalho consequente.

```text
HYPOTHESIS -> VALIDATE -> EVIDENCE -> DECIDE
```

Nunca:

```text
HYPOTHESIS -> ASSUME_TRUE -> PROPAGATE
```

Leia `references/VALIDACAO_PREMISSAS_E_EVIDENCIA.md` quando houver dúvida de suficiência, causalidade ou conflito.

## Fechamento de descoberta material

Detectar inconsistência ou obsolescência não é conclusão suficiente quando a investigação está ao alcance do agente.

```text
MATERIAL_FINDING
-> AUTHORITATIVE_CURRENT_SOURCE
-> OLD_VS_CURRENT
-> MATERIAL_DEPENDENTS
-> BOUND_IMPACT
-> RECONCILE_AFFECTED_OWNERS
-> REPORT_EVIDENCE_AND_RESOLVED_RESULT
```

```text
DO_NOT_DELEGATE_VERIFICATION_TO_USER
WHEN_AGENT_CAN_VERIFY_DIRECTLY
```

A investigação deve ser causalmente limitada: seguir owner, referências diretas e dependentes materiais e parar quando o impacto estiver delimitado. Só deixar a verificação em aberto quando houver bloqueio real de acesso, ferramenta, dado ou autoridade.

## Cold start

1. Identifique escopo e faça inventário raso.
2. Leia README/entrada e owners.
3. Leia o owner de estado macro.
4. Leia o STATUS da frente corrente.
5. Identifique e valide premissas materiais que sustentam diagnóstico/prioridade/NEXT.
6. Carregue bases/contrato/mapa apenas quando apontados ou necessários.
7. Execute o anti-tunnel gate.
8. Só então produza.

```text
READ_UNTIL_GLOBALLY_ORIENTED_AND_LOCALLY_ACTIONABLE
```

## Anti-tunnel gate

Antes de aprofundar materialmente:

```text
MACRO_OBJECTIVE_KNOWN?
CURRENT_MACRO_STATE_KNOWN?
CURRENT_FRONT_IDENTIFIED?
WHY_THIS_FRONT_NOW_KNOWN?
EXPECTED_MACRO_EFFECT_KNOWN?
STOP_OR_REPRIORITIZATION_TRIGGER_KNOWN?
IS_CURRENT_FRONT_STILL_JUSTIFIED?
```

O NEXT herdado não é autojustificado.

## Fonte da verdade

Classifique a informação, encontre owner, autoridade/supersessão e evidência. Não escolha verdade por nome, mtime ou primeiro arquivo encontrado.

## Mudança material

```text
WHAT_CHANGED
-> CLAIMS_CHANGED
-> OWNERS
-> DEPENDENTS
-> MACRO_IMPACT
-> PROPAGATE
-> VERIFY
```

## Handoff

Outro agente sem memória deve conseguir explicar objetivo macro, estado macro, frente prioritária, razão da prioridade, gatilhos de stop/repriorização, estado local, evidência e NEXT.

## Quando carregar referências

- `references/FUNDAMENTOS.md`: princípios universais.
- `references/POLITICA_DOCUMENTAL.md`: governança/owners.
- `references/MAPA_DOCUMENTAL.md`: dependências documentais.
- `references/MATRIZ_FONTE_DA_VERDADE.md`: conflito de owners.
- `references/PROTOCOLO_HANDOFF.md`: fechamento/propagação/handoff.
- `references/GUIA_NOVO_CHAT.md`: recuperação expandida.
- `references/BOOT_NOVO_CHAT.md`: sequência de cold start.

Use os templates em `assets/templates/` somente quando o projeto justificar o owner correspondente.