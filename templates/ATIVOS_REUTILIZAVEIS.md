# Ativos reutilizáveis

`DOCUMENT_ROLE = REUSABLE_ASSET_INDEX`

Promova para cá recursos com valor recorrente que não devem ficar enterrados em histórico.

## Ativo A001 — <título>

```text
ASSET_ID = A001
TYPE = SEARCH_QUERY | PROMPT | DERIVATION | CHECK | SCRIPT | DATASET | METHOD | BENCHMARK
PURPOSE = <para que serve>
OWNER_OR_PATH = <caminho>
RELATED_BASES = <IDs ou NONE>
RELATED_FRONTS = <IDs ou NONE>
WHAT_IT_RESOLVES = <pergunta/capacidade>
WHAT_REMAINS_OPEN = <lacuna>
REUSABLE_WHEN = <gatilho>
STATUS = ACTIVE | SUPERSEDED | LIMITED
```

## Reuse gate

Antes de nova busca/derivação/implementação semelhante:

```text
EXISTING_ASSET_MATCH?
CAN_REUSE_DIRECTLY?
CAN_EXTEND?
WHAT_NEW_GAP_JUSTIFIES_NEW_WORK?
```

Busca ou prompt novo sem lacuna nova demonstrável deve ser evitado.
