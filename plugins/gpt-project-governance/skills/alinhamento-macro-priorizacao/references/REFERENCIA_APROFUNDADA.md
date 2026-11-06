# Referência aprofundada — Alinhamento Macro, Priorização Científica e Valor de Informação

`DOCUMENT_ROLE = SKILL_REFERENCE`

> Não carregar por padrão. O core operacional está em `../ALINHAMENTO_MACRO_PRIORIZACAO_VALOR_INFORMACAO.md`.

> Esta skill pressupõe os fundamentos universais em `../FUNDAMENTOS/README.md`. Não duplica nem substitui postura, propagação de desbloqueios, escopo contextual de bloqueios ou reuse gate.

## Quando usar

Use esta skill quando a tarefa envolver, de forma material:

- estudos com múltiplas frentes, hipóteses, derivações ou experimentos;
- risco de confundir avanço local com avanço relevante;
- necessidade de priorizar investigações pelo impacto no objetivo macro;
- necessidade de integrar resultados parciais ao estado global do estudo;
- avaliação de bloqueadores, dependências, incertezas e decisões pendentes;
- comparação entre investigações concorrentes;
- necessidade de decidir quando continuar, rebaixar, congelar ou encerrar uma linha de trabalho;
- necessidade de distinguir nova informação de reformulação redundante;
- necessidade de medir progresso por redução de incerteza, eliminação de hipóteses, remoção de bloqueadores ou ganho decisório.

## Quando não usar

Evite esta skill quando a tarefa for apenas:

- edição textual simples;
- consulta factual isolada;
- alteração administrativa trivial;
- execução mecânica já integralmente prescrita por contrato local;
- tarefa sem objetivo macro, decisão, hipótese, dependência ou priorização relevante.

## Limites de autoridade

Esta skill é metodológica. Ela não pode sobrescrever:

- instrução explícita do usuário/operador;
- autoridade canônica do projeto;
- contratos locais;
- ADRs;
- locks ou freezes;
- NOGOs, FAILs ou decisões vigentes **dentro do escopo e das premissas que continuam aplicáveis**;
- escopo autorizado;
- evidência científica ou operacional promovida.

Preservar um NOGO/FAIL não significa extrapolá-lo. Se nova evidência, mudança de regime, hipótese ou modelo afetar sua base, aplique os fundamentos de reavaliação e propagação.

Se houver conflito, prevalece a governança superior e o conflito deve ser explicitado.

---

# 1. Objetivo

Atuar como camada de inteligência estratégica sobre qualquer estudo, modelo, derivação, experimento, simulação ou implementação.

A função desta skill é impedir que progresso local seja confundido com progresso relevante.

O agente deve avaliar continuamente:

- o objetivo macro;
- os bloqueadores reais;
- as hipóteses que sustentam o modelo;
- as decisões que ainda dependem de evidência;
- as derivações em andamento;
- o impacto potencial de cada resultado;
- o valor marginal da próxima investigação.

Princípio central:

> Progresso não é quantidade de trabalho realizado; é mudança material na capacidade de explicar, prever, decidir ou fechar o objetivo macro.

---

# 2. Reconstrução do objetivo macro

Antes de avaliar qualquer trabalho, formalizar:

```text
MACRO_OBJECTIVE
MACRO_SUCCESS_CRITERIA
MACRO_FAILURE_CRITERIA
MACRO_UNCERTAINTIES
MACRO_BLOCKERS
MACRO_DECISIONS_PENDING
```

O objetivo macro deve ser expresso em termos de resultado, não de atividade.

Evitar objetivos como:

- derivar mais relações;
- melhorar um solver;
- testar mais casos;
- aumentar precisão;
- executar mais simulações.

Preferir objetivos como:

- distinguir entre hipóteses concorrentes;
- determinar uma relação necessária;
- reduzir incerteza decisiva;
- fechar um parâmetro necessário;
- demonstrar ou refutar uma propriedade;
- tornar uma previsão ou decisão possível.

---

# 3. Cadeia obrigatória de impacto

Toda tarefa deve possuir uma cadeia explícita:

```text
OBJETIVO MACRO
→ BLOQUEADOR
→ PERGUNTA
→ HIPÓTESE
→ DERIVAÇÃO / EXPERIMENTO
→ RESULTADO POSSÍVEL
→ DECISÃO AFETADA
→ IMPACTO MACRO
```

Se a cadeia não puder ser construída, classificar a tarefa como:

```text
UNLINKED_TO_MACRO
```

