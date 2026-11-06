# Matriz de fonte da verdade

`DOCUMENT_ROLE = REFERENCE`

| Informação | Owner padrão | Regra |
|---|---|---|
| Escopo/navegação | `README.md` | estável; não ledger |
| Estado macro/prioridade entre frentes | `MACRO_STATUS.md` ou seção macro declarada | obrigatório como informação; arquivo dedicado quando complexidade justificar |
| Estado operacional/NEXT da frente | `STATUS.md` | única fonte viva operacional por padrão |
| Razão da prioridade atual | owner macro | não inferir apenas do STATUS local |
| Requisitos/invariantes vigentes | `CONTRATO_ESPECIFICACOES.md` ou owner local | criar só quando necessário; supersessão explícita |
| Autoridade/cânone | lock/ponteiro canônico referenciado pelo estado | separar de frente ativa |
| Bases consolidadas | `BASES_CANONICAS.md` ou owner declarado | pilares reutilizáveis |
| Relações vivas | `MAPA_DE_CONHECIMENTO.md` ou owner declarado | índice, não evidência completa |
| Ativos reutilizáveis | `ATIVOS_REUTILIZAVEIS.md` ou equivalente | queries/derivações/checks/datasets/métodos |
| Arquitetura | `docs/ARCHITECTURE.md` | estrutural |
| Estrutura física/casas canônicas | `ESTRUTURA_REPOSITORIO.md` ou README | define raiz, zonas funcionais e ciclo de vida |
| Entregável humano corrente | `USER_ACCESS_ZONE` declarada | fácil acesso; não misturar com máquina |
| Releases/histórico de entregáveis | `releases/` ou owner local | corrente separado de histórico |
| Decisão durável | ADR | razão + supersessão |
| Implementação | código + testes | observável |
| Evidência | tests/outputs/reports | preservar estatuto real |
| Skills disponíveis | `skills/README.md` | roteador |
| Histórico | ledger/archive/changelog | nunca primeira leitura |
| Handoff | view/procedimento | não novo owner |
| Conversa | nenhum | nunca canônica isoladamente |

## Conflito

```text
CLASSIFY_INFORMATION
-> FIND_OWNER
-> CHECK_SUPERSESSION/AUTHORITY
-> CHECK_EVIDENCE
-> RECONCILE_OWNER + DEPENDENTS
```

Não escolher verdade por nome, `mtime` ou arquivo mais recente.

Quando um owner muda, propagar somente às dependências materialmente afetadas.

`NEXT_EXECUTABLE_ACTION` pertence ao estado operacional; sua **justificativa e prioridade** pertencem ao estado macro.
