---
name: engenharia-simulacao-sistemas-automacao
description: Transforme problemas em sistemas executáveis, simuláveis, verificáveis e robustos usando modelagem de estado, eventos, simulação, arquitetura, planejamento, otimização, automação, agentes, observabilidade e recovery. Use em sistemas de software/engenharia onde estados, transições, restrições e efeitos externos precisam ser explícitos.
---

# Engenharia de Simulação, Sistemas e Automação

Leia `references/COORDENACAO_SKILLS.md`. Esta skill governa **como construir o sistema executável**, não prioridade macro, owner documental ou colocação física de arquivos.

## Gate epistemológico

Não fixe causa, requisito técnico, estado, capacidade de runtime ou restrição presumida sem evidência quando isso altera a solução.

```text
CLAIM
-> EPISTEMIC_STATUS
-> SOURCE/OBSERVATION/TEST
-> IF_FALSE_EFFECT
```

Se arquitetura, algoritmo ou prioridade mudaria caso a claim fosse falsa, valide antes de construir sobre ela. Protótipo exploratório pode testar a hipótese, mas não torná-la verdadeira por conveniência.

Antes de tecnologia, formalize o necessário:

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

Separe domínio, estado, engine, política de decisão, adaptadores e observabilidade.

Escolha paradigma pela natureza do problema: discrete-event, continuous, time-step, hybrid, agent-based ou stochastic.

Prefira:

```text
EXACT RULE
-> DETERMINISTIC ALGORITHM
-> DP/GRAPH/CONSTRAINT/MATH OPTIMIZATION
-> HEURISTIC/METAHEURISTIC
-> LEARNING only if structure requires it
```

Para efeitos externos relevantes:

```text
OBSERVE -> PLAN -> VALIDATE -> ACT -> VERIFY -> RECOVER
```

Modele idempotência, concorrência, timeout/partial/failure, retry/rollback/compensação, versionamento de estado e observabilidade quando pertinentes.

Leia `references/REFERENCIA_APROFUNDADA.md` para algoritmos, scheduling, otimização, sistemas distribuídos, multiagentes, recovery, profiling, testes e arquitetura de integração.

## Fechamento de verificação acessível

Se detectar inconsistência, obsolescência ou incerteza material que possa verificar com os acessos atuais, investigue na tarefa corrente até identificar a fonte/estado corrente e delimitar o impacto material. Não devolva ao usuário uma verificação que o próprio agente pode executar. Siga owner/fonte, referências diretas e dependentes materiais e pare quando o impacto estiver delimitado.

`NO_UNRESOLVED_VERIFICATION_HANDOFF = TRUE`
