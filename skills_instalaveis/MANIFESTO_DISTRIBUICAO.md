# Manifesto da distribuição de skills

`DISTRIBUTION_STATUS = READY`

`EPISTEMIC_POLICY = DELIVERY_COMPLETENESS_INTENT_RECONCILIATION_V3`

## Pacotes

| Pacote | Owner de decisão | Gatilho dominante |
|---|---|---|
| `governanca-projetos-continuidade` | verdade, owners, contexto, cold start, handoff, contratos | qualquer trabalho material dependente de projeto/repositório existente |
| `alinhamento-macro-priorizacao` | prioridade, VOI, stop/repriorização | escolher qual frente merece trabalho |
| `organizacao-higiene-repositorio` | localização física e ciclo de vida | criar/mover/organizar artefatos |
| `modelagem-fisico-matematica` | formulação/redução/validação matemática | problema físico-matemático material |
| `engenharia-simulacao-sistemas-automacao` | arquitetura executável/estado/automação | sistema, simulação, automação, agentes |

## Composição

```text
GOVERNANÇA
  define contexto e autoridade

MACRO
  decide se/por que/qual frente

ORGANIZAÇÃO
  decide onde artefatos moram

DOMÍNIO
  decide como resolver
  ├── MODELAGEM FÍSICO-MATEMÁTICA
  └── ENGENHARIA DE SISTEMAS
```

Mais de uma skill pode atuar no mesmo trabalho quando cada uma permanecer no próprio eixo de decisão.


## Canais de distribuição

```text
CANONICAL_EDITABLE_SOURCE = skills_instalaveis/pacotes/
INDIVIDUAL_SKILL_DISTRIBUTION = skills_instalaveis/UPLOADS_CHATGPT/*.zip
COMBINED_PLUGIN_DISTRIBUTION = plugins/gpt-project-toolkit/
GITHUB_MARKETPLACE = .agents/plugins/marketplace.json
```

O plugin conjunto não cria uma nova fonte da verdade. Sua árvore `skills/` deve permanecer idêntica aos pacotes canônicos correspondentes.

Consulte `DISTRIBUICAO_PLUGIN_GITHUB.md`.


## Regra do agregador

```text
PLUGIN_AGGREGATOR_ROLE = ROUTER
DEFAULT_SKILL = NONE
ROUTE_BY_TASK = TRUE
GOVERNANCE_IS_NOT_DEFAULT = TRUE
```

O plugin conjunto não altera a precedência semântica das Skills nem transforma a Skill de governança em ponto de entrada obrigatório.


## Gate universal de entrega

```text
DELIVER_AT_HIGHEST_JUSTIFIED_COMPLETENESS = TRUE
NO_PREMATURE_HANDOFF = TRUE
DO_NOT_REASK_ESTABLISHED_CONTEXT = TRUE
COGNITIVE_COMPLETION_IS_NOT_OPERATIONAL_EXECUTION = TRUE
```

A regra vale em qualquer domínio: reconciliar o pedido, validar incerteza material, concluir o que é resolvível e separar conclusão cognitiva de execução operacional.
