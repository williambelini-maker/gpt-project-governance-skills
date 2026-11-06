# Protocolo de atualização, propagação e handoff

`DOCUMENT_ROLE = REFERENCE`

> Consulte quando houver fechamento complexo, propagação pendente ou handoff ambíguo. Não carregar por padrão.

## 1. Conceito

Handoff é uma transação documental: atualizar owners, propagar consequências e deixar o repositório retomável **em contexto macro e local**.

## 2. Eventos que exigem atualização

- implementação material;
- teste/gate decisório;
- resultado científico;
- blocker adicionado/removido;
- NOGO/hipótese alterado;
- mudança de prioridade;
- mudança de arquitetura/contrato;
- decisão durável;
- alteração de cânone;
- abertura/fechamento de frente;
- atualização de base canônica;
- criação de ativo reutilizável relevante;
- mudança de estado macro;
- mudança de razão da prioridade;
- mudança de NEXT;
- criação de nova classe de artefato;
- alteração material da estrutura física;
- mudança de zona de acesso do usuário ou modelo de versionamento.

## 3. Roteamento por consequência

```text
WHAT_CHANGED
-> CLAIMS_CHANGED
-> OWNERS
-> DEPENDENTS
-> MACRO_IMPACT
-> PROPAGATE
-> VERIFY
```

Não atualizar documentos por hábito; atualizar porque uma claim de seu domínio mudou.

## 4. Desbloqueio

Todo desbloqueio material deve executar:

```text
UNLOCK_EVENT
-> affected assumptions
-> affected blockers/NOGOs
-> affected hypotheses/results/fronts
-> newly enabled actions
-> priority recomputation
-> MACRO_STATUS
-> local STATUS
-> NEXT
```

Registrar `UNLOCK_PROPAGATION_STATUS = PENDING` enquanto houver consequência material não incorporada.

## 5. Reconciliation gate antes de nova ramificação

Depois de mudança central, antes de abrir/aprofundar nova frente, verificar:

```text
MACRO_STATUS_UPDATED?
CURRENT_FRONT_STILL_PRIORITY?
BASES_UPDATED?
MAP_UPDATED?
RESULTS_RECLASSIFIED?
PENDING_PROPAGATIONS?
REUSABLE_ASSET_TO_REGISTER?
REPOSITORY_STRUCTURE_STILL_COHERENT?
USER_OUTPUT_STILL_DISCOVERABLE?
```

## 6. Owners

Atualize `MACRO_STATUS` quando mudar objetivo macro, tese, prioridade entre frentes, blocker estratégico, resultado macro vinculante, capacidade habilitada ou gatilho de repriorização.

Atualize `STATUS` quando mudar estado operacional da frente ou NEXT.

Atualize arquitetura quando mudar contrato estrutural; ADR quando houver decisão durável; README quando mudar navegação/owner/escopo; bases quando um pilar consolidado mudar; mapa vivo quando dependências/centralidade mudarem; ativos quando surgir recurso reutilizável.

Atualize `ESTRUTURA_REPOSITORIO`/README quando mudar casa canônica, zona humana, política da raiz, versionamento físico ou ciclo de vida de artefatos.

## 7. Próxima ação

`NEXT_EXECUTABLE_ACTION` deve ser concreta e recalculada depois de desbloqueios ou mudanças de prioridade relevantes.

Antes de herdá-la para outro chat:

```text
NEXT_JUSTIFIED_BY_MACRO_STATE = YES?
```

## 8. Prevenção de drift

Procurar afirmações concorrentes de MACRO_OBJECTIVE/CURRENT_FRONT/WHY_NOW/CURRENT/STATUS/NEXT/P0/BLOCKER/CANONICAL/HANDOFF e referências a blockers já resolvidos ou bases superseded ainda tratadas como ativas.

Detectar especialmente:

- `STATUS` local apontando NEXT cuja razão macro desapareceu;
- frente ainda marcada P0 após resultado que habilitou alternativa melhor;
- `WHY_THIS_FRONT_NOW` divergente entre macro e local;
- resultado local material não propagado ao estado macro;
- raiz acumulando outputs, logs, versões ou entregáveis sem função de entrypoint;
- entregável humano corrente enterrado em diretório técnico;
- `final/final2/novo/corrigido` usado como versionamento;
- mesma classe de artefato espalhada em casas concorrentes.

## 9. Ledgers grandes

Ledgers preservam provenance; índices curtos preservam orientação. Não fazer o próximo chat percorrer histórico para reencontrar query, derivação, resultado, prioridade ou NEXT.

## 10. Handoff completo

Outro chat sem memória deve conseguir:

1. encontrar README, owner macro e STATUS;
2. identificar objetivo e estado macro;
3. conhecer frentes relevantes e prioridade relativa;
4. explicar por que a frente atual está em prioridade;
5. saber quais eventos a fariam parar/repriorizar;
6. identificar bases centrais;
7. entender resultado vinculante e evidência;
8. saber blocker e escopo real de NOGOs;
9. saber se há propagação pendente;
10. descobrir ativos reutilizáveis relevantes;
11. conhecer catálogo de skills e skill ativa;
12. localizar rapidamente arquivos de uso humano e casas canônicas;
13. justificar e executar NEXT sem arqueologia.

## 11. Cold-start continuity test

```text
NEW_AGENT
NO_CHAT_MEMORY
+ REPOSITORY
-> CAN_EXPLAIN_MACRO_STATE?
-> CAN_EXPLAIN_WHY_THIS_FRONT?
-> CAN_EXPLAIN_STOP/REPRIORITIZE?
-> CAN_JUSTIFY_NEXT?
```

Se encontra uma ação mas não consegue justificá-la no contexto global, o handoff está incompleto.

## 12. Anti-resumo concorrente

Resumo executivo é view derivada. Se começar a receber overrides próprios, virou segundo status e deve ser corrigido.
