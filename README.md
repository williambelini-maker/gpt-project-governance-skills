# GPT Project Governance Skills

Sistema aberto de **governança operacional, continuidade, validação de evidências, organização de repositórios e skills reutilizáveis para trabalho com GPTs/agentes**.

Este repositório nasceu de um problema prático: em projetos longos, um agente pode perder contexto entre chats, confundir documentação histórica com estado atual, aprofundar uma frente sem verificar se ela ainda é prioridade ou transformar uma hipótese plausível em premissa sem validar os dados.

O objetivo deste projeto é tornar esse tipo de trabalho **retomável, auditável e epistemicamente disciplinado**, sem transformar documentação em burocracia.

> **Princípio central:** inferência pode gerar uma hipótese; não pode promovê-la silenciosamente a verdade.

~~~text
INFERENCE_CAN_CREATE_A_HYPOTHESIS
INFERENCE_CANNOT_PROMOTE_IT_TO_TRUTH
NO_UNVERIFIED_PREMISE_PROPAGATION = TRUE
~~~

## O que este projeto resolve

O sistema foi desenhado para reduzir falhas recorrentes em trabalho assistido por agentes, como:

- continuar um projeto sem reconstruir o estado global;
- tratar o NEXT herdado como ordem autojustificada;
- otimizar uma frente local que já perdeu valor macro;
- escolher uma “fonte da verdade” apenas pelo nome ou data do arquivo;
- repetir hipóteses até que pareçam fatos;
- priorizar ou implementar com base em premissas não verificadas;
- misturar artefatos humanos, outputs, logs, dados e versões no mesmo lugar;
- perder decisões, blockers, evidências e critérios de parada entre chats;
- recriar buscas, derivações ou ativos que já existiam.

A proposta não é obrigar todos os projetos a usar a mesma árvore documental. A proposta é fornecer **princípios, gates, owners, templates e skills composáveis** que podem ser adotados de forma proporcional à complexidade real do projeto.

## Princípios fundamentais

### 1. Evidência antes de premissa

Claims materiais usam estados epistemológicos explícitos:

~~~text
UNKNOWN
HYPOTHESIS
SUPPORTED
VERIFIED
FALSIFIED
CONFLICT
~~~

Se uma decisão mudaria caso uma hipótese estivesse errada, a hipótese deve ser investigada antes de sustentar a decisão.

~~~text
HYPOTHESIS
-> VALIDATION PLAN
-> INVESTIGATION
-> EVIDENCE
-> STATUS UPDATE
-> DECISION
~~~

### 2. Estado macro antes de aprofundamento local

Uma próxima ação só é válida enquanto sua justificativa continua válida.

~~~text
MACRO OBJECTIVE
-> CURRENT MACRO STATE
-> RELEVANT FRONTS
-> WHY THIS FRONT NOW
-> EXPECTED MACRO EFFECT
-> STOP / REPRIORITIZATION TRIGGER
-> LOCAL STATUS
-> NEXT
~~~

### 3. Uma verdade viva por assunto

Conversa, histórico e arquivos duplicados não devem competir como owners do estado atual.

O projeto separa estado estratégico, estado operacional, contratos vigentes, evidência, histórico, arquitetura, estrutura física e conhecimento reutilizável.

### 4. Continuidade sem depender da memória do chat

Um novo agente deve conseguir reconstruir pelo repositório:

- objetivo macro;
- estado atual;
- frente prioritária;
- por que ela é prioritária;
- premissas materiais e evidências;
- blockers;
- critérios de parada/repriorização;
- próxima ação;
- localização dos owners e artefatos relevantes.

### 5. Organização física é parte da governança

A raiz do repositório é tratada como espaço curado.

~~~text
FUNCTION / ACCESS
-> SUBJECT / DOMAIN
-> LIFECYCLE / VERSION
-> FILE TYPE when useful
~~~

Arquivos são organizados primeiro por função, acesso e ciclo de vida — não simplesmente por extensão.

### 6. Redução antes de força bruta

Quando o problema permite estrutura analítica, matemática ou algorítmica, ela deve ser explorada antes de sweeps, buscas extensas ou computação pesada.

## Skills incluídas

O repositório contém atualmente cinco bundles instaláveis e coordenados:

| Skill | Responsabilidade principal |
|---|---|
| governanca-projetos-continuidade | contexto do projeto, owners, fonte da verdade, cold start, propagação e handoff |
| alinhamento-macro-priorizacao | escolha de frente, valor de informação, blockers, stop e repriorização |
| organizacao-higiene-repositorio | localização física, ciclo de vida, raiz, releases e organização de artefatos |
| modelagem-fisico-matematica | formulação, redução, derivação e validação matemática/física |
| engenharia-simulacao-sistemas-automacao | arquitetura executável, estados, transições, simulação, automação e robustez |

