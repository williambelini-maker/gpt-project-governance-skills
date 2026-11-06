# Skill — Engenharia de Simulação, Sistemas e Automação

`SKILL_ROLE = CORE`

Pergunta central: **como transformar o problema em sistema executável, simulável, verificável e robusto?**

Use quando houver modelagem de estado, simulação, decisão operacional, planejamento, otimização, automação, agentes ou arquitetura material.

## Gate epistemológico antes de modelar

Não fixe estado, causa, requisito técnico, capacidade de runtime ou restrição presumida sem evidência quando isso altera a solução.

```text
CLAIM
-> EPISTEMIC_STATUS
-> SOURCE/OBSERVATION/TEST
-> IF_FALSE_EFFECT
```

Se arquitetura, algoritmo ou prioridade mudaria caso a claim fosse falsa, validar antes de construir sobre ela.

Protótipos exploratórios são permitidos para testar hipótese, mas não transformam a hipótese em requisito verdadeiro por si só.

## Core de modelagem

Antes de escolher tecnologia, formalize apenas o necessário:

```text
ENTITIES
STATE
ACTIONS
EVENTS
TRANSITIONS
RESOURCES
HARD_CONSTRAINTS
OBJECTIVES
UNCERTAINTIES
```

Separe:

```text
DOMAIN_MODEL
STATE_MODEL
EXECUTION_ENGINE
DECISION_POLICY
EXTERNAL_ADAPTERS
OBSERVABILITY
```

Estado e transições importantes devem ser explícitos e auditáveis.

## Escolha do método

Escolha paradigma pela natureza do problema, não pela biblioteca:

```text
discrete-event | continuous | time-step | hybrid | agent-based | stochastic
```

Prefira a solução mais simples que satisfaça o contrato:

```text
EXACT RULE
-> DETERMINISTIC ALGORITHM
-> DP/GRAPH/CONSTRAINT/MATH OPTIMIZATION
-> HEURISTIC/METAHEURISTIC
-> LEARNING only if structure requires it
```

Não usar IA para substituir regra determinística, restrição dura ou validação.

## Verificação essencial

- invariantes do estado;
- hard vs soft constraints;
- baseline simples;
- caso mínimo/oráculo antes de escala;
- verificação da implementação vs validação do modelo;
- sensibilidade e robustez quando material;
- determinismo/replay quando possível.

## Automação e execução

Para efeito externo relevante, considere:

```text
OBSERVE -> PLAN -> VALIDATE -> ACT -> VERIFY -> RECOVER
```

Separar planner/validator/executor quando a consequência justificar.

Modelar quando pertinente:

- idempotência;
- concorrência/ownership;
- timeout/partial/failure;
- retry/rollback/compensação;
- versionamento de estado;
- logs/métricas/tracing.

## Performance

```text
MEASURE -> LOCATE BOTTLENECK -> UNDERSTAND -> OPTIMIZE -> MEASURE AGAIN
```

Reduza antes de escalar. Não adicionar GPU, cache, concorrência, microserviço, agente ou solver sem problema medido que justifique.

## Gate antes de mudança material de solução

```text
PROBLEM/MODEL
STATE + TRANSITIONS
CONSTRAINTS
OBJECTIVE
PROPOSED_METHOD
BASELINE
ACCEPTANCE/VALIDATION
RESOURCE_ENVELOPE
```

Não inventar campos essenciais ausentes. Inspeções e manutenção já autorizadas não precisam desse gate completo.

## Referência sob demanda

Consulte `references/ENGENHARIA_SIMULACAO_SISTEMAS_AUTOMACAO_REFERENCIA.md` quando precisar aprofundar algoritmos em grafos, scheduling, otimização matemática, paradigmas de simulação, sistemas distribuídos, máquinas de estado, multiagentes, recovery, profiling, estruturas de dados, property-based/fuzzing ou arquitetura de integração.

> Modelo antes de código; restrição antes de otimização; baseline antes de sofisticação; validação antes de autonomia.
