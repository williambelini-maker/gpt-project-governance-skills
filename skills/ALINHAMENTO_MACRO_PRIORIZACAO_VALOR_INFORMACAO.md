# Skill — Alinhamento Macro, Priorização e Valor de Informação

`SKILL_ROLE = CORE`

Pergunta central: **o que vale perseguir agora e qual resultado realmente move o objetivo?**

Use quando houver múltiplas frentes/hipóteses, risco de subotimização local, necessidade de repriorizar, avaliar valor de informação ou decidir stop produtivo.

## Gate epistemológico antes de priorizar

Prioridade não pode ser calculada sobre premissa material não verificada como se fosse fato.

```text
PRIORITY_INPUT_GATE
WHICH_CLAIMS_DRIVE_THE_RANKING?
EPISTEMIC_STATUS?
EVIDENCE?
IF_FALSE_DOES_PRIORITY_CHANGE?
```

Se uma claim em `UNKNOWN`, `HYPOTHESIS` ou `CONFLICT` altera materialmente a ordem das frentes:

```text
NEXT_PRIORITY = VALIDATE_THE_PREMISE
```

Se validação imediata for impossível, marque a prioridade como `PROVISIONAL` e mantenha a incerteza explícita. Não use plausibilidade como confirmação.

## Core

Trabalhe de trás para frente:

```text
OBJETIVO MACRO
<- DECISÃO NECESSÁRIA
<- INFORMAÇÃO NECESSÁRIA
<- PERGUNTA
<- INVESTIGAÇÃO
```

Toda frente relevante deve conseguir mostrar:

```text
MACRO_LINK
BLOCKER_OR_QUESTION
EXPECTED_INFORMATION
IF_PASS_WHAT_CHANGES
IF_NOGO_WHAT_CHANGES
DECISION_AFFECTED
COST
```

Se PASS e NOGO levam praticamente ao mesmo estado macro, `VALUE_OF_INFORMATION = LOW`.

## Anti-túnel

A frente herdada do `STATUS` não ganha prioridade apenas por ser a frente atual.

Antes de aprofundar:

```text
LOAD_MACRO_STATE
-> IDENTIFY_ACTIVE_FRONTS
-> EXPLAIN_WHY_THIS_FRONT_NOW
-> CHECK_NEW_RESULTS/UNLOCKS
-> CHECK_STOP/REPRIORITIZATION_TRIGGERS
-> CONFIRM_OR_CHANGE_PRIORITY
```

Se o agente sabe o `NEXT` mas não consegue explicar por que a frente domina alternativas, deve voltar ao owner macro antes de produzir trabalho material.

## Classifique o resultado

```text
MACRO           -> muda tese, decisão, blocker ou capacidade central
MESO            -> fecha dependência necessária para avanço macro
LOCAL           -> melhora interna sem mudança macro material
INFRASTRUCTURAL -> melhora capacidade de executar, não o conhecimento por si só
```

Não promover runtime, cobertura, precisão ou volume de resultados a ganho macro sem cadeia causal.

## Prioridade

Prefira, nesta ordem qualitativa:

1. mudança de decisão macro;
2. remoção de blocker;
3. falsificação de hipótese central;
4. redução do espaço de modelos/decisões;
5. valor de informação e centralidade;
6. custo e reversibilidade.

Pergunte sempre:

```text
WHAT_DECISION_CHANGES?
WHAT_UNCERTAINTY_DROPS?
WHAT_BRANCH_CAN_DIE?
WHAT_BECOMES_ENABLED?
```

## Stop produtivo

Pare/rebaixe uma frente quando:

- a pergunta útil já foi respondida;
- o valor marginal caiu abaixo de alternativas;
- o restante é refinamento sem impacto material;
- PASS/NOGO não mudariam decisão;
- nova evidência tornou a frente redundante.

Tempo já investido não aumenta prioridade futura.

## Após resultado material

```text
UPDATE_GRAPH
-> BLOCKERS/HYPOTHESES
-> RESULT_CLASS
-> MACRO_STATUS
-> PRIORITIES
-> INTEGRATION_DEBT
-> NEXT
```

Resultado validado mas não integrado ao estado macro permanece com dívida de integração.

## Saída mínima útil

```text
MACRO_OBJECTIVE
CURRENT_MACRO_STATE
MATERIAL_DECISION_PREMISES + EPISTEMIC_STATUS
DOMINANT_BLOCKER
ACTIVE_FRONTS
CURRENT_PRIORITY_FRONT
WHY_THIS_FRONT_NOW
NEW_RESULT + CLASS
MACRO_IMPACT
UNCERTAINTY_REMOVED
MARGINAL_VALUE
STOP/REPRIORITIZATION_TRIGGER
NEXT_PRIORITY
```

## Referência sob demanda

Consulte `references/ALINHAMENTO_MACRO_PRIORIZACAO_VALOR_INFORMACAO_REFERENCIA.md` apenas quando precisar de formalização aprofundada de VOI, portfólio de investigações, centralidade, proxy trap, maturidade de hipóteses ou critérios detalhados de abertura/fechamento.

> Profundidade local só vale enquanto aumenta o estado macro do conhecimento ou da decisão.
