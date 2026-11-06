# Status atual da frente

`LAST_RECONCILED_AT = YYYY-MM-DDTHH:MM:SS±HH:MM`

## Vínculo macro

`MACRO_STATUS_OWNER = <MACRO_STATUS.md | INLINE>`

`CURRENT_FRONT_ID = <ID/nome>`

`MACRO_LINK = <como esta frente contribui para o objetivo macro>`

`WHY_THIS_FRONT_NOW = <razão vigente da prioridade>`

`EXPECTED_MACRO_EFFECT = <o que muda no estado macro se houver resultado material>`

`REPRIORITIZATION_TRIGGER = <condição objetiva ou NONE>`

## Estado operacional

`CURRENT_PHASE = <fase>`

`CURRENT_OBJECTIVE = <objetivo desta frente>`

`CANONICAL_AUTHORITY = <ponteiro ou N/A>`

## Premissas e evidência

`EPISTEMIC_STATE_OWNER = <PREMISSAS_E_EVIDENCIAS.md | INLINE | N/A>`

`MATERIAL_PREMISES = <claims + status ou NONE>`

`UNVERIFIED_DECISION_DRIVERS = <claims ou NONE>`

`EVIDENCE_FOR_CURRENT_DECISION = <ponteiros ou NONE>`

`BLOCKED_BY_UNVERIFIED_PREMISE = <claim ou NONE>`

## Contrato vigente

`SPEC_CONTRACT_OWNER = <caminho ou INLINE/N/A>`

`ACTIVE_INVARIANTS = <IDs/resumo ou NONE>`

`CONTRACT_STATUS = SATISFIED | OPEN | CONFLICT | N/A`

## Bases/resultado

`ACTIVE_BASES = <IDs/caminhos ou NONE>`

`LAST_BINDING_RESULT = <resultado>`

`RESULT_STATUS = PASS | FAIL | INCONCLUSIVE | FAILED_EXECUTION | TIMEOUT | NOT_RUN`

`EVIDENCE = <ponteiro>`

## Bloqueadores

`ACTIVE_BLOCKERS = <lista ou NONE>`

## Propagação

`PENDING_PROPAGATIONS = <lista ou NONE>`

`INTEGRATION_DEBT = OPEN | NONE`

`UNLOCK_PROPAGATION_STATUS = PENDING | COMPLETE | N/A`

## Skills

`ACTIVE_SKILLS = <cores ou NONE>`

## Próxima ação

`NEXT_EXECUTABLE_ACTION = <ação concreta e verificável>`

## Apenas se materialmente relevantes

- `KNOWN_NOGOS = <escopo + evidência>`
- `OPEN_QUESTIONS = <perguntas>`
- `INCONSISTENCIES = <pendências>`
- `RECENT_GAINS = <ganhos verificados>`

## Regra anti-túnel

`NEXT_EXECUTABLE_ACTION` não é autojustificado. Antes de aprofundar materialmente esta frente, confirmar no owner macro que `WHY_THIS_FRONT_NOW` ainda procede, que nenhum resultado/desbloqueio mudou a prioridade e que nenhuma premissa material não validada está sustentando silenciosamente o NEXT.

> Estado vivo da frente, não ledger. Se um campo não ajuda retomada/decisão atual, não o mantenha por hábito.
