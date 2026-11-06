# Política resumida de estrutura física

A localização segue:

```text
FUNCTION / ACCESS
-> SUBJECT
-> LIFECYCLE / VERSION
-> EXTENSION when useful
```

## Raiz
`ROOT_IS_CURATED = TRUE`

Raiz contém entrypoints, owners vivos, configuração exigida e diretórios funcionais. Não use a raiz como depósito.

## Zona humana
Projetos com entregáveis recorrentes declaram:
`USER_ACCESS_ZONE = <caminho>`

Arquivos humanos recorrentes não ficam misturados com logs, cache, temporários e intermediários.

## Código
Use VCS por padrão. Evite `v1/v2/final/final2` em nomes de código.

## Dados
Quando aplicável:
```text
data/
├── raw/
├── reference/
├── processed/
└── derived/
```

## Releases
Corrente e histórico são separados. Releases históricos devem ser explícitos, ordenáveis e, quando necessário, imutáveis.

## Legado
Não reorganize em massa sem verificar referências de código, documentação, build, automações e consumidores.
