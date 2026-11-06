# Publicação no GitHub

`TARGET_REPOSITORY_NAME = gpt-project-governance-skills`

`TARGET_VISIBILITY = PUBLIC`

`PUBLICATION_STATUS = READY_FOR_REMOTE_CREATION`

## Conteúdo a publicar

Publicar a raiz deste repositório preservando:

- políticas universais;
- `FUNDAMENTOS/`;
- `NOVO_CHAT/`;
- `skills/` como fonte metodológica;
- `templates/`;
- `skills_instalaveis/pacotes/` como bundles editáveis;
- `skills_instalaveis/UPLOADS_CHATGPT/` como artefatos de distribuição.

## Verificação de exposição

Em 2026-11-06 foi executada busca por padrões comuns de:

- private keys;
- API keys/secrets/passwords/tokens em atribuições;
- tokens GitHub;
- chaves OpenAI no formato `sk-...`.

Resultado nos arquivos texto examinados: **nenhum padrão encontrado**.

Os ZIPs de `UPLOADS_CHATGPT/` são derivados dos bundles Markdown deste próprio repositório.

Esta verificação reduz risco de exposição acidental, mas não substitui secret scanning do próprio GitHub após a publicação.

## Licença

`LICENSE_STATUS = UNDECIDED`

O repositório pode ser público sem arquivo LICENSE, mas isso **não concede automaticamente uma licença de reutilização**. Não foi escolhida licença em nome do proprietário.

## Limitação operacional atual

O conector GitHub disponível nesta conversa permite operar em repositórios existentes (arquivos, branches, commits e PRs), mas não expõe ação para **criar um novo repositório remoto**.

Após o repositório vazio `gpt-project-governance-skills` existir no GitHub, o conteúdo poderá ser enviado pelo conector.
