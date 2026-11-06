# Política universal de estrutura física de repositórios

`DOCUMENT_ROLE = REFERENCE_REPOSITORY_STRUCTURE_POLICY`

Consulte quando houver criação, movimentação, versionamento, organização ou entrega de arquivos. Para criação normal de arquivos, os gates essenciais desta política são herdados pelos `FUNDAMENTOS`.

## Finalidade

Impedir que o repositório vire uma coleção plana de arquivos funcionalmente corretos, porém difíceis de localizar, manter e retomar.

> Arquivo correto no lugar errado ainda é dívida operacional.

## 1. Princípio central

A localização física deve seguir, nesta ordem:

```text
FUNCTION / ACCESS
-> SUBJECT / DOMAIN
-> LIFECYCLE / VERSION
-> FILE TYPE / EXTENSION when useful
```

Não organizar o repositório inteiro primariamente por extensão.

```text
pdf/
csv/
png/
py/
json/
```

é normalmente inferior a:

```text
reports/
data/
src/
artifacts/
usuario/
```

Extensão pode ser útil dentro de uma área funcional quando melhora navegação.

## 2. Raiz é espaço curado

`ROOT_IS_CURATED = TRUE`

A raiz deve conter somente:

- entrypoints humanos;
- owners vivos essenciais;
- arquivos de configuração exigidos pela tecnologia;
- entrypoints técnicos que o ecossistema espera na raiz;
- diretórios funcionais de primeiro nível.

Exemplos aceitáveis:

```text
README.md
MACRO_STATUS.md
STATUS.md
pyproject.toml
package.json
settings.gradle
.gitignore
src/
tests/
docs/
data/
usuario/
```

Evitar na raiz por conveniência:

```text
resultado_final.csv
grafico2.png
saida.json
log.txt
relatorio_v3.docx
teste_novo.py
dados_corrigidos.xlsx
```

## 3. File placement gate

Antes de criar ou mover arquivo material:

```text
FILE_PLACEMENT_GATE

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
-> CLASSIFY_ARTIFACT
-> FIND_EXISTING_CANONICAL_HOME
-> REUSE_HOME
-> CREATE_NEW_DIRECTORY_ONLY_IF_NO_VALID_HOME_EXISTS
```

Nunca criar na raiz apenas porque é o caminho mais curto.

## 4. Classes de artefato

Classifique pelo menos uma classe dominante:

```text
SOURCE
TEST
CONFIGURATION
DOCUMENTATION
RAW_DATA
REFERENCE_DATA
PROCESSED_DATA
DERIVED_DATA
ANALYSIS
EVIDENCE
GENERATED_ARTIFACT
INTERMEDIATE
DELIVERABLE
USER_FACING_CURRENT
RELEASE
LOG
CACHE
TEMPORARY
HISTORICAL
```

A classe determina ciclo de vida e casa física.

## 5. Zona de acesso do usuário

Projetos que produzam arquivos consultados diretamente pelo proprietário devem declarar:

`USER_ACCESS_ZONE = <caminho>`

Default recomendado quando não houver convenção melhor:

```text
usuario/
```

Pode conter, conforme necessidade:

```text
usuario/
├── README.md
├── relatorios/
├── planilhas/
├── mapas/
├── exportacoes/
└── dados_entrega/
```

Regras:

- arquivos recorrentes para uso humano não devem ficar enterrados em logs, caches, outputs técnicos ou diretórios de execução;
- a zona do usuário deve ser rasa e previsível;
- não duplicar manualmente dezenas de arquivos só para facilitar acesso;
- quando houver versão corrente e histórico, a zona humana aponta para a corrente e releases preservam histórico.

## 6. Código-fonte e versionamento

Para código-fonte:

```text
VERSION_CONTROL = GIT_BY_DEFAULT
```

Evitar:

```text
processamento_v1.py
processamento_v2.py
processamento_v3_final.py
```

Preferir:

```text
src/processamento.py
```

com histórico no VCS.

Versões paralelas de código só devem existir quando representarem contratos simultaneamente suportados, migração explícita, baseline congelada ou exigência técnica real.

## 7. Entregáveis e releases

Entregável corrente e histórico não têm o mesmo papel.

Padrão recomendado:

```text
usuario/
└── relatorios/
    └── relatorio_atual.pdf

releases/
├── v001/
├── v002/
└── v003/
```

ou versão por data quando fizer mais sentido:

```text
releases/
├── 2026-10-15/
├── 2026-10-29/
└── 2026-11-06/
```

Evitar nomes sem semântica:

```text
final
final2
novo
corrigido
agora_sim
ultima_versao
```

Se a versão é importante, ela deve ser explícita, ordenável e documentada.

## 8. Dados

Quando aplicável, separar por ciclo de vida:

```text
data/
├── raw/
├── reference/
├── processed/
└── derived/
```

