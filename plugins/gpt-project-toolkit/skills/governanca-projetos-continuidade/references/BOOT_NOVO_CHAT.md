# Boot operacional para novos chats

Este é o **entrypoint padrão**. O objetivo é ficar globalmente orientado e localmente apto a produzir com o mínimo de leitura.

## Boot

1. Leia `../FUNDAMENTOS/README.md`.
2. Identifique repositório/escopo e faça inventário raso, incluindo estrutura de primeiro nível.
3. Leia README/entrada do projeto e identifique owners documentais e, se declarado, o owner de estrutura física.
4. Leia obrigatoriamente o owner de estado macro: `MACRO_STATUS.md` ou seção macro declarada no `STATUS.md`.
5. Leia o `STATUS.md` da frente atual.
6. Identifique premissas materiais que sustentam diagnóstico, prioridade e NEXT; execute `HYPOTHESIS_VALIDATION_GATE`.
7. Leia índices curtos de contrato, bases, mapa de conhecimento e ativos apenas quando apontados ou materialmente necessários.
8. Leia `../skills/README.md` como mapa de capacidades.
9. Classifique o desafio e abra somente a(s) skill(s) acionada(s).
10. Execute o `ANTI_TUNNEL_GATE`: reavalie prioridade, blocker, razão da frente e `NEXT_EXECUTABLE_ACTION` contra o estado macro.
11. Antes de criar artefatos, identifique casa canônica e zona de acesso humano; use `FILE_PLACEMENT_GATE`.
12. Se globalmente orientado, epistemicamente validado, localmente acionável e estruturalmente orientado: **produza**.

```text
READ_UNTIL_GLOBALLY_ORIENTED_AND_LOCALLY_ACTIONABLE
```

Não carregar política extensa, ADRs, ledgers, histórico ou referências de skill sem uma aresta concreta exigindo isso.

## Estado mínimo a conhecer

```text
SCOPE
MACRO_OBJECTIVE
CURRENT_MACRO_STATE
ACTIVE_FRONTS relevantes
CURRENT_PRIORITY_FRONT
WHY_THIS_FRONT_NOW
STOP/REPRIORITIZATION_TRIGGER
CURRENT_OBJECTIVE
CANONICAL_AUTHORITY
ACTIVE_REQUIREMENTS/INVARIANTS relevantes
ACTIVE_BASES relevantes
LAST_BINDING_RESULT
ACTIVE_BLOCKERS
MATERIAL_PREMISES + EPISTEMIC_STATUS
EVIDENCE_FOR_DECISION_DRIVERS
ACTIVE_SKILLS
USER_ACCESS_ZONE quando aplicável
CANONICAL_ARTIFACT_HOMES relevantes
NEXT_EXECUTABLE_ACTION
```

Desconhecido vira `UNKNOWN`; não inventar. Se um UNKNOWN impede justificar a prioridade ou o NEXT, carregar o owner correspondente antes de aprofundar.

## Hypothesis validation gate

Antes de assumir causa, estado, restrição ou dado material:

```text
WHAT_CLAIM_IS_DRIVING_THE_DECISION?
STATUS = UNKNOWN | HYPOTHESIS | SUPPORTED | VERIFIED | FALSIFIED | CONFLICT
WHAT_EVIDENCE?
WHAT_SOURCE/TEST?
IF_FALSE_DOES_PRIORITY_OR_NEXT_CHANGE?
```

Se a resposta muda materialmente e a claim não está suficientemente validada:

```text
VALIDATE_FIRST
```

Pesquisa/investigação direcionada passa a ser o próximo trabalho. Não promover plausibilidade a fato por repetição.

## Anti-tunnel gate

Antes de aprofundar materialmente uma frente:

```text
MACRO_OBJECTIVE_KNOWN?
CURRENT_MACRO_STATE_KNOWN?
CURRENT_FRONT_IDENTIFIED?
WHY_THIS_FRONT_NOW_KNOWN?
EXPECTED_MACRO_EFFECT_KNOWN?
STOP_OR_REPRIORITIZATION_TRIGGER_KNOWN?

-> IS_CURRENT_FRONT_STILL_JUSTIFIED?
   YES -> PROCEED
   NO  -> REPRIORITIZE
   UNKNOWN -> LOAD_MACRO_OWNER
```

O `NEXT` herdado é uma proposta operacional vigente somente enquanto sua justificativa macro continuar válida.

## Antes de produzir

```text
NEW_INPUT
-> HYPOTHESIS_VALIDATION_GATE
-> UPDATE_SPEC_CONTRACT
-> CHECK_AFFECTED_REQUIREMENTS
-> DEFINE_ACCEPTANCE
-> IF_FILE_CREATION: FILE_PLACEMENT_GATE
-> PRODUCE
```

Antes de busca/derivação nova, execute reuse gate: bases, resultados, queries/prompts, checks, scripts, datasets e métodos já existentes. Nova busca exige lacuna nova.

## Durante

- hipótese vale como hipótese até evidência suficiente; não construir cadeia de trabalho sobre inferência não validada;
- blocker vale apenas em seu escopo atual;
- desbloqueio propaga antes de continuar como se nada tivesse mudado;
- mudança de classe de problema pode ativar outra skill;
- resultado relevante volta às bases/estado;
- descoberta material não fica apenas na conversa: promova ao owner correto;
- mudança macro deve atualizar/reconciliar prioridade das frentes;
- arquivo novo deve reutilizar casa canônica existente; não despejar na raiz;
- entregável humano recorrente deve permanecer fácil de localizar e separado de artefatos de máquina;
- antes de força bruta, tente redução estrutural e justifique o espaço remanescente;
- não transformar documentação em trabalho principal.

## Antes de entregar

```text
RELOAD_CURRENT_MACRO_STATE
-> RECHECK_MATERIAL_PREMISES
-> RELOAD_CURRENT_CONTRACT
-> VALIDATE_CHANGE
-> VALIDATE_AFFECTED_INVARIANTS
-> CHECK_REGRESSIONS
-> PROPAGATE_MACRO_IMPACT
-> PROMOTE_MATERIAL_DISCOVERIES
-> UPDATE_AFFECTED_OWNERS
-> VERIFY_REPOSITORY_HYGIENE
-> DELIVER
```

## Cold-start continuity test

Outro chat sem memória da conversa anterior deve conseguir, apenas pelo repositório:

1. entender o objetivo macro e o estado macro atual;
2. conhecer as frentes relevantes e a prioridade relativa;
3. explicar por que a frente atual é prioridade;
4. dizer o que a faria perder prioridade ou parar;
5. distinguir fatos verificados, hipóteses, unknowns e conflitos que sustentam a decisão;
6. localizar o estado operacional e a evidência;
7. localizar entregáveis humanos correntes e casas canônicas sem varrer o repositório;
8. justificar e executar o NEXT sem arqueologia em conversas.

Se souber apenas **o que fazer a seguir**, mas não **por que isso é o melhor passo no contexto global**, a retomada está incompleta.
