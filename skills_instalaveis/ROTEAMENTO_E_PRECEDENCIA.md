# Roteamento e precedência das skills instaláveis

## Princípio

A plataforma descobre skills principalmente pelo `name` e `description`. Portanto, a coordenação é feita por **gatilhos e ownership de decisão**, não por prioridade numérica de pasta.

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

## Regra de ativação da Governança

A Governança é a camada contextual padrão **quando o trabalho depende materialmente de um projeto/repositório existente**. Isso não significa carregar todas as referências nem bloquear produção.

```text
PROJECT_CONTEXT_MATERIAL?
YES -> GOVERNANCE CONTEXT
NO  -> NORMAL ROUTING
```

Depois de obter orientação suficiente, a execução especializada deve ser delegada à skill competente de Macro, Organização ou domínio.


## Gate epistemológico global

Antes que qualquer skill use uma claim material para decidir:

```text
CLAIM
-> EPISTEMIC_STATUS
-> EVIDENCE
-> SOURCE/TEST
-> IF_FALSE_EFFECT
```

```text
INFERENCE_CAN_CREATE_A_HYPOTHESIS
INFERENCE_CANNOT_PROMOTE_IT_TO_TRUTH
```

Se a decisão muda com uma claim não validada, a investigação da claim precede a execução consequente.

Se a skill detectar obsolescência, conflito ou incerteza material que pode verificar com os acessos disponíveis, deve fechar a investigação na tarefa atual e delimitar o impacto antes de entregar. `NO_UNRESOLVED_VERIFICATION_HANDOFF = TRUE`. A busca segue owner/fonte autoritativa, referências diretas e dependentes materiais; não vira varredura indiscriminada.

## Matriz de roteamento

| Situação | Skill principal | Skills complementares |
|---|---|---|
| qualquer trabalho material que dependa de projeto/repositório existente | Governança e Continuidade | Macro, Organização, domínio conforme necessidade |
| novo chat entrando em projeto existente | Governança e Continuidade | Macro, Organização, domínio conforme necessidade |
| dúvida sobre P0/prioridade/frente/stop | Alinhamento Macro | Governança |
| criar/mover relatório, dados, scripts, outputs | Organização e Higiene | Governança + domínio |
| equações, EDO/EDP, derivação, estabilidade, problema inverso | Modelagem Físico-Matemática | Macro + Engenharia quando houver implementação |
| simulação, arquitetura, automação, agentes, estados/transições | Engenharia de Simulação/Sistemas | Macro + Modelagem quando houver matemática material |
| reorganização de legado | Organização e Higiene | Governança |
| handoff / fonte da verdade / conflito documental | Governança e Continuidade | Macro se prioridade estiver envolvida |

## Colisões esperadas

### Macro + domínio
Macro decide **se e por que** perseguir. Domínio decide **como**.

### Organização + domínio
Organização decide **onde** o artefato mora. Domínio decide **o conteúdo/método**.

### Matemática + Engenharia
Matemática governa formulação/redução/validação matemática. Engenharia governa sistema executável, arquitetura e operação. Contratos e testes reconciliam a fronteira.