Ela não deve receber prioridade alta sem justificativa específica.

---

# 4. Classificação obrigatória de resultados

Todo resultado novo deve ser classificado.

## MACRO

Altera materialmente:

- a tese principal;
- uma decisão central;
- um bloqueador estrutural;
- a capacidade preditiva;
- a identificabilidade;
- a validade do modelo;
- a viabilidade do objetivo.

## MESO

Não altera diretamente o objetivo macro, mas fecha uma dependência necessária e demonstrável para um avanço macro.

## LOCAL

Produz avanço interno, como:

- melhor bound;
- melhor parametrização;
- maior precisão;
- decomposição adicional;
- nova identidade;
- simplificação;
- resultado parcial;

sem mudança material imediata no estado macro.

## INFRAESTRUTURAL

Melhora capacidade operacional, como:

- runtime;
- memória;
- pipeline;
- solver;
- tooling;
- automação;
- observabilidade;
- documentação.

Não deve ser contado automaticamente como avanço científico ou macro.

---

# 5. Proibição de inflação de progresso

Nunca promover automaticamente como progresso macro:

- menor erro numérico;
- maior número de testes;
- maior rank;
- maior cobertura;
- melhor runtime;
- mais parâmetros explorados;
- mais teoremas locais;
- mais derivações;
- mais arquivos produzidos.

Antes de atribuir ganho, responder:

```text
WHAT_DECISION_CHANGED?
WHAT_UNCERTAINTY_WAS_REMOVED?
WHAT_BLOCKER_WAS_REDUCED?
WHAT_NEW_MACRO_CAPABILITY_EXISTS?
```

Sem resposta material, classificar como ganho local ou infraestrutural.

---

# 6. Ledger de dependências científicas

Manter uma representação explícita das dependências:

```text
DERIVATION_ID
QUESTION
WHY_IT_EXISTS
MACRO_LINK
INPUT_DEPENDENCIES
EXPECTED_INFORMATION
PASS_IMPLICATION
FAIL_IMPLICATION
DECISION_AFFECTED
CURRENT_PRIORITY
```

Toda derivação deve existir por uma razão rastreável.

Se a razão desaparecer, a derivação deve ser:

- rebaixada;
- congelada;
- encerrada.

---

# 7. Teste PASS / NOGO

Antes de executar uma investigação, responder:

```text
IF_PASS:
    o que muda?

IF_NOGO:
    o que muda?
```

Se PASS e NOGO produzirem praticamente o mesmo estado macro:

```text
VALUE_OF_INFORMATION = LOW
```

e a prioridade deve ser reduzida.

---

# 8. Valor de informação

Avaliar cada investigação pelo seu potencial de reduzir incerteza relevante.

Critérios:

```text
DECISION_SENSITIVITY
UNCERTAINTY_REDUCTION
MODEL_SPACE_REDUCTION
HYPOTHESIS_DISCRIMINATION
BLOCKER_REMOVAL
COST
TIME
DEPENDENCIES
```

Pensar qualitativamente como:

```text
VOI ≈
probabilidade_de_mudar_decisão
× magnitude_da_decisão
× redução_de_incerteza
/ custo
```

Não é necessário produzir um número artificial.

O objetivo é comparar oportunidades.

---

# 9. Teste de sensibilidade macro

Para cada variável, resultado ou refinamento, avaliar:

```text
Δ RESULTADO LOCAL
→ Δ ESTADO DO MODELO
→ Δ PREVISÃO / DECISÃO MACRO
```

Se grande variação local produzir impacto macro desprezível:

```text
MACRO_SENSITIVITY = LOW
```

e a prioridade deve cair.

---

# 10. Proxy trap

Toda métrica local deve ser tratada inicialmente como proxy.

Perguntar:

```text
POR QUE ESTA MÉTRICA REPRESENTA PROGRESSO REAL?
```

Exemplos de possíveis proxies enganosos:

- loss;
- residual;
- erro médio;
- rank;
- cobertura;
- throughput;
- número de casos;
- número de PASSes;
- precisão numérica.

Só utilizar uma métrica como critério de avanço se houver relação demonstrável com o objetivo macro.

---

# 11. Grafo de conhecimento e decisão

Representar o estudo como grafo, não como fila.

Nós podem representar:

- hipóteses;
- resultados;
- parâmetros;
- leis;
- evidências;
- decisões;
- bloqueadores;
- objetivos.

Arestas representam:

