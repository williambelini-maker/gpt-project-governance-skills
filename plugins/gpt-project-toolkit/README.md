# GPT Project Toolkit — Plugin Package

Pacote agregador das cinco Skills do projeto para distribuição conjunta no ChatGPT e em outras superfícies compatíveis.

`PLUGIN_ROLE = SKILL_AGGREGATOR_ROUTER`

`DEFAULT_SKILL = NONE`

`ROUTE_BY_TASK = TRUE`

`GOVERNANCE_IS_NOT_DEFAULT = TRUE`

## Comportamento esperado

A ativação do plugin não significa ativação automática de governança, continuidade ou qualquer outra Skill.

O host deve selecionar a Skill pela natureza da tarefa:

```text
USER_TASK
-> IDENTIFY_RELEVANT_CAPABILITY
-> SELECT_ONLY_RELEVANT_SKILL(S)
-> EXECUTE_WITHIN_EACH_SKILL_SCOPE
```

Mapa de capacidades:

- `governanca-projetos-continuidade` — contexto de projeto, fonte da verdade, owners, continuidade e handoff;
- `alinhamento-macro-priorizacao` — escolha de frente, valor de informação, stop e repriorização;
- `organizacao-higiene-repositorio` — localização física, ciclo de vida e organização de artefatos;
- `modelagem-fisico-matematica` — formulação, derivação, redução e validação físico-matemática;
- `engenharia-simulacao-sistemas-automacao` — arquitetura executável, estados, simulação, automação e robustez.

## Estrutura

```text
plugins/gpt-project-toolkit/
├── plugin.json
├── SOURCE_OF_TRUTH.md
└── skills/
    ├── governanca-projetos-continuidade/
    ├── alinhamento-macro-priorizacao/
    ├── organizacao-higiene-repositorio/
    ├── modelagem-fisico-matematica/
    └── engenharia-simulacao-sistemas-automacao/
```

O formato portátil usa `plugin.json` na raiz e descobre Skills no diretório `skills/`.

## Fonte

A fonte editável das Skills continua sendo:

`skills_instalaveis/pacotes/`

A árvore deste plugin é distribuição derivada. Veja `SOURCE_OF_TRUTH.md`.

## Marketplace

`.agents/plugins/marketplace.json`

aponta para:

`./plugins/gpt-project-toolkit`

## Apps/MCP

`MCP_BUNDLED = NO`

`CONNECTED_APPS_BUNDLED = NO`

Esta versão distribui somente as cinco Skills.
