# Uploads de Skills para o ChatGPT

Esta é a **pasta de referência para uploads** das Skills instaláveis deste repositório.

`UPLOAD_FOLDER = skills_instalaveis/UPLOADS_CHATGPT/`

## Arquivos

- `alinhamento-macro-priorizacao.zip` — 6 arquivos no bundle
- `engenharia-simulacao-sistemas-automacao.zip` — 5 arquivos no bundle
- `governanca-projetos-continuidade.zip` — 20 arquivos no bundle; governança ampla + validação epistemológica
- `modelagem-fisico-matematica.zip` — 5 arquivos no bundle
- `organizacao-higiene-repositorio.zip` — 5 arquivos no bundle

## Como usar

Faça upload de **um ZIP por Skill**. Não envie esta pasta inteira como uma única Skill.

Cada ZIP contém uma única pasta de topo:

```text
<nome-da-skill>/
├── SKILL.md
├── references/   # quando aplicável
└── assets/       # quando aplicável
```

## Fonte de verdade

Estes ZIPs são artefatos de distribuição. Os bundles editáveis continuam em `skills_instalaveis/pacotes/`, e a fonte metodológica canônica continua nas políticas, templates e skills-fonte do repositório.

## Atualização futura

```text
SOURCE CHANGE
-> RECONCILE BUNDLE
-> VALIDATE 1 SKILL.md
-> REGENERATE ZIP
-> REPLACE FILE IN UPLOADS_CHATGPT
```

`GENERATED_AT = 2026-11-08`

`GOVERNANCE_BUNDLE_REVISION = PROJECT_CONTEXT_MATERIAL_V2`


## Revisão epistemológica

`EPISTEMIC_BUNDLE_REVISION = CLOSED_VERIFICATION_AND_BOUNDED_IMPACT_V2`

Os cinco ZIPs desta pasta foram regenerados com esta revisão porque o contrato comum de coordenação mudou. A regra central é: inferência pode criar hipótese, mas hipótese material deve ser validada antes de sustentar prioridade, diagnóstico, arquitetura, implementação ou conclusão.


`EPISTEMIC_ZIPS_REGENERATED = YES`

A revisão V2 acrescenta fechamento obrigatório de verificação acessível: uma Skill que consegue verificar inconsistência/obsolescência deve trazer a evidência, o estado corrente e o impacto delimitado, em vez de devolver a investigação ao usuário.


## Licenciamento dos bundles

Cada ZIP inclui um `LICENSE.md` próprio com o aviso PolyForm Noncommercial 1.0.0 para o material operacional da Skill e preserva a licença aplicável das referências documentais incorporadas.

`BUNDLE_LICENSE_NOTICE = INCLUDED`
