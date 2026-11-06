# Política universal de documentação de repositórios

Objetivo: permitir continuidade entre chats/agentes **sem consumir a produção com burocracia**.

> Conversa não é fonte de verdade. O repositório deve ser retomável por owners vivos e índices curtos.

## Entrada para novos chats

Use:

`NOVO_CHAT/README.md`

Esse arquivo é o boot operacional. **Não é necessário ler toda esta pasta para começar a trabalhar.**

## Camadas

```text
FUNDAMENTOS/README.md   -> comportamento universal, sempre ativo
NOVO_CHAT/README.md     -> boot mínimo com orientação macro
skills/README.md        -> roteador compacto de capacidades
README do projeto       -> escopo, owners e navegação
MACRO_STATUS/owner      -> estado estratégico e prioridade entre frentes
STATUS                  -> estado operacional da frente e NEXT
POLITICA_ESTRUTURA       -> regras de localização, acesso e ciclo de vida dos artefatos
```

Referência sob demanda:

```text
POLITICA_DOCUMENTAL.md
POLITICA_ESTRUTURA_REPOSITORIO.md
POLITICA_VALIDACAO_PREMISSAS_E_EVIDENCIA.md
MAPA_DOCUMENTAL.md
MATRIZ_FONTE_DA_VERDADE.md
GUIA_NOVO_CHAT.md
PROTOCOLO_ATUALIZACAO_E_HANDOFF.md
skills/references/
templates/
```

Leia referência somente quando houver dúvida de autoridade, propagação, adoção documental, handoff, conflito estrutural ou necessidade técnica específica.

## Arquitetura mínima de um projeto

```text
README.md
STATUS.md
MACRO_STATUS_OWNER = MACRO_STATUS.md | seção macro explícita no STATUS
REPOSITORY_STRUCTURE_OWNER = ESTRUTURA_REPOSITORIO.md | README
```

Projetos com múltiplas frentes, prioridades concorrentes ou objetivo local subordinado a objetivo maior devem preferir:

```text
MACRO_STATUS.md
```

Adicionar quando houver valor real:

```text
CONTRATO_ESPECIFICACOES.md
BASES_CANONICAS.md
MAPA_DE_CONHECIMENTO.md
ATIVOS_REUTILIZAVEIS.md
docs/ARCHITECTURE.md
ESTRUTURA_REPOSITORIO.md
ADRs
```

Não criar documentos só porque existe template.

## Regras de eficiência

- uma verdade viva por assunto;
- estado macro separado de estado operacional quando houver múltiplas frentes;
- ponteiros em vez de duplicação;
- estado vivo curto;
- catálogo de skills conhecido, detalhes sob gatilho;
- hipótese material é investigada antes de virar premissa operacional;
- `NO_UNVERIFIED_PREMISE_PROPAGATION`;
- bases/resultados/ativos antes de nova busca;
- especificações vigentes antes de alteração;
- validação de regressões afetadas antes da entrega;
- atualização somente dos owners afetados;
- histórico separado do boot;
- raiz curada: nenhum artefato novo vai para a raiz por conveniência;
- novos arquivos passam por `FILE_PLACEMENT_GATE`;
- entregáveis humanos recorrentes ficam em zona de acesso explícita;
- corrente, release e histórico não se misturam;
- `NEXT` nunca é autojustificado: revalidar contra o estado macro;
- `READ_UNTIL_GLOBALLY_ORIENTED_AND_LOCALLY_ACTIONABLE`.

## Critério de saúde

Um novo chat sem memória deve descobrir rapidamente:

```text
SCOPE
MACRO_OBJECTIVE
CURRENT_MACRO_STATE
ACTIVE/RELEVANT_FRONTS
CURRENT_PRIORITY_FRONT
WHY_THIS_FRONT_NOW
STOP/REPRIORITIZATION_TRIGGER
CURRENT_OBJECTIVE
ACTIVE_REQUIREMENTS/INVARIANTS
ACTIVE_BASES
LAST_BINDING_RESULT
ACTIVE_BLOCKERS
MATERIAL_PREMISES + EPISTEMIC_STATUS
EVIDENCE_FOR_DECISION_DRIVERS
ACTIVE_SKILLS
USER_ACCESS_ZONE
CANONICAL_ARTIFACT_HOMES
NEXT_EXECUTABLE_ACTION
```

Além de descobrir o `NEXT`, deve conseguir **justificar por que ele continua sendo o melhor próximo passo no contexto macro**.

Também deve conseguir localizar sem busca ampla os arquivos correntes de uso humano e saber onde novas classes de artefato devem ser criadas.

Se isso exigir arqueologia em conversas, ledgers, buscas antigas ou varredura da raiz, a memória operacional/estrutural está degradada.
