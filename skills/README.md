# Roteador de skills metodológicas

Este arquivo é o **mapa compacto de capacidades**. Conheça o catálogo; abra apenas a skill necessária.

```text
ENTENDER PROBLEMA
-> CONFIRMAR ORIENTAÇÃO MACRO SUFICIENTE
-> MATCH DE SKILL
-> LER CORE DA SKILL
-> CONSULTAR references/ SOMENTE SE NECESSÁRIO
-> PRODUZIR
```

Skills são método, não fonte de verdade nem owner de prioridade.

## Gate antes de ativar profundamente uma skill

Uma skill pode operar sobre o problema local somente depois de haver contexto suficiente para responder:

```text
MACRO_OBJECTIVE
CURRENT_MACRO_STATE
MATERIAL_PREMISES_VALIDATED_OR_EXPLICITLY_UNCERTAIN
CURRENT_FRONT
WHY_THIS_FRONT_NOW
EXPECTED_MACRO_EFFECT
STOP/REPRIORITIZATION_TRIGGER
```

Se isso for materialmente desconhecido, consultar o owner macro antes de aprofundar. A skill não deve inferir prioridade global apenas porque o `STATUS` local contém um `NEXT`.

Antes de usar qualquer claim material como entrada de decisão, aplique `HYPOTHESIS_VALIDATION_GATE`. Skill pode formular hipótese; não pode promovê-la a verdade sem evidência.

Quando uma skill detectar inconsistência, obsolescência ou incerteza material que consegue verificar diretamente, a investigação deve ser fechada na tarefa corrente: localizar fonte autoritativa, comparar estado antigo × atual, rastrear dependentes materiais e delimitar impacto. Não devolver como “próximo trabalho” algo verificável com os acessos disponíveis. `NO_UNRESOLVED_VERIFICATION_HANDOFF = TRUE`.

## Catálogo

| Skill | Pergunta central | Ativar quando | Core |
|---|---|---|---|
| **Alinhamento Macro, Priorização e Valor de Informação** | O que vale perseguir agora? | múltiplas frentes, ganho local vs macro, VOI, bloqueadores, stop/repriorização | `ALINHAMENTO_MACRO_PRIORIZACAO_VALOR_INFORMACAO.md` |
| **Modelagem Físico-Matemática** | Como compreender, reduzir e resolver matematicamente? | equações, dinâmica, estabilidade, EDO/EDP, variacional, assintótica, problemas inversos | `MODELAGEM_FISICO_MATEMATICA_DERIVACAO_REDUCAO_VALIDACAO.md` |
| **Engenharia de Simulação, Sistemas e Automação** | Como transformar o problema em sistema executável e robusto? | estados, eventos, simulação, arquitetura, planejamento, automação, agentes | `ENGENHARIA_SIMULACAO_SISTEMAS_AUTOMACAO.md` |
| **Organização e Higiene de Repositório** | Onde cada artefato deve morar? | criação/migração de arquivos, raiz bagunçada, outputs, releases, zona do usuário, versionamento físico | `ORGANIZACAO_HIGIENE_REPOSITORIO.md` |

## Estado de roteamento

```text
KNOWN_SKILLS = catálogo lido
ACTIVE_SKILLS = <core(s) ou NONE>
SKILL_SELECTION_REASON = <razão>
MACRO_ORIENTATION_STATUS = SUFFICIENT | INSUFFICIENT
```

Reavaliar quando mudar materialmente: classe do problema, objetivo, blocker, fase, frente, prioridade, tipo de decisão ou estrutura física. Não a cada microação.

A skill de organização pode ser ativada sem aprofundamento metodológico quando a tarefa cria/move múltiplos artefatos ou quando a casa canônica não está clara.

## Core vs referência

O arquivo principal da skill deve conter somente:

- gatilhos;
- princípios;
- processo de decisão;
- gates;
- critérios de validação/stop;
- rota para aprofundamento.

Conhecimento enciclopédico fica em `references/` e só é lido quando a técnica concreta exigir.

## Autoridade

Skill não sobrescreve instrução do usuário, contrato vigente, owner macro, owner canônico, evidência, ADR ou blocker ainda aplicável.

## Novas skills

Uma skill nova deve responder claramente:

```text
WHEN_TO_ACTIVATE
CENTRAL_QUESTION
MACRO_CONTEXT_REQUIRED
CORE_PROCESS
GATES
EPISTEMIC_PREMISE_POLICY
WHEN_TO_STOP
WHEN_TO_LOAD_REFERENCE
```

Se o core crescer a ponto de virar manual, extrair detalhes para `references/`.
