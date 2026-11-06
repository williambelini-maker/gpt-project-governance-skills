# Distribuição do plugin via GitHub

`DOCUMENT_ROLE = PLUGIN_DISTRIBUTION_GUIDE`

## Objetivo

Distribuir as cinco Skills como um único plugin sem substituir as fontes canônicas existentes.

## Arquitetura

```text
skills_instalaveis/pacotes/
        |
        | fonte editável
        v
plugins/gpt-project-governance/skills/
        |
        | pacote de distribuição
        v
.agents/plugins/marketplace.json
        |
        | catálogo GitHub
        v
ChatGPT / Work / Codex
```

## Formato adotado

O plugin usa o formato portátil Agent Plugins 1.0:

- `plugins/gpt-project-governance/plugin.json`
- `plugins/gpt-project-governance/skills/<skill>/SKILL.md`

O formato portátil é preferido para novos pacotes. O overlay `.codex-plugin/plugin.json` não é necessário nesta primeira versão.

## Marketplace

Arquivo:

`.agents/plugins/marketplace.json`

Plugin:

`gpt-project-governance`

Source:

`./plugins/gpt-project-governance`

## GitHub

Repositório alvo:

`https://github.com/williambelini-maker/gpt-project-governance-skills`

Para importação de marketplace em workspace, a documentação atual do ChatGPT usa o URL do repositório e procura `.agents/plugins/marketplace.json` na raiz quando o campo Path fica vazio.

A importação de marketplace de workspace exige permissão administrativa no workspace. Para uso local/pessoal no desktop/Codex, o mesmo marketplace pode ser adicionado como fonte de plugin conforme os controles disponíveis na superfície.

## Atualização

```text
CHANGE_CANONICAL_SKILL
-> VALIDATE_SOURCE_PACKAGE
-> SYNC_PLUGIN_COPY
-> VALIDATE_ONE_SKILL_MD_PER_SKILL
-> VALIDATE_REFERENCES
-> VALIDATE_PLUGIN_JSON
-> VALIDATE_MARKETPLACE_JSON
-> COMMIT
-> GITHUB_SYNC/IMPORT
```

## Validação mínima antes de publicar

- existem exatamente cinco diretórios de Skill;
- cada Skill tem exatamente um `SKILL.md`;
- referências e assets continuam relativos ao diretório da própria Skill;
- `plugin.json` é JSON válido;
- `.agents/plugins/marketplace.json` é JSON válido;
- o nome da entrada do marketplace coincide com o nome do plugin;
- o source path aponta para `./plugins/gpt-project-governance`;
- nenhum MCP/app é declarado sem existir;
- licenças e avisos permanecem dentro das Skills;
- a cópia de plugin corresponde à fonte canônica.

## Referências oficiais

- https://developers.openai.com/plugins/build/plugins
- https://learn.chatgpt.com/docs/enterprise/plugin-management
- https://learn.chatgpt.com/docs/build-skills

## Estado

`PLUGIN_FORMAT = AGENT_PLUGINS_1_0_PORTABLE`

`PLUGIN_VERSION = 0.1.0`

`SKILL_COUNT = 5`

`GITHUB_MARKETPLACE_MANIFEST = READY_LOCAL`

`REMOTE_PUBLICATION = NOT_PERFORMED_IN_THIS_STEP`
