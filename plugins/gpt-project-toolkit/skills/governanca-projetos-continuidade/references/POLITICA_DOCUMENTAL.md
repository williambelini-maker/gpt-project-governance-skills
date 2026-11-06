# Política documental universal

`DOCUMENT_ROLE = REFERENCE`

Consulte quando houver dúvida de governança, owner, propagação ou adoção. **Não faz parte do boot normal.**

## Finalidade

Preservar continuidade suficiente para produzir sem depender da conversa e sem transformar documentação em fim próprio.

## Regras

### Um assunto vivo, um owner

Mirrors/resumos apontam; não competem.

### Estado macro e estado operacional têm papéis distintos

Todo projeto deve expor orientação macro suficiente para justificar a frente atual. Em projeto simples, isso pode estar inline no `STATUS.md`. Em projeto com múltiplas frentes, prioridades concorrentes, blockers estratégicos ou objetivo local subordinado a objetivo maior, usar `MACRO_STATUS.md` ou owner equivalente.

```text
MACRO_STATE
-> CURRENT_PRIORITY_FRONT
-> WHY_THIS_FRONT_NOW
-> LOCAL_STATUS
-> NEXT
```

`STATUS.md` não deve, sozinho, transformar uma prioridade momentânea em verdade estratégica.

### Estado vivo é curto

`MACRO_STATUS.md` guarda somente estado estratégico corrente, prioridade entre frentes e gatilhos de mudança.

`STATUS.md` guarda somente estado operacional corrente da frente, seus ponteiros e `NEXT`.

Histórico fica fora do boot.

### Contrato vigente preserva intenção

Quando houver complexidade suficiente, `CONTRATO_ESPECIFICACOES.md` governa requisitos, invariantes, restrições e aceitação vigentes.

Nova instrução altera/supersede o contrato; não apaga silenciosamente obrigações ainda ativas.

### Premissa material não vira verdade por inferência

Claims materiais devem preservar estado epistemológico:

```text
UNKNOWN | HYPOTHESIS | SUPPORTED | VERIFIED | FALSIFIED | CONFLICT
```

Antes de prioridade, decisão ou implementação consequente, aplique `HYPOTHESIS_VALIDATION_GATE`.

Se a decisão muda conforme uma hipótese não validada, a investigação dessa hipótese precede a decisão. Consulte `POLITICA_VALIDACAO_PREMISSAS_E_EVIDENCIA.md`.

### Mudança material propaga

```text
CHANGE
-> AFFECTED_CLAIMS
-> OWNERS
-> DEPENDENTS
-> MACRO_IMPACT
-> UPDATE
-> VERIFY
```

Desbloqueio material exige reavaliar blockers/NOGOs/hipóteses/resultados, prioridades, estado macro e `NEXT`.

### Bases permanecem centrais

Projetos com conhecimento acumulado podem usar `BASES_CANONICAS.md`, `MAPA_DE_CONHECIMENTO.md` e `ATIVOS_REUTILIZAVEIS.md`. Criar somente quando reduzirem redescoberta.

Antes de novo trabalho significativo:

```text
EXISTING_BASE?
EXISTING_RESULT?
EXISTING_ASSET?
NEW_GAP?
```

### Skills são sob demanda

`skills/README.md` é roteador. Abrir core pertinente; detalhes técnicos ficam em `skills/references/` e são consultados somente por necessidade concreta.

### Estrutura física é contrato separado

Owner documental responde **quem governa a afirmação**. Estrutura física responde **onde o artefato deve morar**.

A criação/movimentação de arquivos segue `POLITICA_ESTRUTURA_REPOSITORIO.md`. Não usar a ausência de regra documental como licença para despejar artefatos na raiz.

### Produção governa o orçamento documental

```text
READ_UNTIL_GLOBALLY_ORIENTED_AND_LOCALLY_ACTIONABLE
```

Quando estado macro, autoridade, estado local, contrato e método necessários já forem suficientes, parar de ler e produzir.

Atualizar somente owners afetados. Não preencher templates ou relatórios por hábito.

## Owners padrão

```text
README                    -> entrada/navegação/ponteiros de owners
MACRO_STATUS              -> estado estratégico, portfólio de frentes e razão da prioridade
STATUS                    -> estado operacional da frente/NEXT
CONTRATO_ESPECIFICACOES   -> requisitos/invariantes vigentes, quando necessário
PREMISSAS_E_EVIDENCIAS     -> claims materiais abertas + estado epistemológico, quando necessário
BASES_CANONICAS           -> pilares reutilizáveis, quando necessário
MAPA_DE_CONHECIMENTO      -> relações vivas, quando necessário
ATIVOS_REUTILIZAVEIS      -> queries/derivações/checks/datasets/métodos reutilizáveis
ARCHITECTURE              -> estrutura vigente
ADR                       -> decisão durável e razão
código + testes           -> implementação observável
evidência/ledgers         -> prova/provenance, não onboarding
ESTRUTURA_REPOSITORIO      -> casas canônicas, zona humana, raiz e versionamento físico
```

## Precedência

```text
INSTRUÇÃO EXPLÍCITA DO USUÁRIO/OPERADOR
> GOVERNANÇA E CONTRATO DO PROJETO
> OWNERS/ADRs/EVIDÊNCIA LOCAL
> FUNDAMENTOS UNIVERSAIS
> SKILL ATIVA
> HEURÍSTICA GENÉRICA
```

## Anti-tunnel gate

Antes de aprofundar materialmente uma frente, verificar:

```text
MACRO_OBJECTIVE_KNOWN?
CURRENT_MACRO_STATE_KNOWN?
CURRENT_FRONT_IDENTIFIED?
WHY_THIS_FRONT_NOW_KNOWN?
EXPECTED_MACRO_EFFECT_KNOWN?
STOP_OR_REPRIORITIZATION_TRIGGER_KNOWN?
CURRENT_FRONT_STILL_JUSTIFIED?
```

Se a resposta material for desconhecida, carregar o owner macro. Se a justificativa caiu, repriorizar antes de continuar.

## Anti-padrões

- múltiplos STATUS/handoffs concorrentes;
- estado macro implícito enterrado em histórico;
- tratar `NEXT` como ordem autojustificada;
- aprofundar frente sem saber por que ela é prioridade;
- transformar inferência plausível em fato sem validação;
- priorizar com base em claim material UNKNOWN/HYPOTHESIS sem investigar;
- copiar hipótese para STATUS/MACRO_STATUS e tratá-la como verdade por repetição;
- histórico no boot;
- escolher verdade por nome ou `mtime`;
- NOGO local aplicado globalmente;
- cautela mantida após a causa cair;
- desbloqueio sem propagação;
- nova busca sem reuse gate;
- nova alteração sem considerar contrato vigente;
- correção que introduz regressão em requisito ativo;
- carregar todas as skills/referências;
- documentação atualizada sem claim material alterada;
- arquivo novo jogado na raiz por conveniência;
- misturar entregável humano com logs/cache/intermediários;
- versionar código por nomes `v2/final/final2` quando VCS já resolve;
- criar pasta nova sem verificar casa funcional existente;
- continuar lendo quando já existe orientação global e próxima ação segura.

## Adoção em legado

Não renomeie tudo. Primeiro identifique README, owner macro, STATUS, owners reais e dependências de caminho; depois introduza apenas os índices e migrações que resolvem um problema observável de continuidade.

Para legado, estrutura física é migrada incrementalmente. Para arquivos novos, `FILE_PLACEMENT_GATE` vale imediatamente.

> Documentação é infraestrutura de produção. Se não melhora decisão, execução, validação ou retomada, deve ser condensada ou virar referência.
