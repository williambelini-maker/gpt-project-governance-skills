# GPT Project Toolkit

Toolkit de **5 Skills coordenadas para ChatGPT/agentes** cobrindo continuidade de projetos, priorização, organização de repositórios, modelagem físico-matemática e engenharia de sistemas/simulação.

O toolkit não impõe uma Skill padrão. A tarefa determina qual capacidade deve ser usada.

```text
USER TASK
-> identify relevant capability
-> load only the relevant Skill(s)
-> execute within each Skill's scope
```

## Skills

| Skill | Use quando |
|---|---|
| `governanca-projetos-continuidade` | o trabalho depende do estado de um projeto/repositório existente, owners, contexto, continuidade ou handoff |
| `alinhamento-macro-priorizacao` | é preciso escolher entre frentes, hipóteses, experimentos ou investigações |
| `organizacao-higiene-repositorio` | é preciso decidir onde arquivos e artefatos devem morar, limpar raiz, separar corrente/histórico/releases |
| `modelagem-fisico-matematica` | há formulação, derivação, redução ou validação matemática/física material |
| `engenharia-simulacao-sistemas-automacao` | há arquitetura executável, estados, transições, simulação, automação, agentes ou robustez |

As Skills podem ser combinadas quando cada uma atua no próprio eixo de decisão.

## Instalação no ChatGPT

Para instalar as cinco Skills juntas:

```text
plugins/releases/gpt-project-toolkit-0.2.2.zip
```

No ChatGPT:

```text
Criar plugin
-> Importar
-> selecionar gpt-project-toolkit-0.2.2.zip
```

O pacote contém somente:

```text
plugin.json
skills/
  alinhamento-macro-priorizacao/
  engenharia-simulacao-sistemas-automacao/
  governanca-projetos-continuidade/
  modelagem-fisico-matematica/
  organizacao-higiene-repositorio/
```

Para instalar Skills individualmente, consulte `skills_instalaveis/UPLOADS_CHATGPT/`.

## Como funciona

Você não precisa chamar uma Skill pelo nome. O host pode selecionar a Skill adequada pelo gatilho descrito no `SKILL.md`.

Exemplos:

```text
"continue este projeto"
-> governanca-projetos-continuidade

"qual dessas frentes vale atacar primeiro?"
-> alinhamento-macro-priorizacao

"organize este repositório"
-> organizacao-higiene-repositorio

"derive e valide este modelo"
-> modelagem-fisico-matematica

"projete e simule este sistema"
-> engenharia-simulacao-sistemas-automacao
```

O agregador `GPT Project Toolkit` não transforma governança em comportamento padrão.

## Fonte e distribuição

```text
skills_instalaveis/pacotes/
        |
        | fonte editável das Skills
        v
plugins/gpt-project-toolkit/skills/
        |
        | distribuição conjunta
        v
plugins/releases/gpt-project-toolkit-<version>.zip
```

- fonte editável: `skills_instalaveis/pacotes/`
- plugin: `plugins/gpt-project-toolkit/`
- release atual: `plugins/releases/gpt-project-toolkit-0.2.2.zip`
- marketplace: `.agents/plugins/marketplace.json`
- distribuição individual: `skills_instalaveis/UPLOADS_CHATGPT/`

## Estrutura principal

```text
.
├── plugins/
│   ├── gpt-project-toolkit/
│   └── releases/
├── skills_instalaveis/
│   ├── pacotes/
│   └── UPLOADS_CHATGPT/
├── skills/
├── templates/
├── FUNDAMENTOS/
├── NOVO_CHAT/
├── legal/
├── LICENSE.md
├── CONTRIBUTING.md
└── README.md
```

## Coordenação entre Skills

Cada Skill possui ownership distinto:

```text
governança/continuidade -> contexto, owners, estado e handoff
priorização            -> qual frente e por quê agora
organização            -> onde artefatos moram
modelagem              -> formulação, redução e validação matemática/física
engenharia             -> arquitetura executável, simulação e automação
```

Instrução explícita do usuário, contratos e evidência do projeto prevalecem sobre heurísticas genéricas.

## Princípio epistemológico comum

As cinco Skills compartilham uma regra:

```text
INFERENCE_CAN_CREATE_A_HYPOTHESIS
INFERENCE_CANNOT_PROMOTE_IT_TO_TRUTH
NO_UNVERIFIED_PREMISE_PROPAGATION = TRUE
```

Isso não significa que toda tarefa seja de governança; é apenas uma regra de qualidade comum às Skills quando decisões dependem de claims materiais.

## Licenciamento

Este projeto é **source-available** e usa licenciamento público não comercial com possibilidade de licenciamento comercial separado.

- Skills operacionais e ativos instaláveis: **PolyForm Noncommercial 1.0.0**
- documentação e metodologia: **CC BY-NC-SA 4.0**
- uso comercial: somente conforme licença aplicável ou acordo escrito separado

Entrada legal:

- `LICENSE.md` — mapa de escopo
- `legal/README.md` — índice jurídico completo
- `legal/COMMERCIAL_LICENSING.md` — licenciamento comercial
- `CONTRIBUTING.md` — regras de contribuição

## Repositório

O nome histórico do repositório remoto é `gpt-project-governance-skills`. O produto distribuído atualmente é **GPT Project Toolkit**.

---

# English

**GPT Project Toolkit** is a coordinated set of five installable Skills for project continuity, prioritization, repository organization, physical/mathematical modeling, and engineering/simulation/automation.

There is **no default Skill**. The task determines which capability is loaded.

Current combined ChatGPT package:

```text
plugins/releases/gpt-project-toolkit-0.2.2.zip
```

The editable Skill sources live in `skills_instalaveis/pacotes/`; `plugins/gpt-project-toolkit/` is a generated combined distribution.

Licensing: operational/installable Skill material uses PolyForm Noncommercial 1.0.0; documentation/methodology uses CC BY-NC-SA 4.0. See `LICENSE.md` and `legal/README.md`.
