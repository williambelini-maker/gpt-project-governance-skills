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