As skills podem atuar juntas. Elas não dependem de uma prioridade numérica artificial; cada uma possui **ownership de decisão** em um eixo diferente.

A precedência conceitual usada pelo sistema é:

~~~text
EXPLICIT USER INSTRUCTION
> PROJECT CONTRACT / OWNERS / EVIDENCE
> GOVERNANCE AND CONTINUITY
> MACRO ALIGNMENT
> REPOSITORY ORGANIZATION
> DOMAIN SKILL
> GENERIC HEURISTIC
~~~

## Estrutura do repositório

~~~text
.
├── FUNDAMENTOS/
│   └── README.md
├── NOVO_CHAT/
│   └── README.md
├── skills/
│   ├── README.md
│   └── references/
├── templates/
├── skills_instalaveis/
│   ├── pacotes/
│   ├── UPLOADS_CHATGPT/
│   ├── ROTEAMENTO_E_PRECEDENCIA.md
│   └── MANIFESTO_DISTRIBUICAO.md
├── POLITICA_DOCUMENTAL.md
├── POLITICA_ESTRUTURA_REPOSITORIO.md
├── POLITICA_VALIDACAO_PREMISSAS_E_EVIDENCIA.md
├── MAPA_DOCUMENTAL.md
├── MATRIZ_FONTE_DA_VERDADE.md
└── PROTOCOLO_ATUALIZACAO_E_HANDOFF.md
~~~

## Como usar

Para compreender a metodologia, comece por:

1. FUNDAMENTOS/README.md
2. POLITICA_VALIDACAO_PREMISSAS_E_EVIDENCIA.md
3. NOVO_CHAT/README.md
4. skills/README.md

Para instalar as Skills já empacotadas, use os ZIPs de:

~~~text
skills_instalaveis/UPLOADS_CHATGPT/
~~~

Cada ZIP corresponde a uma Skill individual. Os diretórios editáveis que originam esses artefatos ficam em:

~~~text
skills_instalaveis/pacotes/
~~~

Os ZIPs são distribuição; as fontes do repositório continuam sendo a referência para evolução e manutenção.

## Validação epistemológica

Uma das regras mais importantes deste projeto é impedir a propagação de premissas não verificadas.

Antes de uma claim material sustentar prioridade, diagnóstico, arquitetura, implementação ou conclusão:

~~~text
HYPOTHESIS_VALIDATION_GATE

WHAT_CLAIM_IS_BEING_USED?
WHAT_IS_ITS_EPISTEMIC_STATUS?
WHAT_EVIDENCE_SUPPORTS_IT?
WHAT_SOURCE_OR_TEST_PROVES_IT?
WHAT_DECISION_DEPENDS_ON_IT?
WOULD_THE_DECISION_CHANGE_IF_FALSE?
~~~

Se a resposta depende materialmente de algo ainda classificado como UNKNOWN, HYPOTHESIS ou CONFLICT, a investigação deve preceder a decisão.

## Estado do projeto

Os bundles instaláveis estão preparados em skills_instalaveis/.

A revisão epistemológica atual é:

~~~text
NO_UNVERIFIED_PREMISE_PROPAGATION_V1
~~~

O projeto continua evoluindo a partir de uso real em repositórios e fluxos de trabalho longos.

## Licenciamento

Este repositório usa **licenciamento não comercial com licenciamento comercial separado**.

- **Skills operacionais e ativos executáveis/instaláveis**: PolyForm Noncommercial License 1.0.0.
- **Documentação, metodologia e materiais textuais**: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0).
- **Uso comercial não é concedido pelas licenças públicas**. Venda, integração comercial, redistribuição paga, oferta como serviço monetizado ou outro uso comercial exige autorização escrita separada do titular.

Consulte:
- `LICENSE.md` — mapa de escopo e precedência;
- `LICENSE-SOFTWARE.md` — aplicação da PolyForm Noncommercial;
- `LICENSE-DOCUMENTATION.md` — aplicação da CC BY-NC-SA 4.0;
- `COMMERCIAL_LICENSING.md` — como solicitar direitos comerciais.

Uma licença comercial separada pode envolver royalties, participação, contribuição ao projeto, parceria, pagamento fixo ou outra contrapartida negociada. Nenhuma dessas condições é automática: dependem de acordo escrito específico.

### Contribuições e direitos comerciais futuros