- depende de;
- implica;
- refuta;
- suporta;
- restringe;
- habilita.

A prioridade deve emergir do grafo atual.

Não continuar automaticamente uma sequência apenas porque já estava planejada.

---

# 12. Centralidade científica

Resultados mais centrais devem receber prioridade maior.

Avaliar:

- quantas decisões dependem do nó;
- quantos bloqueadores ele afeta;
- quantas hipóteses ele pode eliminar;
- quantas ramificações ele pode fechar;
- quanta informação futura ele habilita.

Uma pequena derivação central pode valer mais do que uma derivação enorme periférica.

---

# 13. Critério de fechamento

Uma linha de trabalho deve ser fechada ou colocada em stop produtivo quando:

- a pergunta relevante foi respondida;
- nenhum resultado restante pode alterar decisão macro;
- o valor marginal de informação ficou baixo;
- a linha depende de input externo inexistente;
- o restante é refinamento sem impacto material;
- outro caminho domina claramente em valor esperado.

Não confundir "ainda há coisas para calcular" com "a linha ainda merece continuar".

---

# 14. Critério de abertura

Uma nova investigação deve justificar:

```text
MACRO_QUESTION
WHY_NOW
EXPECTED_INFORMATION_GAIN
WHAT_CAN_BE_ELIMINATED
WHAT_DECISION_CAN_CHANGE
DEPENDENCIES
COST
```

Não abrir uma investigação apenas porque uma técnica matemática permite novos desdobramentos.

---

# 15. Reavaliação dinâmica

Após qualquer resultado relevante:

1. atualizar o grafo;
2. atualizar bloqueadores;
3. atualizar hipóteses;
4. atualizar incertezas;
5. atualizar dependências;
6. reavaliar todas as prioridades afetadas;
7. cancelar trabalho tornado desnecessário.

Planejamento antigo não possui autoridade sobre evidência nova.

---

# 16. Hierarquia de prioridade

Ordenar preferencialmente por:

1. capacidade de mudar decisão macro;
2. capacidade de remover bloqueador;
3. capacidade de falsificar hipótese central;
4. redução do espaço de modelos;
5. valor de informação;
6. centralidade no grafo;
7. custo;
8. reversibilidade;
9. risco.

---

# 17. Falsificação antes de refinamento

Antes de melhorar uma hipótese, procurar formas de refutá-la.

Preferir:

```text
TESTE DECISIVO
```

a:

```text
REFINAMENTO INCREMENTAL
```

quando ambos custarem aproximadamente o mesmo.

---

# 18. Resultados negativos

Um NOGO pode ter mais valor que um PASS.

Valorizar resultados que:

- eliminam classes inteiras de modelos;
- bloqueiam caminhos redundantes;
- demonstram não identificabilidade;
- provam impossibilidade;
- encerram hipóteses persistentes.

Nunca tratar resultado negativo como ausência de progresso.

---

# 19. Derivações pendentes

Toda derivação pendente deve carregar:

```text
PENDING_DERIVATION
MACRO_PURPOSE
EXPECTED_DECISION_IMPACT
DEPENDENCIES
CURRENT_INFORMATION_VALUE
STATUS
```

Reavaliar periodicamente.

Derivações que perderam ligação macro devem sair da fila principal.

---

# 20. Dívida de integração

Um resultado não está completamente concluído enquanto não tiver sido integrado ao modelo macro.

Após derivação relevante, verificar:

```text
MODEL_UPDATED?
ASSUMPTIONS_UPDATED?
DEPENDENCIES_UPDATED?
DECISIONS_UPDATED?
STATUS_UPDATED?
```

Se não:

```text
INTEGRATION_DEBT = OPEN
```

A prioridade pode ser integrar antes de produzir nova derivação.

---

# 21. Informação órfã

Detectar resultados que existem mas não foram incorporados.

Classificar:

```text
ORPHAN_RESULT
```

quando um resultado:

- está documentado;
- foi validado;
- mas não alterou a representação do estado do estudo.

Investigar se:

- é irrelevante;
- foi esquecido;
- possui consequência ainda não propagada.

---

# 22. Propagação de consequências

Após um resultado central, percorrer suas dependências.

Perguntar:

```text
WHAT DOES THIS INVALIDATE?
WHAT DOES THIS ENABLE?
WHAT BECOMES REDUNDANT?
WHAT SHOULD BE RECOMPUTED?
WHAT SHOULD BE STOPPED?
```

Evitar manter trabalho herdado que foi tornado obsoleto.

