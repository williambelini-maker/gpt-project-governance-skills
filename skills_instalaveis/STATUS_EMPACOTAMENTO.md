# Status de empacotamento

`STATUS = FULL_BUNDLES_READY`

`EPISTEMIC_REVISION = DELIVERY_COMPLETENESS_INTENT_RECONCILIATION_V3`

`LAST_RECONCILED_AT = 2026-11-08`

`GOVERNANCE_TRIGGER = PROJECT_CONTEXT_MATERIAL_V2`

## Bundles instaláveis

- `governanca-projetos-continuidade` — core + fundamentos + política documental + mapa/matriz + boot/handoff + templates essenciais.
- `organizacao-higiene-repositorio` — core + política de estrutura física + template de estrutura.
- `alinhamento-macro-priorizacao` — core + referência aprofundada integral + template macro.
- `modelagem-fisico-matematica` — core + referência aprofundada integral.
- `engenharia-simulacao-sistemas-automacao` — core + referência aprofundada integral.

## Fonte canônica

Os bundles são distribuições derivadas.

```text
SOURCE_OF_TRUTH
= arquivos de política / skills / templates fora de skills_instalaveis/

DISTRIBUTION
= skills_instalaveis/pacotes/
```

Mudança na fonte exige reconciliação do bundle correspondente antes de nova publicação.

## Coordenação

A precedência entre skills não depende do nome da pasta. O contrato de coordenação está em:

`skills_instalaveis/ROTEAMENTO_E_PRECEDENCIA.md`

e também em:

`references/COORDENACAO_SKILLS.md`

dentro de cada bundle.

## Estado

Os cinco pacotes estão preparados como diretórios de skill individuais, cada um com um único `SKILL.md` e recursos locais.


## Revisão de ativação da Governança

A descrição de `governanca-projetos-continuidade` foi ampliada para ser considerada sempre que o trabalho depender materialmente do estado de um projeto/repositório existente — incluindo implementação, análise, documentação, organização e entrega — sem forçar ativação em tarefas isoladas fora de contexto de projeto.

O ZIP de upload correspondente foi regenerado após essa revisão.


## Revisão epistemológica

Todos os bundles compartilham agora o contrato:

```text
INFERENCE_CAN_CREATE_A_HYPOTHESIS
INFERENCE_CANNOT_PROMOTE_IT_TO_TRUTH
NO_UNVERIFIED_PREMISE_PROPAGATION = TRUE
```

Governança, Macro, Modelagem e Engenharia possuem gates explícitos antes de usar claims materiais. Organização herda o gate pelo contrato comum de coordenação.


`EPISTEMIC_ZIPS_REGENERATED = YES`


## Licenciamento de distribuição

`BUNDLE_LICENSE_NOTICE = INCLUDED`

Todos os bundles instaláveis carregam `LICENSE.md` interno. O material operacional da Skill é PolyForm Noncommercial 1.0.0; documentação/referências incorporadas preservam a licença documental aplicável definida no mapa de licenciamento do repositório.


## Revisão universal de entrega — V3

O contrato comum foi generalizado. A versão anterior estava excessivamente centrada em obsolescência/verificação. Agora o comportamento universal separa:

```text
USER_INTENT_RECONCILIATION
EPISTEMIC_VALIDATION_WHEN_MATERIAL
COMPLETENESS_BEFORE_DELIVERY
ACTION_AUTHORIZATION
```

```text
DELIVER_AT_HIGHEST_JUSTIFIED_COMPLETENESS = TRUE
NO_PREMATURE_HANDOFF = TRUE
NO_SECOND_PROMPT_FOR_ALREADY_SOLVABLE_REQUIREMENT = TRUE
DO_NOT_REASK_ESTABLISHED_CONTEXT = TRUE
COGNITIVE_COMPLETION_IS_NOT_OPERATIONAL_EXECUTION = TRUE
```

A Skill conclui o que é resolvível, preserva incerteza genuína, evita revalidação ritual e não transforma fechamento analítico em autorização automática para agir.
