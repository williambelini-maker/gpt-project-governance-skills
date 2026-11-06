# Fonte da verdade do plugin

`DISTRIBUTION_ROLE = GENERATED_PLUGIN_PACKAGE`

Este diretório existe para distribuir as Skills como um único plugin.

## Fonte canônica

A fonte editável das Skills permanece em:

`skills_instalaveis/pacotes/`

A árvore:

`plugins/gpt-project-governance/skills/`

é uma cópia de distribuição. Alterações metodológicas devem ser feitas primeiro na fonte canônica e depois propagadas para o plugin.

## Regra

```text
EDIT_SKILL
-> skills_instalaveis/pacotes/<skill>/
-> VALIDATE
-> PROPAGATE_TO_PLUGIN
-> VALIDATE_PLUGIN
-> PUBLISH
```

Não editar uma Skill somente dentro de `plugins/gpt-project-governance/skills/`, pois isso criaria divergência entre a distribuição individual por ZIP e a distribuição por plugin.

## Skills incluídas

- governanca-projetos-continuidade
- alinhamento-macro-priorizacao
- organizacao-higiene-repositorio
- modelagem-fisico-matematica
- engenharia-simulacao-sistemas-automacao

## Licenciamento

Cada Skill copiada preserva seus avisos e escopos de licença. O empacotamento como plugin não altera o licenciamento dos arquivos incorporados.

Consulte `LICENSE.md` na raiz do repositório.
