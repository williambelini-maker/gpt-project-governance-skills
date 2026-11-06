# Estado macro atual

`DOCUMENT_ROLE = LIVE_MACRO_STATE`

`LAST_RECONCILED_AT = YYYY-MM-DDTHH:MM:SS±HH:MM`

## Orientação

`MACRO_OBJECTIVE = <objetivo maior que governa as frentes>`

`MACRO_PHASE = <fase estratégica>`

`CURRENT_MACRO_THESIS = <estado resumido do entendimento/estratégia>`

`LAST_MACRO_BINDING_RESULT = <resultado que mudou materialmente o estado macro ou NONE>`

`DOMINANT_MACRO_BLOCKER = <blocker estratégico ou NONE>`

## Portfólio de frentes

`CURRENT_PRIORITY_FRONT = <ID/nome>`

`WHY_THIS_FRONT_NOW = <por que esta frente domina alternativas agora>`

`DECISION_AFFECTED = <decisão macro que a frente informa ou habilita>`

`EXPECTED_INFORMATION_OR_CAPABILITY = <o que esta frente deve produzir>`

`EXPECTED_MACRO_EFFECT = <o que muda se PASS/NOGO/resultado material>`

`STOP_OR_REPRIORITIZATION_TRIGGERS = <condições objetivas>`

### Outras frentes relevantes

- `F001` — <estado + prioridade + razão curta>
- `F002` — <estado + prioridade + razão curta>

### Frentes adiadas/encerradas relevantes

- <frente> — <razão + condição de reabertura, se houver>

## Mudanças macro recentes

`RECENT_MACRO_CHANGE = <mudança material ou NONE>`

`NEWLY_ENABLED_CAPABILITIES = <capacidades/frentes habilitadas ou NONE>`

`PENDING_MACRO_PROPAGATIONS = <lista ou NONE>`

## Ponteiros

`CURRENT_FRONT_STATUS = <STATUS.md ou caminho>`

`KNOWLEDGE_MAP = <MAPA_DE_CONHECIMENTO.md ou N/A>`

`CANONICAL_BASES = <BASES_CANONICAS.md ou N/A>`

`SPEC_CONTRACT = <CONTRATO_ESPECIFICACOES.md ou N/A>`

`REUSABLE_ASSETS = <ATIVOS_REUTILIZAVEIS.md ou N/A>`

## Gate de continuidade

Um novo agente sem memória deve conseguir responder, somente com owners vivos:

```text
WHAT_ARE_WE_TRYING_TO_ACHIEVE?
WHERE_ARE_WE_MACROSCOPICALLY?
WHICH_FRONTS_EXIST?
WHY_IS_THIS_FRONT_PRIORITY_NOW?
WHAT_RESULT_WOULD_CHANGE_PRIORITY?
WHAT_WOULD_STOP_OR_REPRIORITIZE_IT?
WHERE_IS_THE_LOCAL_STATE?
```

Se não conseguir, o estado macro está insuficiente.

> Estado estratégico vivo, não histórico. Não duplicar evidência completa nem detalhes operacionais da frente.
