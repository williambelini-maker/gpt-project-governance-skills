# Contrato vigente de especificações

`DOCUMENT_ROLE = SPEC_CONTRACT`

Use somente quando o projeto tiver requisitos/invariantes suficientes para justificar owner próprio. Estado vivo, não transcrição de conversa.

## Vigentes

```text
SPEC_ID = S001
TYPE = REQUIREMENT | INVARIANT | CONSTRAINT | ACCEPTANCE | PREFERENCE
STATEMENT = <o que deve permanecer verdadeiro>
PRIORITY = MUST | SHOULD | MAY
STATUS = ACTIVE | LOCKED | SUPERSEDED
SCOPE = <onde se aplica>
ACCEPTANCE = <como verificar>
DEPENDS_ON = <IDs/componentes ou NONE>
EVIDENCE = <ponteiro ou PENDING>
SUPERSEDED_BY = <ID ou NONE>
```

## Gate de mudança

```text
NEW_INPUT
-> ADD/MODIFY/SUPERSEDE SPEC
-> AFFECTED_SPECS
-> PRESERVED_INVARIANTS
-> ACCEPTANCE
-> PRODUCE
```

## Gate de entrega

```text
NEW_REQUIREMENTS = PASS?
AFFECTED_REQUIREMENTS = PASS?
INVARIANTS = PRESERVED?
REGRESSIONS = NONE_DETECTED?
UNRESOLVED_CONFLICTS = NONE?
```

Não revalidar tudo por padrão; use dependências para definir o conjunto materialmente afetado.
