# Fonte da verdade do plugin

`DISTRIBUTION_ROLE = GENERATED_PLUGIN_PACKAGE`

`PLUGIN_IDENTITY = gpt-project-toolkit`

`PLUGIN_ROLE = SKILL_AGGREGATOR_ROUTER`

Este diretório distribui as cinco Skills como um único plugin. Ele não é owner metodológico e não cria uma sexta competência.

## Fonte canônica

A fonte editável das Skills permanece em:

`skills_instalaveis/pacotes/`

A árvore:

`plugins/gpt-project-toolkit/skills/`

é uma cópia de distribuição.

## Regra de propagação

```text
EDIT_SKILL
-> skills_instalaveis/pacotes/<skill>/
-> VALIDATE
-> PROPAGATE_TO_PLUGIN
-> VALIDATE_PLUGIN
-> BUILD_RELEASE
-> PUBLISH
```

Não editar uma Skill somente dentro de `plugins/gpt-project-toolkit/skills/`.

## Regra de roteamento

```text
DEFAULT_SKILL = NONE
ROUTE_BY_TASK = TRUE
GOVERNANCE_IS_NOT_DEFAULT = TRUE
```

A presença do plugin não promove `governanca-projetos-continuidade` acima das demais Skills. Cada Skill mantém seu próprio gatilho e ownership.

## Skills incluídas

- governanca-projetos-continuidade
- alinhamento-macro-priorizacao
- organizacao-higiene-repositorio
- modelagem-fisico-matematica
- engenharia-simulacao-sistemas-automacao

## Licenciamento

Cada Skill copiada preserva seus avisos e escopos de licença. O empacotamento conjunto não altera o licenciamento.

Consulte `LICENSE.md` na raiz do repositório.
