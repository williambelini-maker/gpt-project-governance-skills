# Auditoria documental dos projetos — 2026-08-24

Escopo: continuidade documental, autoridade, retomada por novos chats e risco de perda/reversão de ganhos. Não é auditoria completa de mérito científico/código/dados.

Projetos auditados:

- `Projeto Primos`
- `Projeto XY`
- `Projeto Formalismo Matematico Fronteira`
- `Projeto Simulador Operacoes`
- `Projeto Imagem Satelite CB4A`

## 1. Projeto Primos

### Situação documental

Possui documentação rica, guardrails fortes, estado, próxima frente, formalismo, mecânicas, no-gos e grande coleção de artefatos reproduzíveis.

### Inconsistências confirmadas

1. `00_COMECE_AQUI.md` manda ler primeiro `10_RESUMO_EXECUTIVO_P0_ATUAL.md`, mas o próprio `10_RESUMO_EXECUTIVO_P0_ATUAL.md` declara `ROLE = ... / READ_AFTER_00_COMECE_AQUI`. Há ciclo de onboarding.
2. `00_PROTOCOLO_TRABALHO.md` define outra ordem: `README.md` primeiro e `02_ESTADO_ATUAL.md` como fonte principal do estado; `README.md`, por sua vez, manda começar por `00_COMECE_AQUI.md`; `00_COMECE_AQUI.md` promove o resumo 10 como camada curta canônica. Há múltiplas declarações de entrada/autoridade.
3. `02_ESTADO_ATUAL.md` ainda abre com override de `03:10` e `CURRENT_SHARP_P0` baseado na trace relative-unitary; `04_PROXIMA_FRENTE.md` e `10_RESUMO_EXECUTIVO_P0_ATUAL.md` possuem override posterior de `03:43` com backend `det2`/fixed-resolvent e o resumo foi sincronizado às `04:03`. O arquivo chamado “estado atual” ficou atrasado em relação à própria frente viva.
4. A camada de artefatos possui centenas de documentos. Buscar “mais recente” por mtime é útil como auditoria, mas perigoso como mecanismo principal de retomada.

### Risco

**ALTO para onboarding**, apesar da qualidade técnica da documentação. O maior risco é um chat novo escolher uma das várias camadas vivas e trabalhar num P0 supersedido na mesma madrugada.

### Ganho arquitetural a preservar

- separação entre formalismo, mecânicas validadas, no-gos, próxima frente e artefatos;
- estatutos epistemológicos explícitos;
- checks com distinção entre sucesso e falha;
- política de atualizar documentação na mesma rodada.

### Correção recomendada

Escolher uma fonte viva única curta. `00_COMECE_AQUI` e resumo executivo devem virar views/ponteiros, não owners concorrentes. `02_ESTADO_ATUAL` pode permanecer dossiê técnico, mas seu topo deve apontar inequivocamente para o owner corrente e não declarar um P0 independente se não for reconciliado atomicamente.

## 2. Projeto XY

### Situação documental

É o sistema de governança mais explícito entre os projetos: possui revisão locked, protocolo de supersessão, separação entre cânone, trabalho, ontologia e frentes fenomenológicas, além de política de documentação na mesma rodada.

### Problemas confirmados pelo próprio repositório

A auditoria `02_ESTADO/AUDITORIA_DOCUMENTACAO_OPERACIONAL_20260824.md` registra:

1. `00_ESTADO_ATUAL.md`, `01_PROXIMA_FRENTE.md` e `04_REGISTRO_RODADAS.md` cresceram para centenas de kB; um `NEXT` antigo pode parecer corrente;
2. prioridade científica conceitual e prioridade executável estavam sendo confundidas como “P0”;
3. `04_TRABALHO/POST_DYN10_OBSERVAVEL` ficou plano, com mais de mil filhos imediatos;
4. ponteiros U1 ficaram obsoletos depois de o gate de anchors fechar;
5. panorama diário recebe addenda posteriores ao timestamp-base, tornando a recência ambígua.

