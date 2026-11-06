# Manifesto da distribuição de skills

`DISTRIBUTION_STATUS = READY`

`EPISTEMIC_POLICY = NO_UNVERIFIED_PREMISE_PROPAGATION_V1`

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
