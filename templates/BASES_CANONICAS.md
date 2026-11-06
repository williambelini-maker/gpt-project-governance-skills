# Bases canônicas

`DOCUMENT_ROLE = KNOWLEDGE_BASE_INDEX`

Use em projetos onde conhecimento consolidado sustenta múltiplas frentes. Não transformar em relatório narrativo.

## Base B001 — <título>

```text
BASE_ID = B001
CLAIM_OR_CAPABILITY = <o que está estabelecido>
STATUS = ACTIVE | SUPERSEDED | LIMITED
OWNER = <documento/evidência canônica>
VALIDITY_SCOPE = <onde vale>
EVIDENCE = <ponteiros>
WHAT_IT_ENABLES = <capacidades/frentes>
WHAT_DEPENDS_ON_IT = <IDs/frentes/decisões>
LAST_RECONCILED_AT = <timestamp>
```

### Impacto de resultado novo

```text
STRENGTHENED_BY = <resultado ou NONE>
WEAKENED_BY = <resultado ou NONE>
SUPERSEDED_BY = <base/decisão ou NONE>
```

## Regra

Nova frente deve apontar para bases aplicáveis. Resultado relevante deve declarar se fortalece, limita, especializa ou supersede alguma base.
