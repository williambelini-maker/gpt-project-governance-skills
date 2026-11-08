---
name: organizacao-higiene-repositorio
description: Organize a estrutura física de repositórios, escolha casas canônicas para arquivos, mantenha a raiz curada, separe arquivos do usuário de artefatos de máquina, trate versionamento/releases e migre legado com segurança. Use ao criar ou mover múltiplos arquivos, outputs, relatórios, datasets, releases ou ao corrigir repositório bagunçado.
---

# Organização e Higiene de Repositório

Leia `references/COORDENACAO_SKILLS.md`. Esta skill governa **onde** artefatos moram; não redefine prioridade macro nem conteúdo técnico.

## Precedência física

```text
FUNCTION / ACCESS
-> SUBJECT
-> LIFECYCLE / VERSION
-> EXTENSION when useful
```

Não organizar globalmente por extensão.

## File placement gate

Antes de criar/mover artefato material:

```text
ARTIFACT_ROLE?
PRIMARY_USER?
SUBJECT?
LIFECYCLE?
VERSIONING_MODEL?
EXISTING_CANONICAL_HOME?
USER_ACCESS_REQUIRED?
ROOT_REQUIRED_BY_TECHNOLOGY?
```

Depois:

```text
INSPECT_NEAREST_STRUCTURE
-> FIND_EXISTING_CANONICAL_HOME
-> REUSE_HOME
-> CREATE_DIRECTORY_ONLY_IF_NEEDED
```

## Regras obrigatórias

- raiz é curada;
- não criar na raiz por conveniência;
- arquivos humanos recorrentes ficam em zona rasa e previsível;
- código usa VCS por padrão, não nomes `v2/final/final2`;
- corrente, release e histórico são papéis diferentes;
- raw data é imutável por padrão;
- logs/cache/temp não competem com entregáveis;
- legado é migrado incrementalmente após verificar dependências de caminho.

Leia `references/POLITICA_ESTRUTURA_REPOSITORIO.md` para a política completa e use `assets/ESTRUTURA_REPOSITORIO.md` quando o projeto exigir contrato físico próprio.

## Fechamento de verificação acessível

Se detectar inconsistência, obsolescência ou incerteza material que possa verificar com os acessos atuais, investigue na tarefa corrente até identificar a fonte/estado corrente e delimitar o impacto material. Não devolva ao usuário uma verificação que o próprio agente pode executar. Siga owner/fonte, referências diretas e dependentes materiais e pare quando o impacto estiver delimitado.

`NO_UNRESOLVED_VERIFICATION_HANDOFF = TRUE`