Contribuições externas só devem ser incorporadas após aceite explícito do `CONTRIBUTOR_LICENSE_AGREEMENT.md`. Esse acordo preserva a autoria do contribuidor, mas concede ao mantenedor direitos suficientes para continuar distribuindo o projeto sob as licenças públicas e também negociar licenças comerciais separadas sobre a contribuição incorporada.

Consulte também:
- `CONTRIBUTING.md`;
- `CONTRIBUTOR_LICENSE_AGREEMENT.md`;
- `COMMERCIAL_LICENSE_TEMPLATE.md`;
- `LEGAL_READINESS.md`;
- `THIRD_PARTY_NOTICES.md`.

---

# English

An open system for **operational governance, continuity, evidence validation, repository organization, and reusable skills for GPT/agent-assisted work**.

This repository grew out of a practical problem: in long-running projects, an agent may lose context between chats, confuse historical documentation with current state, deepen a workstream without checking whether it is still the right priority, or turn a plausible hypothesis into an operational premise without validating the data.

The goal of this project is to make that work **resumable, auditable, and epistemically disciplined** without turning documentation into bureaucracy.

> **Core principle:** inference may create a hypothesis; it may not silently promote it to truth.

~~~text
INFERENCE_CAN_CREATE_A_HYPOTHESIS
INFERENCE_CANNOT_PROMOTE_IT_TO_TRUTH
NO_UNVERIFIED_PREMISE_PROPAGATION = TRUE
~~~

## What this project addresses

The system is designed to reduce recurring failures in agent-assisted work, such as:

- continuing a project without reconstructing the global state;
- treating an inherited NEXT as self-justifying;
- optimizing a local workstream that no longer has macro value;
- selecting a “source of truth” only because of a filename or modification date;
- repeating hypotheses until they begin to look like facts;
- prioritizing or implementing based on unverified premises;
- mixing human-facing deliverables, outputs, logs, data, and versions in the same place;
- losing decisions, blockers, evidence, and stop criteria between chats;
- recreating searches, derivations, or reusable assets that already exist.

The proposal is not to force every project into the same documentation tree. It is to provide **principles, gates, owners, templates, and composable skills** that can be adopted in proportion to the real complexity of a project.

## Fundamental principles

### 1. Evidence before premise

Material claims use explicit epistemic states:

~~~text
UNKNOWN
HYPOTHESIS
SUPPORTED
VERIFIED
FALSIFIED
CONFLICT
~~~

If a decision would change when a hypothesis is false, that hypothesis must be investigated before it is allowed to support the decision.

~~~text
HYPOTHESIS
-> VALIDATION PLAN
-> INVESTIGATION
-> EVIDENCE
-> STATUS UPDATE
-> DECISION
~~~

### 2. Macro state before local depth

A next action remains valid only while its justification remains valid.

~~~text
MACRO OBJECTIVE
-> CURRENT MACRO STATE
-> RELEVANT FRONTS
-> WHY THIS FRONT NOW
-> EXPECTED MACRO EFFECT
-> STOP / REPRIORITIZATION TRIGGER
-> LOCAL STATUS
-> NEXT
~~~

### 3. One live truth owner per subject

Conversation history, historical records, and duplicated files should not compete as owners of current state.

The project distinguishes strategic state, operational state, active contracts, evidence, history, architecture, physical repository structure, and reusable knowledge.

### 4. Continuity without relying on chat memory

A new agent should be able to reconstruct from the repository:

- the macro objective;
- current state;
- the priority workstream;
- why it is the priority;
- material premises and supporting evidence;
- blockers;
- stop/reprioritization criteria;
- the next action;
- the location of relevant owners and artifacts.

### 5. Physical organization is part of governance

The repository root is treated as a curated space.

~~~text
FUNCTION / ACCESS
-> SUBJECT / DOMAIN
-> LIFECYCLE / VERSION
-> FILE TYPE when useful
~~~

Files are organized first by function, access, and lifecycle — not simply by extension.

### 6. Reduction before brute force

When a problem has exploitable analytical, mathematical, or algorithmic structure, that structure should be used before large sweeps, broad searches, or expensive computation.

## Included skills

The repository currently contains five coordinated, installable bundles:

| Skill | Primary responsibility |
|---|---|
| governanca-projetos-continuidade | project context, owners, source of truth, cold start, propagation, and handoff |
| alinhamento-macro-priorizacao | workstream selection, value of information, blockers, stop, and reprioritization |
| organizacao-higiene-repositorio | physical placement, lifecycle, repository root, releases, and artifact organization |
| modelagem-fisico-matematica | mathematical/physical formulation, reduction, derivation, and validation |
| engenharia-simulacao-sistemas-automacao | executable architecture, states, transitions, simulation, automation, and robustness |