---

# 23. Separação entre importância e dificuldade

Não atribuir prioridade maior apenas porque algo é:

- matematicamente sofisticado;
- computacionalmente caro;
- intelectualmente interessante;
- difícil de concluir.

Prioridade depende de impacto esperado, não de dificuldade.

---

# 24. Separação entre precisão e utilidade

Mais precisão não é necessariamente mais informação.

Perguntar:

```text
A DECISÃO MUDA COM ESTA PRECISÃO ADICIONAL?
```

Se não mudar, refinamento pode ter baixo valor.

---

# 25. Critério de suficiência

Sempre procurar o nível mínimo de precisão necessário para responder à pergunta macro.

Evitar resolver com precisão excessiva um problema cuja decisão não depende dela.

---

# 26. Teoria das restrições

Identificar o gargalo dominante.

Se existe um bloqueador que limita toda a cadeia, priorizar ações que atuem nele.

Otimizar componentes não limitantes produz pouco ganho sistêmico.

---

# 27. Anti-subotimização

Nunca maximizar o desempenho de um componente sem verificar efeito global.

Perguntar:

```text
LOCAL_IMPROVEMENT
→ SYSTEM_EFFECT
```

Melhoria local que transfere problema para outro componente pode ter ganho global nulo ou negativo.

---

# 28. Portfólio de investigação

Quando houver múltiplas investigações possíveis, tratá-las como portfólio.

Avaliar:

- valor esperado;
- custo;
- dependência;
- risco;
- correlação de resultados;
- informação complementar.

Evitar investir toda capacidade em investigações altamente correlacionadas.

---

# 29. Diversidade informacional

Quando duas investigações testam quase a mesma hipótese com a mesma fonte de informação, o valor marginal da segunda pode ser baixo.

Preferir evidência independente quando possível.

---

# 30. Reversibilidade

Ações baratas e reversíveis podem ser exploratórias.

Ações caras ou irreversíveis exigem evidência mais forte.

A prioridade deve incorporar:

```text
COST_OF_BEING_WRONG
```

---

# 31. Evidência independente

Distinguir:

```text
NEW_INFORMATION
```

de:

```text
REFORMULATION_OF_EXISTING_INFORMATION
```

Uma nova transformação matemática do mesmo dado não constitui automaticamente nova evidência.

---

# 32. Redundância epistemológica

Se múltiplos resultados forem funções da mesma fonte de informação, não contá-los como evidências independentes.

Detectar:

- circularidade;
- reparametrização;
- recombinação;
- pós-processamento redundante.

---

# 33. Atualização da crença

Quando nova evidência surgir, perguntar:

```text
QUAL HIPÓTESE FICOU MAIS PROVÁVEL?
QUAL FICOU MENOS?
QUAL FOI ELIMINADA?
```

Mesmo sem formalismo bayesiano, o raciocínio deve refletir atualização real.

---

# 34. Estado de maturidade

Cada hipótese pode ser classificada como:

```text
OPEN
SUPPORTED
STRONGLY_SUPPORTED
REFUTED
UNIDENTIFIABLE
BLOCKED
CLOSED
```

Não manter hipóteses indefinidamente como "em estudo" após evidência suficiente.

---

# 35. Pontuação de prioridade

Quando útil, construir avaliação qualitativa:

```text
PRIORITY ≈
MACRO_IMPACT
× INFORMATION_GAIN
× DECISION_RELEVANCE
× CENTRALITY
/ COST
```

Aplicar penalidades para:

- redundância;
- dependência de hipótese frágil;
- baixa sensibilidade macro;
- alto custo;
- ausência de decisão afetada.

Não produzir falsa precisão numérica.

---

# 36. Perguntas obrigatórias antes de continuar trabalho local

Antes de continuar, responder:

```text
1. Qual objetivo macro isso serve?
2. Qual decisão pode mudar?
3. Qual hipótese pode ser eliminada?
4. Qual bloqueador pode ser removido?
5. PASS e NOGO levam a estados diferentes?
6. O resultado macro é sensível a esta variável?
7. Existe investigação mais barata e mais decisiva?
8. Isto é nova informação ou apenas refinamento?
```

---

# 37. Perguntas obrigatórias depois de um resultado

Depois de concluir uma derivação ou experimento:

```text
1. O que sabemos agora que não sabíamos?
2. Qual incerteza foi reduzida?
3. Qual decisão mudou?
4. Qual ramo morreu?
5. Qual ramo foi habilitado?
6. Qual trabalho planejado se tornou desnecessário?
7. O objetivo macro ficou materialmente mais próximo?
```

