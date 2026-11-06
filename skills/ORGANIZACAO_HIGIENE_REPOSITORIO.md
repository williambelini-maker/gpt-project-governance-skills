# Skill — Organização e Higiene de Repositório

`SKILL_ROLE = CORE`

Pergunta central: **onde cada artefato deve morar para que humanos e agentes encontrem, usem e mantenham o projeto sem arqueologia?**

## Quando ativar

Ativar quando houver:

- criação de múltiplos arquivos;
- novos outputs/relatórios/datasets/artefatos;
- raiz congestionada;
- nomes `final/final2/novo/corrigido`;
- versões paralelas sem política;
- mistura entre arquivo humano e arquivo de máquina;
- migração ou reorganização de legado;
- dificuldade de localizar corrente vs histórico;
- criação de diretórios estruturais.

## Contexto necessário

```text
REPOSITORY_SCOPE
EXISTING_TOP_LEVEL_STRUCTURE
USER_ACCESS_PATTERN
TECHNOLOGY_CONSTRAINTS
CURRENT_CANONICAL_PATHS
VERSION_CONTROL_MODEL
```

Não inventar estrutura sem inspecionar a existente.

## Processo central

```text
INVENTORY_SHALLOW
-> CLASSIFY_ARTIFACTS
-> IDENTIFY_HUMAN_ENTRYPOINTS
-> IDENTIFY_MACHINE_AREAS
-> IDENTIFY_CURRENT_VS_HISTORY
-> FIND_CANONICAL_HOMES
-> DETECT_PLACEMENT_DEBT
-> PROPOSE_MINIMAL_STRUCTURE
-> VALIDATE_PATH_DEPENDENCIES
-> MIGRATE_INCREMENTALLY_IF_NEEDED
-> VERIFY_DISCOVERABILITY
```

## Precedência de organização

```text
FUNCTION / ACCESS
-> SUBJECT
-> LIFECYCLE / VERSION
-> EXTENSION when useful
```

Não organizar globalmente por extensão.

## Gates

### FILE_PLACEMENT_GATE

```text
ROLE?
PRIMARY_USER?
SUBJECT?
LIFECYCLE?
VERSIONING?
EXISTING_HOME?
USER_ACCESS_REQUIRED?
ROOT_REQUIRED?
```

### ROOT_HYGIENE_GATE

```text
ROOT_IS_CURATED
ROOT_ONLY_IF_ENTRYPOINT_OR_REQUIRED
```

### USER_ACCESS_GATE

Arquivos recorrentes do usuário devem estar em área humana rasa e previsível.

### VERSIONING_GATE

Código usa VCS por padrão. Releases e entregáveis podem ter versões congeladas explícitas.

### LEGACY_MIGRATION_GATE

Não mover legado sem verificar referências, builds, automações, documentação e consumidores externos.

## Critérios de organização

Preferir:

- uma casa canônica por classe de artefato;
- diretórios de primeiro nível com função inequívoca;
- nomes estáveis;
- corrente separado de histórico;
- dados raw separados de derivados;
- artefatos de máquina separados de entregáveis humanos;
- zona humana facilmente acessível;
- raiz pequena e previsível.

Evitar:

- despejo na raiz;
- `misc/`, `outros/`, `coisas/` como solução permanente;
- `output/` universal sem contrato;
- duplicar arquivo corrente em várias pastas;
- pasta por extensão como arquitetura principal;
- versionar código pelo nome quando Git resolve;
- criar nova pasta sem verificar estrutura existente.

## Saída mínima útil

```text
CURRENT_STRUCTURE
PLACEMENT_PROBLEMS
USER_ACCESS_ZONE
CANONICAL_HOMES
ROOT_POLICY
VERSIONING_MODEL
PROPOSED_MINIMAL_CHANGES
MIGRATION_RISKS
VERIFICATION
```

## Stop

Pare quando:

- novos artefatos têm homes inequívocos;
- zona humana está clara;
- raiz está curada;
- corrente vs histórico está claro;
- migração adicional teria custo maior que benefício.

## Referência

Consulte `../POLITICA_ESTRUTURA_REPOSITORIO.md` quando precisar das regras completas de classificação, versionamento, dados, releases ou migração.

> Estrutura deve reduzir busca e erro; não maximizar número de pastas.
