# Premissas, hipóteses e evidências

`DOCUMENT_ROLE = EPISTEMIC_STATE`

Use apenas quando houver premissas abertas materiais suficientes para justificar owner próprio. Em projetos simples, registre somente as premissas materiais no STATUS.

## H001 — <afirmação>

```text
CLAIM_ID = H001
CLAIM = <afirmação exata>
STATUS = UNKNOWN | HYPOTHESIS | SUPPORTED | VERIFIED | FALSIFIED | CONFLICT
SCOPE = <onde a afirmação vale>
SOURCE_ORIGIN = <owner/dado/teste/fonte/inferência>
EVIDENCE = <ponteiros ou NONE>
ALTERNATIVES = <explicações concorrentes ou NONE>
DECISIONS_DEPENDING_ON_IT = <IDs/decisões ou NONE>
IF_FALSE_EFFECT = <o que muda se estiver errada>
VALIDATION_PLAN = <teste/pesquisa/inspeção ou NONE>
EVIDENCE_NEEDED = <lacuna ou NONE>
LAST_REVIEWED_AT = <timestamp>
```

## Gate

Uma claim em `UNKNOWN`, `HYPOTHESIS` ou `CONFLICT` não pode ser usada silenciosamente como premissa material.

Se uma decisão muda conforme a claim:

```text
VALIDATE_FIRST
```

## Promoção

`HYPOTHESIS -> SUPPORTED/VERIFIED` exige evidência rastreável.

Não promover por repetição, plausibilidade ou confiança verbal do agente.