---

# 38. Formato padrão por ciclo

## Objetivo macro

Qual estado final está sendo buscado.

## Estado macro atual

O que já está estabelecido.

## Bloqueador dominante

O principal limitante.

## Resultado novo

O que foi obtido.

## Classe do resultado

```text
MACRO | MESO | LOCAL | INFRAESTRUTURAL
```

## Impacto causal

Como o resultado propaga até o objetivo macro.

## Incerteza removida

O que deixou de estar aberto.

## Decisão alterada

Qual escolha agora muda.

## Resultados pendentes de integração

O que ainda precisa ser propagado ao modelo.

## Valor marginal da linha atual

```text
HIGH | MEDIUM | LOW | EXHAUSTED
```

## Próxima prioridade

A ação com maior valor esperado de informação e impacto.

---

# 39. Critério de stop produtivo

Declarar:

```text
PRODUCTIVE_STOP
```

quando ainda existirem possíveis desdobramentos, mas nenhum deles possuir valor marginal suficiente para o objetivo atual.

Um stop produtivo é um resultado racional, não uma falha.

---

# 40. Critério de reabertura

Uma linha em stop só deve reabrir com:

- nova evidência;
- nova hipótese;
- novo observável;
- nova dependência;
- nova necessidade macro;
- mudança explícita de prioridade.

Não reabrir apenas porque ainda existem derivações possíveis.

---

# 41. Regra contra viés de continuidade

Tempo já investido não aumenta prioridade futura.

Ignorar sunk cost.

Perguntar sempre:

```text
SE ESTA LINHA COMEÇASSE HOJE, ELA AINDA SERIA PRIORIDADE?
```

Se não, repriorizar.

---

# 42. Regra contra viés de produção

Não premiar caminhos apenas porque produzem resultados frequentes.

Uma linha que produz dezenas de resultados locais pode ser menos valiosa que uma linha difícil com potencial de eliminar a principal incerteza.

---

# 43. Regra contra profundidade sem consequência

Não continuar aprofundando uma ramificação apenas porque existe estrutura adicional.

Profundidade só é relevante enquanto:

```text
MARGINAL_MACRO_VALUE > ALTERNATIVE_VALUE
```

---

# 44. Regra de integração contínua

Resultados importantes devem atualizar imediatamente:

- modelo conceitual;
- hipóteses;
- dependências;
- prioridades;
- estado documental.

Não acumular resultados desconectados em relatórios históricos.

---

# 45. Critério de qualidade

Avaliar o trabalho por:

```text
REDUÇÃO DE INCERTEZA
+
ELIMINAÇÃO DE HIPÓTESES
+
REMOÇÃO DE BLOQUEADORES
+
AUMENTO DE CAPACIDADE PREDITIVA
+
AUMENTO DE CAPACIDADE DECISÓRIA
+
REDUÇÃO DE ESPAÇO DE MODELOS
```

Não por volume de produção.

---

# 46. Compatibilidade com outras skills

Esta skill pode ser combinada com skills técnicas.

Exemplos de composição:

```text
ALINHAMENTO_MACRO_PRIORIZACAO_VALOR_INFORMACAO
+
MODELAGEM_FISICO_MATEMATICA_DERIVACAO_REDUCAO_VALIDACAO
```

quando for necessário decidir o que investigar e, depois, aplicar método físico-matemático rigoroso.

Ou:

```text
ALINHAMENTO_MACRO_PRIORIZACAO_VALOR_INFORMACAO
+
ENGENHARIA_SIMULACAO_SISTEMAS_AUTOMACAO
```

quando for necessário decidir onde investir capacidade e, depois, construir ou otimizar o sistema correspondente.

Esta skill orienta prioridade e integração; não substitui o método técnico específico.

---

# 47. Regra final

Sempre raciocinar de trás para frente:

```text
OBJETIVO MACRO
← DECISÃO NECESSÁRIA
← INFORMAÇÃO NECESSÁRIA
← PERGUNTA
← INVESTIGAÇÃO
```

Nunca apenas:

```text
TENHO UMA DERIVAÇÃO POSSÍVEL
→ VOU EXECUTÁ-LA
```

Regra máxima:

> Nenhuma investigação recebe prioridade por ser interessante, difícil ou produtiva localmente; ela recebe prioridade pelo quanto pode mudar o estado macro do conhecimento ou da decisão.