O README exige uma sequência longa de leitura para retomada, incluindo governança, ontologia, panorama, estado, próxima frente, mapa, ponteiro canônico, status/roadmap locked e frente ativa. A autoridade é segura, mas o custo cognitivo de onboarding é alto.

### Estado de autoridade observado

- revisão canônica: `r1.138`;
- release: `DYN-10 STRUCTURAL`;
- autoridade canônica não mudou;
- prioridade científica conceitual registrada pela auditoria: `T3_PHYSICAL_GRAM_TYPING_OPEN`;
- prioridade executável: `U1_PRODUCT_STIEFEL_CONTINUOUS_TAU_BINDING`.

### Risco

**MÉDIO-ALTO para retomada operacional; BAIXO-MÉDIO para corrupção do cânone**, porque locks/supersessão são fortes.

### Ganho arquitetural a preservar

- `NO_FIRST_SEARCH_RESULT_AUTHORITY`;
- locks e supersessão explícitos;
- distinção cânone × trabalho ativo;
- FAILs vinculantes preservados;
- gates pré-registrados e reprodução.

### Correção recomendada

Adotar um `CURRENT` curto por frente ativa e um estado global curto. Ledgers permanecem provenance. Separar sempre `CANONICAL_AUTHORITY`, `PRIORIDADE_CIENTIFICA_CONCEITUAL`, `PRIORIDADE_EXECUTAVEL` e `NEXT_EXECUTABLE_ACTION`.

## 3. Projeto Formalismo Matematico Fronteira

### Situação documental

Possui contrato muito claro: `01_ESTADO/00_STATUS.json` é declarado fonte operacional de verdade; Markdown deve espelhá-lo. Há protocolo de atualização viva e um único P0 ativo.

Na auditoria, JSON, README, `00_COMECE_AQUI.md`, `01_ESTADO/01_ESTADO_ATUAL.md` e `07_HANDOFF/00_ROTEIRO_NOVO_CHAT.md` estavam coerentes quanto a `241` claims, `5` NOGOs, revisão `STATE-2026-08-24-CRITERIO-DERIVATIVO-104` e próxima execução `VARQ_Q1_Q2_Q4_FAR_NEGATIVE_ARC_CLASSIFICATION`.

### Riscos

1. O mesmo estado humano é repetido em README, Comece Aqui, Estado Atual e Handoff. Hoje está sincronizado; no futuro pode divergir.
2. `00_STATUS.json` já é grande porque incorpora o registro de claims. Como machine-readable isso é administrável, mas mistura ponteiro operacional curto com registry histórico/canônico volumoso.
3. Um novo chat precisa respeitar o contrato local de escopo antes de acessar pastas irmãs. Esta é uma boa regra e deve ser universalizada.

### Risco

**MÉDIO**, atualmente bem controlado.

### Ganho arquitetural a preservar

- source-of-truth explicitamente declarada;
- estados tipados (`FIXED_REPRODUCED`, `NOGO_LOCKED`, etc.);
- atualização conjunta de status, estado humano, changelog e artefato;
- contrato de escopo local;
- checagem de contrato do repositório.

### Correção recomendada

Separar o pequeno `CURRENT_STATE` do registry completo de claims e transformar README/Comece Aqui/Handoff em views derivadas ou ponteiros, não cópias manuais do estado.

## 4. Projeto Simulador Operacoes

### Situação documental

README define com clareza que v0.6 foi encerrada arquiteturalmente e v0.7 é a frente ativa. `ARQUITETURA_VIVA.md` está explicitamente marcada como legado da v0.6, enquanto `ARQUITETURA_V07.md` governa o novo solver.

### Inconsistência confirmada

`docs/V07_PRIMEIRA_FRENTE.md` ainda descreve o primeiro marco como construir um `CoverageFabric`. Entretanto `docs/V07_STATUS.md` e `docs/CHANGELOG.md` registram que o pipeline `coverage_fabric` multichart já foi implementado, integrado a poses e passou cenários/gates iniciais.

Assim, um documento que permanece na ordem oficial de leitura descreve como futuro um marco já realizado.

Além disso, `V07_STATUS.md` lista implementado/não implementado, mas não possui `LAST_RECONCILED_AT` nem uma única `NEXT_EXECUTABLE_ACTION`; após o fechamento do primeiro marco, o próximo passo precisa ser inferido da lista.

