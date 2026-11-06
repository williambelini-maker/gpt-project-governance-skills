# Estrutura física do repositório

`DOCUMENT_ROLE = REPOSITORY_STRUCTURE_CONTRACT`

Use somente quando a estrutura física for complexa o suficiente para justificar owner próprio. Projetos simples podem declarar esses ponteiros no README.

## Política da raiz

`ROOT_POLICY = CURATED`

`USER_ACCESS_ZONE = <usuario/ | entregas/ | outro | N/A>`

`SOURCE_ROOT = <src/ | app/ | outro | N/A>`

`TEST_ROOT = <tests/ | outro | N/A>`

`DATA_ROOT = <data/ | outro | N/A>`

`REPORT_ROOT = <reports/ | outro | N/A>`

`ARTIFACT_ROOT = <artifacts/ | outro | N/A>`

`RELEASE_ROOT = <releases/ | outro | N/A>`

`HISTORY_ROOT = <archive/ | outro | N/A>`

## Casas canônicas

| Classe | Casa canônica | Corrente/histórico | Observação |
|---|---|---|---|
| código-fonte | <path> | current + Git history | |
| testes | <path> | current | |
| raw data | <path> | immutable | |
| processed data | <path> | current/derived | |
| relatórios fonte | <path> | current + Git | |
| entregáveis humanos | <path> | current | |
| releases | <path> | immutable | |
| evidência | <path> | append/frozen conforme contrato | |
| artefatos intermediários | <path> | disposable | |
| logs/cache/temp | <path> | disposable | |

## Estrutura de referência

Criar somente diretórios usados pelo projeto.

```text
project/
├── README.md
├── MACRO_STATUS.md
├── STATUS.md
├── usuario/
│   ├── README.md
│   ├── relatorios/
│   ├── planilhas/
│   ├── mapas/
│   └── exportacoes/
├── src/
├── tests/
├── data/
│   ├── raw/
│   ├── reference/
│   ├── processed/
│   └── derived/
├── analyses/
├── reports/
│   ├── sources/
│   └── generated/
├── artifacts/
│   ├── figures/
│   ├── tables/
│   ├── maps/
│   ├── evidence/
│   └── intermediate/
├── docs/
│   ├── ARCHITECTURE.md
│   └── decisions/
├── releases/
└── archive/
```

## Versionamento

`SOURCE_VERSIONING = GIT | OTHER`

`DELIVERABLE_VERSIONING = RELEASE_DIRS | DATED_RELEASES | NONE`

`CURRENT_DELIVERABLE_POINTER = <path ou N/A>`

## Exceções de raiz

Liste apenas exigências reais:

- <arquivo> — <por que precisa ficar na raiz>

## Migração de legado

`MIGRATION_STATUS = NONE | PLANNED | IN_PROGRESS | COMPLETE`

`PATH_DEPENDENCIES_CHECKED = YES | NO | N/A`

- <origem> -> <destino> — <risco/razão>

## Verificação

```text
ROOT_HYGIENE = PASS?
USER_ACCESS = PASS?
CURRENT_VS_HISTORY = CLEAR?
CANONICAL_HOMES = CLEAR?
PATH_DEPENDENCIES = SAFE?
```