Regras:

- `raw/` deve permanecer imutável por padrão;
- transformação produz novo artefato;
- dado intermediário não deve competir com dado canônico;
- arquivo exportado ao usuário pode ser promovido para a zona humana sem transformar essa cópia em nova fonte canônica.

## 9. Artefatos gerados

Artefatos técnicos gerados devem ter área própria, por exemplo:

```text
artifacts/
├── figures/
├── tables/
├── maps/
├── intermediate/
└── evidence/
```

ou equivalente coerente com o projeto.

`outputs/` genérico é aceitável apenas quando o projeto realmente usa essa pasta como contrato técnico claro. Não usar `outputs/` como depósito universal.

## 10. Logs, cache e temporários

Separar artefatos efêmeros:

```text
logs/
.cache/
tmp/
build/
dist/
```

somente quando apropriados à tecnologia e preferencialmente fora da navegação humana principal.

Arquivos temporários não devem virar evidência, release ou entregável por acidente.

## 11. Organização por assunto

Quando uma área tiver múltiplos assuntos materialmente distintos, dividir semanticamente:

```text
analyses/
├── solo/
├── clima/
└── produtividade/
```

Não criar subpastas por assunto quando houver poucos arquivos e a divisão piorar a navegação.

## 12. Extensão é critério secundário

Agrupar por extensão apenas quando:

- a área funcional já está definida;
- muitos arquivos similares justificam a separação;
- isso melhora acesso humano ou automação.

Exemplo aceitável:

```text
artifacts/
├── figures/
├── tables/
└── maps/
```

Não transformar o repositório em um classificador de MIME types.

## 13. Estrutura mínima recomendada

Não é obrigatório criar todas as pastas.

```text
project/
├── README.md
├── MACRO_STATUS.md
├── STATUS.md
├── usuario/          # quando houver entregáveis humanos recorrentes
├── src/              # quando houver código
├── tests/            # quando houver testes
├── data/             # quando houver dados
├── analyses/         # quando houver análises persistentes
├── reports/          # fontes/produção de relatórios
├── artifacts/        # artefatos técnicos gerados
├── docs/             # arquitetura e decisões
├── releases/         # versões congeladas quando necessário
└── archive/          # histórico não corrente quando necessário
```

Criar somente áreas que tenham função real.

## 14. Gate de higiene da raiz

```text
ROOT_HYGIENE_GATE

MUST_THIS_FILE_BE_IN_ROOT?
IS_IT_AN_ENTRYPOINT?
IS_IT_A_LIVE_OWNER?
IS_ROOT_REQUIRED_BY_TOOLING?
IS_THERE_A_CANONICAL_HOME?

if canonical home exists -> USE IT
if root not required -> DO NOT PLACE IN ROOT
```

## 15. Gate de acesso do usuário

```text
USER_ACCESS_GATE

IS_USER_FACING?
IS_FREQUENTLY_ACCESSED?
IS_IT_CURRENT?
IS_IT_EASY_TO_FIND_FROM_ROOT?
IS_IT_MIXED_WITH_MACHINE_ARTIFACTS?

if user-facing + recurrent -> promote/link via USER_ACCESS_ZONE
```

## 16. Gate de versionamento

```text
VERSIONING_GATE

IS_THIS_SOURCE_CODE?
IS_GIT_SUFFICIENT?
IS_THIS_A_RELEASE?
MUST_MULTIPLE_VERSIONS_COEXIST?
WHAT_IS_CURRENT?
WHAT_IS_HISTORICAL?
```

Não criar versão em nome de arquivo sem necessidade concreta.

## 17. Legado e migração

Não reorganizar repositório inteiro por impulso.

Antes de mover legado:

```text
LEGACY_MIGRATION_GATE

PATH_REFERENCED_BY_CODE?
PATH_REFERENCED_BY_DOCS?
EXTERNAL_CONSUMER?
BUILD/CI DEPENDENCY?
USER_BOOKMARK/WORKFLOW?
SAFE_TO_MOVE?
REDIRECT/UPDATE_REQUIRED?
```

Para arquivos novos, a política é rígida imediatamente.

Para legado, migrar incrementalmente quando houver benefício claro e segurança.

## 18. Critério de saúde física

Um usuário ou agente deve conseguir responder rapidamente:

```text
WHERE_IS_CURRENT_USER_OUTPUT?
WHERE_IS_SOURCE?
WHERE_ARE_TESTS?
WHERE_ARE_RAW/PROCESSED_DATA?
WHERE_ARE REPORTS?
WHERE_ARE GENERATED_ARTIFACTS?
WHERE_ARE RELEASES?
WHERE_IS_HISTORY?
WHAT_BELONGS_IN_ROOT?
```

Se a resposta exige procurar pelo repositório inteiro, a estrutura física está degradada.

> Organização física é parte da interface do projeto.
