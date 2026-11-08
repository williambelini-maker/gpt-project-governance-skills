---
name: alinhamento-macro-priorizacao
description: Decida qual frente, hipótese, experimento ou investigação merece prioridade agora com base em objetivo macro, blockers, valor de informação, impacto causal, stop e repriorização. Use quando houver múltiplas frentes, risco de aprofundamento local, dúvida de P0, ganho local versus macro ou necessidade de escolher o próximo trabalho.
---

# Alinhamento Macro, Priorização e Valor de Informação

Leia `references/COORDENACAO_SKILLS.md`. Esta skill governa **se/por que/qual frente**; skills de domínio governam como executar.

## Gate epistemológico antes da prioridade

```text
PRIORITY_INPUT_GATE
WHICH_CLAIMS_DRIVE_THE_RANKING?
EPISTEMIC_STATUS?
EVIDENCE?
IF_FALSE_DOES_PRIORITY_CHANGE?
```

Se uma claim material em `UNKNOWN`, `HYPOTHESIS` ou `CONFLICT` altera a ordem das frentes, a prioridade imediata é validar essa claim. Se não for possível, a prioridade deve ser explicitamente `PROVISIONAL`.

Não use plausibilidade, narrativa coerente ou repetição como evidência.

Trabalhe de trás para frente:

```text
OBJETIVO MACRO
<- DECISÃO NECESSÁRIA
<- INFORMAÇÃO NECESSÁRIA
<- PERGUNTA
<- INVESTIGAÇÃO
```

Toda frente relevante deve mostrar:

```text
MACRO_LINK
BLOCKER_OR_QUESTION
EXPECTED_INFORMATION
IF_PASS_WHAT_CHANGES
IF_NOGO_WHAT_CHANGES
DECISION_AFFECTED
COST
```

Se PASS e NOGO levam praticamente ao mesmo estado macro, o valor de informação é baixo.

## Anti-túnel

```text
LOAD_MACRO_STATE
-> IDENTIFY_ACTIVE_FRONTS
-> EXPLAIN_WHY_THIS_FRONT_NOW
-> CHECK_NEW_RESULTS/UNLOCKS
-> CHECK_STOP/REPRIORITIZATION_TRIGGERS
-> CONFIRM_OR_CHANGE_PRIORITY
```

Classifique resultados como MACRO, MESO, LOCAL ou INFRASTRUCTURAL. Não confunda mais produção, cobertura, precisão ou runtime com ganho macro sem cadeia causal.

Leia `references/REFERENCIA_APROFUNDADA.md` para VOI, centralidade, portfólio de investigações, proxy traps e critérios detalhados.

## Fechamento de verificação acessível

Se detectar inconsistência, obsolescência ou incerteza material que possa verificar com os acessos atuais, investigue na tarefa corrente até identificar a fonte/estado corrente e delimitar o impacto material. Não devolva ao usuário uma verificação que o próprio agente pode executar. Siga owner/fonte, referências diretas e dependentes materiais e pare quando o impacto estiver delimitado.

`NO_UNRESOLVED_VERIFICATION_HANDOFF = TRUE`
