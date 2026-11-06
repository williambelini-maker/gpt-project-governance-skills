# Distribuição do GPT Project Toolkit

`DOCUMENT_ROLE = PLUGIN_DISTRIBUTION_GUIDE`

```text
PLUGIN_NAME = gpt-project-toolkit
DISPLAY_NAME = GPT Project Toolkit
PLUGIN_ROLE = SKILL_AGGREGATOR_ROUTER
DEFAULT_SKILL = NONE
ROUTE_BY_TASK = TRUE
GOVERNANCE_IS_NOT_DEFAULT = TRUE
PLUGIN_VERSION = 0.2.1
SKILL_COUNT = 5
REMOTE_PUBLICATION = PUBLISHED
```

## Fonte

```text
skills_instalaveis/pacotes/
-> plugins/gpt-project-toolkit/skills/
-> plugins/releases/gpt-project-toolkit-0.2.1.zip
```

A fonte editável das Skills é `skills_instalaveis/pacotes/`. A árvore do plugin é distribuição derivada.

## Instalação

```text
ChatGPT
-> Criar plugin
-> Importar
-> gpt-project-toolkit-0.2.1.zip
```

## Release atual

- arquivo: `plugins/releases/gpt-project-toolkit-0.2.1.zip`
- tamanho: `169929` bytes
- SHA-256: `2a5032e1c4f879dae18cecef2535c40de705c7f67eaa80117a3045f0fa78d705`

## Validação

Antes de publicar:

- cinco Skills;
- exatamente um `SKILL.md` por Skill;
- cópias do plugin idênticas à fonte;
- referências/assets válidos;
- manifesto válido;
- nenhuma Skill default;
- ZIP contendo somente `plugin.json` + `skills/`;
- licenças e URLs internas coerentes;
- SHA-256 registrado em `plugins/releases/README.md`.

## Histórico

- `0.2.0`: primeira versão com identidade GPT Project Toolkit.
- `0.1.1`: identidade antiga excessivamente orientada à governança; superseded.