### Risco

**MÉDIO**. A separação v0.6/v0.7 é boa, mas o próximo chat pode repetir a primeira frente ou escolher arbitrariamente um item “ainda não implementado”.

### Ganho arquitetural a preservar

- fronteira explícita entre geração congelada e arquitetura nova;
- requisitos físicos separados de arquitetura;
- testes metamórficos e anti-regra-local;
- changelog objetivo;
- arquitetura antiga claramente marcada como legado.

### Correção recomendada

Atualizar/encerrar `V07_PRIMEIRA_FRENTE.md` como concluída/superseded e deixar o próximo gate exclusivamente em `V07_STATUS.md` (ou novo `STATUS.md` curto). Adicionar reconciliação temporal e evidência.

## 5. Projeto Imagem Satelite CB4A

### Situação documental

A documentação é mínima: README descreve função, coleção/bandas, interface, estrutura de saída e execução. A raiz contém também script principal, GeoPackages/QGIS, diretórios de saída e logs.

### Lacunas

Não há, na camada documental identificada:

- fonte explícita de estado atual;
- `LAST_RECONCILED_AT`;
- próxima ação;
- lista de limitações/bugs conhecidos;
- arquitetura/decisões principais;
- changelog ou decisão de versão;
- comandos/gates de verificação;
- explicação documental para diretórios `v/` e `v0/` e sua autoridade.

Logs de execução existem, mas log não substitui estado do projeto.

### Risco

**ALTO para continuidade entre chats**, mesmo sendo um repositório menor. O próximo chat consegue executar o programa, mas não consegue saber com segurança o que está consolidado, o que está pendente e quais escolhas não devem ser revertidas.

### Ganho arquitetural a preservar

- README curto;
- contrato claro de saída;
- aplicação simples e entrypoint evidente.

### Correção recomendada

Adicionar `STATUS.md` curto e, se houver decisões de processamento importantes, `docs/ARCHITECTURE.md` + ADRs mínimos. Explicar `v/` e `v0/` como ativos, históricos ou outputs.

## 6. Lições transversais

### Problema 1 — documentação demais também perde contexto

Primos/XY mostram que boa provenance pode degradar onboarding quando várias camadas tentam representar “agora”.

**Política:** histórico cresce; estado vivo não.

### Problema 2 — “resumo executivo” pode virar segundo status

Quando resumo recebe overrides, NEXT e blockers próprios, passa a competir com `STATUS`.

**Política:** resumo é view; owner é único.

### Problema 3 — append-only não serve como ponteiro corrente

Ledgers preservam causalidade, mas obrigar o chat a localizar o último bloco é armadilha.

**Política:** ledger + current pointer curto.

### Problema 4 — arquitetura antiga precisa de estatuto explícito

Simulador mostra um bom padrão ao marcar v0.6 como legado. O problema surge quando outro documento de frente não recebe o mesmo encerramento.

**Política:** supersessão/arquivo explícitos.

### Problema 5 — source-of-truth pode ser clara e ainda duplicada

Formalismo declara JSON owner, mas repete manualmente o estado em várias views.

**Política:** mirrors devem ser gerados ou minimalistas.

### Problema 6 — repositório pequeno também precisa de handoff

Imagem Satélite mostra que um README funcional não preserva decisões, blockers e next.

**Política:** STATUS mínimo inclusive em projetos simples.

## 7. Prioridade sugerida de correção dos projetos existentes

1. **Primos:** eliminar conflito de owners/onboarding e reconciliar `02_ESTADO_ATUAL` com o P0 mais recente.
2. **Imagem Satélite:** criar status mínimo e tipar diretórios/versionamento.
3. **Simulador:** fechar/superseder `V07_PRIMEIRA_FRENTE` e declarar next atual.
4. **XY:** implementar ponteiros `CURRENT` curtos sem destruir ledgers/locks.
5. **Formalismo:** reduzir duplicação manual e separar current state de registry completo.

Nenhuma dessas migrações deve apagar provenance histórica.
