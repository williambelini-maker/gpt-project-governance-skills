# Distribuição do GPT Project Toolkit via GitHub

`DOCUMENT_ROLE = PLUGIN_DISTRIBUTION_GUIDE`

## Objetivo

Distribuir as cinco Skills como um único toolkit, sem transformar governança ou qualquer outra Skill em comportamento padrão do agregador.

## Identidade

```text
PLUGIN_NAME = gpt-project-toolkit
DISPLAY_NAME = GPT Project Toolkit
PLUGIN_ROLE = SKILL_AGGREGATOR_ROUTER
DEFAULT_SKILL = NONE
ROUTE_BY_TASK = TRUE
GOVERNANCE_IS_NOT_DEFAULT = TRUE
```

## Arquitetura

```text
skills_instalaveis/pacotes/
        |
        | fonte editável
        v
plugins/gpt-project-toolkit/skills/
        |
        | pacote de distribuição
        v
plugin.json
        |
        +--> plugins/releases/gpt-project-toolkit-<version>.zip
        |
        +--> .agents/plugins/marketplace.json
```

## Formato

- `plugins/gpt-project-toolkit/plugin.json`
- `plugins/gpt-project-toolkit/skills/<skill>/SKILL.md`
- `.agents/plugins/marketplace.json`

O ZIP para `Criar plugin -> Importar` contém somente `plugin.json` e `skills/`.

## Roteamento

O plugin não deve inferir que a tarefa é de governança só porque foi ativado.

```text
USER_TASK
-> CLASSIFY_CAPABILITY
-> SELECT_RELEVANT_SKILL(S)
-> APPLY_SKILL_SCOPE
```

As cinco Skills continuam independentes e coordenáveis.

## Marketplace

Plugin:

`gpt-project-toolkit`

Source:

`./plugins/gpt-project-toolkit`

## GitHub

Repositório:

`https://github.com/williambelini-maker/gpt-project-governance-skills`

O nome técnico do repositório é preservado por continuidade de URLs e histórico; ele não define o nome nem o comportamento do plugin agregador.

## Atualização

```text
CHANGE_CANONICAL_SKILL
-> VALIDATE_SOURCE_PACKAGE
-> SYNC_PLUGIN_COPY
-> VALIDATE_ONE_SKILL_MD_PER_SKILL
-> VALIDATE_REFERENCES
-> VALIDATE_PLUGIN_JSON
-> VALIDATE_MARKETPLACE_JSON
-> BUILD_RELEASE_ZIP
-> VERIFY_RELEASE_ZIP
-> PUBLISH_GITHUB
```

## Validação mínima

- exatamente cinco diretórios de Skill;
- exatamente um `SKILL.md` por Skill;
- referências e assets preservados;
- `plugin.json` JSON válido;
- nome do plugin = `gpt-project-toolkit`;
- versão SemVer;
- `shortDescription` com no máximo 30 caracteres;
- marketplace aponta para `./plugins/gpt-project-toolkit`;
- nenhuma Skill é declarada como default;
- nenhuma descrição do agregador apresenta governança como função principal;
- nenhum MCP/app é declarado sem existir;
- cópias das Skills idênticas às fontes canônicas.

## Instalação no ChatGPT por Importar

Artefato atual:

`plugins/releases/gpt-project-toolkit-0.2.0.zip`

Fluxo:

```text
ChatGPT
-> Criar plugin
-> Importar
-> selecionar gpt-project-toolkit-0.2.0.zip
```

## Migração

`gpt-project-governance-0.1.1.zip` é release histórica e superseded.

Usuários devem substituir a instalação anterior pelo `GPT Project Toolkit` v0.2.0.

## Estado

`PLUGIN_FORMAT = AGENT_PLUGINS_1_0_PORTABLE`

`PLUGIN_VERSION = 0.2.0`

`SKILL_COUNT = 5`

`REMOTE_PUBLICATION = PENDING`


`RELEASE_ZIP = plugins/releases/gpt-project-toolkit-0.2.0.zip`

`RELEASE_ZIP_SHA256 = c0037c3e3bece289fc3c19113ef58e3f837ffa1bfb95c81200e48bfe44104c92`

`RELEASE_ZIP_BYTES = 170028`
