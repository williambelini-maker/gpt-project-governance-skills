# Mapa documental e grafo de dependências

`DOCUMENT_ROLE = REFERENCE_DOCUMENT_GRAPH`

> Referência sob demanda. Não faz parte do boot normal; consulte para dúvida de owner, dependência ou propagação.

Este documento define como navegar e atualizar documentação sem tratar o repositório como uma pilha de arquivos.

## 1. Cinco vistas diferentes

### Estado macro
Responde: **onde estamos no problema maior, quais frentes existem e por que uma delas é prioritária agora?**

### Grafo documental
Responde: **quem governa qual afirmação?**

### Grafo de conhecimento
Responde: **qual hipótese, base, resultado ou decisão depende de quê?**

### Estado operacional
Responde: **o que está habilitado, bloqueado, pendente ou executável agora dentro da frente atual?**

### Estrutura física
Responde: **onde cada classe de artefato mora, o que pertence à raiz, onde o usuário encontra entregáveis e como corrente/histórico são separados?**

Não misturar os papéis.

## 2. Tipos de documento

Documentos importantes devem ser interpretáveis por papel:

```text
DOCUMENT_ROLE = LIVE_MACRO_STATE | LIVE_STATE | FOUNDATION | AUTHORITY | ARCHITECTURE | REPOSITORY_STRUCTURE_CONTRACT | DECISION | METHOD | EVIDENCE | HISTORY | VIEW
OWNER_OF = <classe de afirmação>
DEPENDS_ON = <owners/nós relevantes>
UPDATES = <dependentes normalmente afetados>
STATUS = ACTIVE | HISTORICAL | SUPERSEDED | LOCKED
```

Nem todo arquivo precisa materializar esse cabeçalho, mas o papel deve ser inequívoco pelo README/matriz.

## 3. Owners padrão

```text
README.md                 -> entrada, escopo, owners e navegação
MACRO_STATUS.md           -> estado estratégico, frentes, prioridade e gatilhos de repriorização
STATUS.md                 -> estado operacional da frente
BASES_CANONICAS.md        -> pilares consolidados reutilizáveis, quando o projeto exigir
MAPA_DE_CONHECIMENTO.md   -> índice operacional das relações vivas, quando o projeto exigir
ATIVOS_REUTILIZAVEIS.md   -> queries, derivações, checks, datasets e métodos reaproveitáveis
ARCHITECTURE.md           -> contratos estruturais atuais
ESTRUTURA_REPOSITORIO.md  -> casas físicas, raiz, zona humana e versionamento
ADRs                      -> decisão durável e racional
skills/README.md          -> roteador de capacidades metodológicas
EVIDENCE/relatórios       -> prova/provenance
CHANGELOG/history         -> histórico
```

Em projeto simples, o papel `LIVE_MACRO_STATE` pode ser uma seção inequívoca no `STATUS.md`.

## 4. Regra de atualização por consequência

Não perguntar primeiro "quais arquivos editar?". Perguntar:

```text
WHAT_CHANGED?
-> WHICH_CLAIMS_CHANGED?
-> WHO_OWNS_THESE_CLAIMS?
-> WHICH_DEPENDENTS_ARE_AFFECTED?
-> MACRO_IMPACT?
-> UPDATE_OWNERS
-> PROPAGATE
-> VERIFY_CONSISTENCY
```

## 5. Eventos de propagação

Eventos típicos:

```text
NEW_RESULT
NEW_DECISION
BLOCKER_ADDED
BLOCKER_REMOVED
HYPOTHESIS_REJECTED
HYPOTHESIS_SUPPORTED
ARCHITECTURE_CHANGED
SCOPE_CHANGED
PRIORITY_CHANGED
METHOD_CHANGED
BASE_UPDATED
FRONT_OPENED
FRONT_CLOSED
```

Exemplo de desbloqueio:

```text
BLOCKER_REMOVED
-> STATUS
-> dependent NOGOs
-> hypotheses
-> derivations/fronts
-> MACRO_STATUS
-> priorities
-> reusable results that gain relevance
-> NEXT_EXECUTABLE_ACTION
```

## 6. Owner da afirmação

Uma afirmação importante deve ter um owner inequívoco. Outros documentos apontam para o owner e registram apenas o efeito necessário à sua própria função.

Evitar copiar a mesma verdade completa para README, MACRO_STATUS, STATUS, handoff, arquitetura e relatório.

## 7. Vistas derivadas

Resumo, handoff, dashboard ou panorama são `VIEW`, não owner. Devem apontar para a fonte viva e não receber overrides independentes.

## 8. Bases e frentes

Uma frente é derivada do tronco do estudo, não substitui o tronco.

```text
MACRO_OBJECTIVE
<- MACRO_STATE
<- CANONICAL_BASES
<- BINDING_RESULTS
<- ACTIVE_FRONTS
```

Nova frente deve registrar quais bases/resultados reutiliza, qual lacuna permanece e por que merece prioridade relativa.

## 9. Ativos reutilizáveis

Busca, prompt, derivação, script, check, dataset ou método útil deve ser promovido de histórico solto para ativo reutilizável quando tiver valor recorrente.

Antes de nova busca/derivação, executar `REUSE_GATE`.

## 10. Dívida de integração e propagação

Use quando aplicável:

```text
INTEGRATION_DEBT = OPEN | NONE
PENDING_PROPAGATIONS = <lista ou NONE>
UNLOCK_PROPAGATION_STATUS = PENDING | COMPLETE | N/A
```

Resultado validado porém ainda não incorporado ao estado macro/operacional ou às dependências não está completamente encerrado.

## 11. Boot documental recomendado

```text
FUNDAMENTOS
-> README do projeto
-> owner de estrutura física quando declarado
-> MACRO_STATUS/owner macro
-> STATUS da frente
-> MAPA/BASES pertinentes
-> skills/README
-> skill(s) acionadas
-> arquitetura/ADRs/evidência somente no escopo necessário
-> ANTI_TUNNEL_GATE
-> NEXT
```

O objetivo é navegação por relação, owner e casa canônica, não varredura massiva.

## 12. Regra de continuidade

```text
NEXT
<- LOCAL_STATUS
<- CURRENT_PRIORITY_FRONT
<- MACRO_STATE
<- BASES + RESULTS + DECISIONS
```

Se um agente consegue encontrar o `NEXT` mas não justificar essa cadeia, o cold start está incompleto.


## 13. Distribuição de Skills

A distribuição não altera ownership metodológico.

```text
skills_instalaveis/pacotes/   -> SOURCE
skills_instalaveis/UPLOADS_CHATGPT/*.zip -> INDIVIDUAL_DISTRIBUTION
plugins/gpt-project-toolkit/ -> COMBINED_PLUGIN_DISTRIBUTION
.agents/plugins/marketplace.json -> PLUGIN_CATALOG
```

Mudanças de conteúdo nas Skills devem nascer na fonte e propagar para ZIPs/plugin; não devem nascer na cópia do plugin.
