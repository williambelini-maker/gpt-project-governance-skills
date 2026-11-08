# Status de empacotamento

`STATUS = FULL_BUNDLES_READY`

`EPISTEMIC_REVISION = CLOSED_VERIFICATION_AND_BOUNDED_IMPACT_V2`

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


## Revisão de fechamento de investigação — V2

O contrato comum agora exige:

```text
NO_UNRESOLVED_VERIFICATION_HANDOFF = TRUE
DISCOVERED_STALENESS_IS_AN_INVESTIGATION_TRIGGER = TRUE
MATERIAL_FINDING_REQUIRES_BOUNDED_IMPACT = TRUE
```

Quando houver acesso e ferramentas suficientes, inconsistência/obsolescência material deve ser investigada até identificar a fonte corrente, comparar antigo × atual, rastrear dependentes materiais e delimitar impacto. A busca é causalmente limitada; bloqueio só é devolvido quando realmente impede o fechamento.