Skills may operate together. They do not rely on an artificial numeric priority; each one owns a different decision axis.

The conceptual precedence used by the system is:

~~~text
EXPLICIT USER INSTRUCTION
> PROJECT CONTRACT / OWNERS / EVIDENCE
> GOVERNANCE AND CONTINUITY
> MACRO ALIGNMENT
> REPOSITORY ORGANIZATION
> DOMAIN SKILL
> GENERIC HEURISTIC
~~~

## Repository structure

~~~text
.
├── FUNDAMENTOS/
│   └── README.md
├── NOVO_CHAT/
│   └── README.md
├── skills/
│   ├── README.md
│   └── references/
├── templates/
├── skills_instalaveis/
│   ├── pacotes/
│   ├── UPLOADS_CHATGPT/
│   ├── ROTEAMENTO_E_PRECEDENCIA.md
│   └── MANIFESTO_DISTRIBUICAO.md
├── POLITICA_DOCUMENTAL.md
├── POLITICA_ESTRUTURA_REPOSITORIO.md
├── POLITICA_VALIDACAO_PREMISSAS_E_EVIDENCIA.md
├── MAPA_DOCUMENTAL.md
├── MATRIZ_FONTE_DA_VERDADE.md
└── PROTOCOLO_ATUALIZACAO_E_HANDOFF.md
~~~

## How to use it

To understand the methodology, start with:

1. FUNDAMENTOS/README.md
2. POLITICA_VALIDACAO_PREMISSAS_E_EVIDENCIA.md
3. NOVO_CHAT/README.md
4. skills/README.md

To install the already packaged Skills, use the ZIP files in:

~~~text
skills_instalaveis/UPLOADS_CHATGPT/
~~~

Each ZIP corresponds to one individual Skill. The editable bundle directories that generate those artifacts are in:

~~~text
skills_instalaveis/pacotes/
~~~

ZIP files are distribution artifacts; the repository sources remain the reference for maintenance and evolution.

## Epistemic validation

One of the most important rules in this project is preventing the propagation of unverified premises.

Before a material claim is allowed to support prioritization, diagnosis, architecture, implementation, or a conclusion:

~~~text
HYPOTHESIS_VALIDATION_GATE

WHAT_CLAIM_IS_BEING_USED?
WHAT_IS_ITS_EPISTEMIC_STATUS?
WHAT_EVIDENCE_SUPPORTS_IT?
WHAT_SOURCE_OR_TEST_PROVES_IT?
WHAT_DECISION_DEPENDS_ON_IT?
WOULD_THE_DECISION_CHANGE_IF_FALSE?
~~~

If the answer materially depends on something still classified as UNKNOWN, HYPOTHESIS, or CONFLICT, investigation must precede the decision.

## Project status

The installable bundles are prepared under skills_instalaveis/.

The current epistemic revision is:

~~~text
NO_UNVERIFIED_PREMISE_PROPAGATION_V1
~~~

The project continues to evolve from real use in repositories and long-running workflows.

## Licensing

This repository uses **noncommercial public licensing with separate commercial licensing**.

- **Operational Skills and executable/installable assets**: PolyForm Noncommercial License 1.0.0.
- **Documentation, methodology, and textual materials**: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0).
- **Commercial use is not granted by the public licenses**. Sale, commercial integration, paid redistribution, monetized service offerings, or other commercial use requires separate written authorization from the rights holder.

See:
- `LICENSE.md` — scope and precedence map;
- `LICENSE-SOFTWARE.md` — PolyForm Noncommercial application;
- `LICENSE-DOCUMENTATION.md` — CC BY-NC-SA 4.0 application;
- `COMMERCIAL_LICENSING.md` — how to request commercial rights.

A separate commercial license may involve royalties, participation, project contribution, partnership, a fixed fee, or other negotiated consideration. None of these terms are automatic; they require a specific written agreement.

### Contributions and future commercial rights

External contributions should only be incorporated after explicit acceptance of `CONTRIBUTOR_LICENSE_AGREEMENT.md`. Contributors retain authorship/ownership of their contributions, while granting the maintainer sufficient rights to continue public distribution and to negotiate separate commercial licenses covering incorporated contributions.

See also:
- `CONTRIBUTING.md`;
- `CONTRIBUTOR_LICENSE_AGREEMENT.md`;
- `COMMERCIAL_LICENSE_TEMPLATE.md`;
- `LEGAL_READINESS.md`;
- `THIRD_PARTY_NOTICES.md`.
