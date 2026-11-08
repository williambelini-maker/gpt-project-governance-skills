# Contrato de coordenação entre skills

Este arquivo define **ownership de decisão**, não uma ordem de carregamento garantida pela plataforma.

## Precedência

```text
INSTRUÇÃO EXPLÍCITA DO USUÁRIO
> CONTRATO / OWNERS / EVIDÊNCIA DO PROJETO
> GOVERNANÇA E CONTINUIDADE
> ALINHAMENTO MACRO (se/por que/prioridade)
> ORGANIZAÇÃO DE REPOSITÓRIO (onde/ciclo de vida)
> SKILL DE DOMÍNIO (como resolver)
> HEURÍSTICA GENÉRICA
```

## Ownership

- Governança e Continuidade: fonte de verdade, owners, cold start, handoff, propagação e contrato.
- Alinhamento Macro: decide qual frente merece prioridade, stop/repriorização e valor de informação.
- Organização e Higiene: decide onde arquivos/artefatos devem morar e como corrente/histórico se separam.
- Modelagem Físico-Matemática: decide formulação, derivação, redução e validação matemática.
- Engenharia de Simulação/Sistemas/Automação: decide arquitetura executável, estados, transições, simulação, automação e robustez.

## Regra de composição

Skills podem atuar juntas em dimensões diferentes. Nenhuma skill de domínio pode redefinir prioridade macro ou fonte de verdade. A skill de organização não decide conteúdo técnico. A skill macro não escolhe algoritmo detalhado quando uma skill de domínio é competente.

Em conflito real, preserve instrução explícita, contrato, owner canônico e evidência do projeto.


## Gate epistemológico universal

Todas as skills obedecem:

```text
INFERENCE_CAN_CREATE_A_HYPOTHESIS
INFERENCE_CANNOT_PROMOTE_IT_TO_TRUTH
NO_UNVERIFIED_PREMISE_PROPAGATION = TRUE
```

Antes de usar claim material para prioridade, diagnóstico, arquitetura, implementação ou conclusão:

```text
HYPOTHESIS_VALIDATION_GATE
-> EPISTEMIC_STATUS
-> EVIDENCE
-> SOURCE/TEST
-> IF_FALSE_EFFECT
```

Se a decisão muda conforme claim em `UNKNOWN`, `HYPOTHESIS` ou `CONFLICT`, validar primeiro. Trabalho exploratório pode testar a hipótese, mas não promovê-la sem evidência.


## Gate universal de entrega

Todas as Skills obedecem a um gate de qualidade antes da entrega:

```text
DELIVER_AT_HIGHEST_JUSTIFIED_COMPLETENESS = TRUE
NO_PREMATURE_HANDOFF = TRUE
NO_SECOND_PROMPT_FOR_ALREADY_SOLVABLE_REQUIREMENT = TRUE
DO_NOT_REASK_ESTABLISHED_CONTEXT = TRUE
COGNITIVE_COMPLETION_IS_NOT_OPERATIONAL_EXECUTION = TRUE
```

```text
USER_INTENT_RECONCILIATION_GATE
-> EXPLICIT_REQUESTS
-> CONSTRAINTS_AND_REJECTIONS
-> EXPECTED_OUTPUT
-> AVAILABLE_AND_ESTABLISHED_CONTEXT
-> MATERIAL_PARTS_STILL_UNFULFILLED?
```

```text
COMPLETENESS_BEFORE_DELIVERY_GATE
IS_THIS_THE_RESULT
OR_ONLY_A_DESCRIPTION_OF_WORK_STILL_TO_DO?
WHAT_MATERIAL_PART_IS_RESOLVABLE_NOW?
AM_I_LEAVING_"PROBABLY/POSSIBLY/SHOULD_CHECK/NEXT_STEP"
ONLY_BECAUSE_I_STOPPED_EARLY?
AM_I_ASKING_FOR_SOMETHING_ALREADY_ANSWERED?
```

Se uma parte material do pedido é resolvível agora, dentro do escopo e com contexto/ferramentas disponíveis, complete o raciocínio antes da entrega. Não exigir um segundo prompt para perceber requisito já explícito.

```text
UNRESOLVED_BECAUSE_REALITY_IS_UNCERTAIN
!=
UNRESOLVED_BECAUSE_AGENT_STOPPED_EARLY
```

Linguagem probabilística é legítima para incerteza real; não substitui análise ou verificação disponível. Não revalidar por ritual o que já está estabelecido, salvo fato novo, contradição ou ambiguidade material.

Fechar o raciocínio não autoriza automaticamente mudança material:

```text
ACTION_GATE
IS_THE_ACTION_REQUESTED_OR_AUTHORIZED?
IS_THE_MATERIAL_BASIS_SUFFICIENT?
ARE_RELEVANT_CONSEQUENCES_UNDERSTOOD?
```

Sem autorização/justificativa suficiente para agir, entregue a conclusão, proposta ou contexto corrente já estruturado e deixe explícito somente o bloqueio real de execução.
