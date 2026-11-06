# <NOME_DO_PROJETO>

## Finalidade
<descrição curta>

## Escopo
`REPOSITORY_SCOPE = <pasta/limites>`

## Owners

```text
MACRO_STATUS_OWNER = MACRO_STATUS.md | STATUS.md#Contexto-macro
STATUS_OWNER = STATUS.md
CANONICAL_AUTHORITY_POINTER = <caminho ou N/A>
BASES_OWNER = BASES_CANONICAS.md | N/A
KNOWLEDGE_MAP_OWNER = MAPA_DE_CONHECIMENTO.md | N/A
REUSABLE_ASSETS_OWNER = ATIVOS_REUTILIZAVEIS.md | N/A
ARCHITECTURE_OWNER = docs/ARCHITECTURE.md | N/A
EPISTEMIC_STATE_OWNER = PREMISSAS_E_EVIDENCIAS.md | STATUS.md#Premissas-e-evidencia | N/A
REPOSITORY_STRUCTURE_OWNER = ESTRUTURA_REPOSITORIO.md | INLINE
USER_ACCESS_ZONE = usuario/ | entregas/ | outro | N/A
```

Projetos com múltiplas frentes, prioridades concorrentes, blockers estratégicos ou objetivo local subordinado a objetivo maior devem usar `MACRO_STATUS.md`. Projetos simples podem manter orientação macro inline no `STATUS.md`, sem criar documento extra.

## Ordem de leitura

1. fundamentos universais da política;
2. este README e owners;
3. owner de estado macro;
4. `STATUS.md` da frente atual;
5. premissas/hipóteses materiais e suas evidências, quando a decisão depender delas;
6. owner de estrutura física, quando necessário para criar/mover artefatos;
7. bases/mapa/contrato apontados pelo estado macro ou local;
8. `ATIVOS_REUTILIZAVEIS.md`, quando a tarefa envolver pesquisa/derivação/execução já trabalhada;
9. catálogo universal de skills;
10. skill(s) acionadas;
11. arquitetura/ADRs/evidências pertinentes.

Antes de executar o `NEXT`, confirmar que a frente ainda é coerente com o estado macro e continua prioritária.

Histórico e outputs não são primeira leitura.

## Execução
`<comando principal>`

## Verificação
`<comando de teste/gate>`

## Mapa documental

- estado macro: `MACRO_STATUS.md` ou seção macro declarada em `STATUS.md`
- estado operacional: `STATUS.md`
- bases: `BASES_CANONICAS.md` ou N/A
- premissas/evidência: `PREMISSAS_E_EVIDENCIAS.md`, STATUS inline ou N/A
- mapa vivo: `MAPA_DE_CONHECIMENTO.md` ou N/A
- ativos reutilizáveis: `ATIVOS_REUTILIZAVEIS.md` ou N/A
- arquitetura: `docs/ARCHITECTURE.md` ou N/A
- decisões: `docs/decisions/` ou N/A
- estrutura física: `ESTRUTURA_REPOSITORIO.md` ou declaração inline
- acesso do usuário: `USER_ACCESS_ZONE`
- histórico: `CHANGELOG.md`/archive

## Regras locais

- <guardrail 1>
- <guardrail 2>
