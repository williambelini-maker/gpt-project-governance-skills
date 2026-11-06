# GPT Project Governance — Plugin Package

Pacote de distribuição das cinco Skills do projeto para ChatGPT/Codex via plugin.

## Estrutura

```text
plugins/gpt-project-governance/
├── plugin.json
├── SOURCE_OF_TRUTH.md
└── skills/
    ├── governanca-projetos-continuidade/
    ├── alinhamento-macro-priorizacao/
    ├── organizacao-higiene-repositorio/
    ├── modelagem-fisico-matematica/
    └── engenharia-simulacao-sistemas-automacao/
```

O formato portátil atual usa `plugin.json` na raiz e descobre Skills automaticamente no diretório `skills/`.

## Fonte

Não editar as cópias deste diretório como fonte primária.

Fonte canônica:

`skills_instalaveis/pacotes/`

Veja `SOURCE_OF_TRUTH.md`.

## Marketplace do repositório

O repositório expõe este plugin por:

`.agents/plugins/marketplace.json`

A entrada aponta para:

`./plugins/gpt-project-governance`

## Apps/MCP

`MCP_BUNDLED = NO`

`CONNECTED_APPS_BUNDLED = NO`

A primeira versão distribui apenas Skills. Integrações como Pasta_Projetos/GitHub permanecem separadas até haver motivo para acoplá-las ao plugin.
