# Referência aprofundada — Engenharia de Simulação, Sistemas e Automação

`DOCUMENT_ROLE = SKILL_REFERENCE`

> Não carregar por padrão. O core operacional está em `../ENGENHARIA_SIMULACAO_SISTEMAS_AUTOMACAO.md`.

> Esta skill pressupõe os fundamentos universais em `../FUNDAMENTOS/README.md`. Não duplica nem substitui postura, propagação de desbloqueios, preservação de bases ou reuse gate.

## Quando usar

Use esta skill quando a tarefa envolver, de forma material:

- modelagem de sistemas;
- simulação;
- otimização;
- arquitetura de software;
- automação;
- sistemas autônomos;
- engenharia de processos;
- planejamento;
- controle;
- computação científica;
- sistemas distribuídos;
- engenharia de decisão.

## Quando não usar

Evite esta skill quando a tarefa for apenas:

- edição textual simples;
- atividade administrativa sem modelagem ou automação;
- consulta factual;
- CRUD trivial;
- alteração cosmética de interface;
- trabalho já integralmente governado por contrato local mais específico que torne esta camada redundante.

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

Preservar um NOGO/FAIL não autoriza extrapolação. Quando nova evidência ou mudança de sistema afetar sua base, aplique os fundamentos de reavaliação e propagação.

Se houver conflito, prevalece a governança superior e o conflito deve ser explicitado.

---

# 1. Objetivo

Atuar como especialista de alto nível em:

- modelagem de sistemas;
- simulação;
- otimização;
- arquitetura de software;
- automação;
- sistemas autônomos;
- engenharia de processos;
- planejamento;
- controle;
- computação científica;
- sistemas distribuídos;
- engenharia de decisão.

O objetivo é transformar problemas reais em sistemas:

- formalmente definidos;
- simuláveis;
- verificáveis;
- reproduzíveis;
- eficientes;
- robustos;
- auditáveis;
- extensíveis;
- seguros para automação.

Regra fundamental:

> compreender o sistema antes de implementar o sistema.

---

# 2. Modelagem antes da implementação

Antes de escolher linguagem, biblioteca, framework ou algoritmo, formalizar:

```text
ENTIDADES
ESTADOS
AÇÕES
EVENTOS
RECURSOS
RESTRIÇÕES
DEPENDÊNCIAS
TRANSIÇÕES
OBJETIVOS
OBSERVAÇÕES
INCERTEZAS
```

Não deixar conceitos fundamentais implícitos no código.

---

# 3. Separação de camadas conceituais

Sempre distinguir:

```text
MODELO DO DOMÍNIO
MODELO DE ESTADO
MOTOR DE EXECUÇÃO
POLÍTICA DE DECISÃO
OTIMIZADOR
INTERFACES EXTERNAS
OBSERVABILIDADE
```

Nunca misturar deliberadamente:

- regra do mundo;
- regra de decisão;
- detalhe de implementação.

---

# 4. Estado explícito

Todo sistema relevante deve possuir estado formalmente representado.

O estado precisa poder ser:

- consultado;
- validado;
- serializado;
- comparado;
- persistido;
- reproduzido;
- auditado.

Evitar estado oculto em:

- variáveis globais;
- efeitos colaterais;
- closures;
- ordem acidental;
- callbacks implícitos.

---

# 5. Transições explícitas

Toda ação deve possuir:

```text
PRECONDIÇÕES
ENTRADA
AÇÃO
TRANSIÇÃO
EFEITOS
SAÍDA
FALHAS POSSÍVEIS
```

Uma mudança de estado sem causa identificável deve ser considerada defeito de modelagem.

---

# 6. Invariantes

Identificar invariantes estruturais do sistema.

Exemplos genéricos:

```text
capacidade >= utilização
estoque >= 0
estado pertence ao domínio permitido
recurso exclusivo não possui dois owners simultâneos
evento final não ocorre antes do evento inicial
```

Transformar invariantes importantes em validações automáticas.

---

# 7. Restrições duras e flexíveis

Separar:

```text
HARD_CONSTRAINTS
SOFT_CONSTRAINTS
PREFERENCES
OBJECTIVES
```

Uma restrição física ou lógica não deve virar penalidade arbitrária apenas para facilitar otimização.

---

# 8. Objetivos múltiplos

Antes de criar uma função objetivo escalar, identificar todas as métricas relevantes.

Exemplos:

- tempo;
- custo;
- energia;
- utilização;
- risco;
- atraso;
- qualidade;
- throughput;
- robustez;
- complexidade.

Utilizar quando adequado:

- otimização lexicográfica;
- Pareto;
- prioridades;
- constraints com objetivo secundário.

Evitar pesos arbitrários sem significado operacional.

---

# 9. Escolha correta do paradigma de simulação

Determinar primeiro a natureza temporal do sistema.

Possibilidades:

- eventos discretos;
- tempo contínuo;
- passos discretos;
- sistemas híbridos;
- modelos baseados em agentes;
- processos estocásticos.

Não escolher paradigma por preferência de biblioteca.

---

# 10. Tempo como variável formal

Definir explicitamente:

```text
UNIDADE DE TEMPO
RELÓGIO
ORDENAÇÃO DE EVENTOS
EVENTOS SIMULTÂNEOS
ATRASOS
JANELAS
DEPENDÊNCIAS TEMPORAIS
```

Nunca depender de ordem incidental de execução para definir causalidade.

---

# 11. Causalidade

Manter a cadeia:

```text
CAUSA
→ EVENTO
→ TRANSIÇÃO
→ NOVO ESTADO
```

Evitar atualizar estado apenas porque uma determinada função foi chamada.

---

# 12. Sistemas determinísticos e estocásticos

Classificar explicitamente fontes de incerteza.

Distinguir:

```text
INCERTEZA ALEATÓRIA
INCERTEZA DE MODELO
INCERTEZA DE PARÂMETRO
INCERTEZA DE OBSERVAÇÃO
```

Não introduzir aleatoriedade onde o sistema é determinístico apenas para “realismo”.

---

# 13. Aleatoriedade reproduzível

Quando houver stochasticidade:

- utilizar seeds;
- registrar distribuições;
- registrar parâmetros;
- separar geração aleatória da lógica;
- permitir replay.

---

# 14. Engenharia de experimentos

Não testar modelos apenas em grandes cenários.

Construir progressão:

```text
CASO MÍNIMO
→ CASO CONTROLADO
→ CASO LIMITE
→ CASO REALISTA
→ ESCALA
```

Sempre que possível, usar casos pequenos cuja solução possa ser conhecida.

---

# 15. Baselines

Toda técnica sofisticada deve ser comparada contra uma referência simples.

Possíveis baselines:

- política atual;
- greedy;
- FIFO;
- nearest-first;
- solução determinística simples;
- random;
- heurística trivial.

Sem baseline, ganho não é demonstrado.

---

# 16. Verificação e validação

Distinguir:

```text
VERIFICAÇÃO
= o sistema implementa corretamente o modelo?

VALIDAÇÃO
= o modelo representa suficientemente o fenômeno?
```

Nunca tratar ambas como a mesma coisa.

---

# 17. Análise de sensibilidade

Investigar:

- quais parâmetros dominam o resultado;
- quais possuem pouca influência;
- quais provocam mudança de regime;
- quais decisões são frágeis.

Não gastar recursos explorando parâmetros irrelevantes.

---

# 18. Robustez

Não buscar apenas solução ótima nominal.

Avaliar desempenho sob:

- perturbações;
- ruído;
- atraso;
- falha;
- variação de parâmetros;
- cenários adversos.

Quando aplicável considerar:

- otimização robusta;
- stochastic programming;
- cenários;
- intervalos;
- chance constraints.

---

# 19. Complexidade computacional

Antes de implementar, estimar quando relevante:

```text
TEMPO
MEMÓRIA
ESCALABILIDADE
PARALELISMO
COMPLEXIDADE ASSINTÓTICA
```

Não resolver um problema de arquitetura adicionando hardware.

---

# 20. Redução antes de escala

Buscar:

- simplificação algorítmica;
- decomposição;
- pruning;
- agregação;
- redução dimensional;
- pré-computação;
- memoização;
- índices;
- representação esparsa.

Força bruta é último recurso.

---

# 21. Escolha algorítmica

Preferir a técnica mais simples que resolva corretamente o problema.

Escalonamento recomendado:

```text
REGRA EXATA
↓
ALGORITMO DETERMINÍSTICO
↓
PROGRAMAÇÃO DINÂMICA
↓
OTIMIZAÇÃO EM GRAFOS
↓
CONSTRAINT PROGRAMMING
↓
PROGRAMAÇÃO MATEMÁTICA
↓
HEURÍSTICAS
↓
METAHEURÍSTICAS
↓
BUSCA AVANÇADA
↓
APRENDIZADO
```

Não usar ML ou IA quando algoritmo clássico for suficiente.

---

# 22. Hard skills algorítmicas

Dominar e considerar quando pertinentes:

- algoritmos em grafos;
- shortest path;
- minimum spanning tree;
- flow;
- matching;
- assignment;
- scheduling;
- dynamic programming;
- branch and bound;
- constraint programming;
- linear programming;
- integer programming;
- convex optimization;
- nonlinear optimization;
- local search;
- metaheurísticas;
- search algorithms;
- planning algorithms.

---

# 23. Hard skills de simulação

Dominar:

- discrete-event simulation;
- stochastic simulation;
- agent-based simulation;
- continuous simulation;
- hybrid simulation;
- Monte Carlo;
- queueing systems;
- finite-state systems;
- event-driven architectures.

---

# 24. Hard skills matemáticas

Quando necessárias:

- álgebra linear;
- probabilidade;
- estatística;
- cálculo;
- EDOs;
- otimização;
- teoria de grafos;
- processos estocásticos;
- teoria de filas;
- análise numérica;
- métodos iterativos;
- análise assintótica.

---

# 25. Hard skills de arquitetura

Dominar:

- modularidade;
- encapsulamento;
- composição;
- interfaces;
- dependency inversion;
- separação de responsabilidades;
- event sourcing;
- state machines;
- message passing;
- concorrência;
- paralelismo;
- pipelines;
- sistemas distribuídos.

---

# 26. Core puro

Sempre que possível, estruturar o núcleo como:

```text
ESTADO + AÇÃO
→ TRANSIÇÃO
→ NOVO ESTADO
```

Manter fora do core:

- banco;
- rede;
- API;
- filesystem;
- UI;
- mensageria.

Isso facilita teste e replay.

---

# 27. Determinismo controlável

Mesmo sistemas complexos devem permitir modo determinístico quando tecnicamente possível.

Isso é essencial para:

- debugging;
- comparação;
- regressão;
- reprodução de falhas.

---

# 28. Idempotência

Toda operação externa deve responder:

```text
O QUE ACONTECE SE ESTA AÇÃO FOR EXECUTADA DUAS VEZES?
```

Quando necessário utilizar:

```text
operation_id
idempotency_key
state_version
```

---

# 29. Concorrência

Quando houver múltiplos processos, workers ou agentes, definir:

```text
OWNERSHIP
LOCKING
ATOMICIDADE
VERSIONAMENTO
CONFLITO
RETRY
```

Concorrência sem semântica explícita é fonte de inconsistência.

---

# 30. Máquinas de estado

Quando comportamento possuir fases distintas, preferir estados explícitos.

Exemplo genérico:

```text
IDLE
READY
EXECUTING
WAITING
VERIFYING
FAILED
RECOVERING
COMPLETED
```

Não representar workflows complexos apenas por encadeamento de `if`.

---

# 31. Comando e evento

Distinguir:

```text
COMMAND
= intenção

EVENT
= fato ocorrido
```

Essa separação é fundamental em sistemas assíncronos e automações.

---

# 32. Event log

Registrar eventos relevantes com:

```text
timestamp
entity
event
previous_state
action
new_state
cause
operation_id
```

O histórico deve permitir entender como o sistema chegou ao estado atual.

---

# 33. Observabilidade

Implementar quando pertinente:

- logs estruturados;
- métricas;
- tracing;
- contadores;
- timings;
- códigos de erro;
- estado operacional.

Sistema sem observabilidade não deve ser considerado operacionalmente maduro.

---

# 34. Falhas como parte do modelo

Representar explicitamente:

```text
SUCCESS
FAILURE
TIMEOUT
PARTIAL
CANCELLED
INVALID
UNAVAILABLE
```

Nunca transformar timeout ou execução parcial em sucesso implícito.

---

# 35. Recovery

Toda automação relevante precisa de estratégia de recuperação.

Perguntar:

```text
SE FALHAR AQUI, COMO O ESTADO É RECUPERADO?
```

Considerar:

- retry;
- rollback;
- compensação;
- checkpoint;
- replay;
- intervenção manual.

---

# 36. Checkpoints

Em processos longos, persistir pontos de progresso úteis.

Evitar arquiteturas onde qualquer falha obriga reiniciar tudo.

---

# 37. Automação segura

Nunca permitir que decisão probabilística tenha acesso irrestrito a ação crítica.

Arquitetura recomendada:

```text
OBSERVAR
↓
INTERPRETAR
↓
PROPOR
↓
VALIDAR
↓
EXECUTAR
↓
VERIFICAR
```

---

# 38. Planejador e executor separados

Separar:

```text
PLANNER
VALIDATOR
EXECUTOR
```

O planner pode produzir solução inválida.

O validator deve bloquear execução inválida.

---

# 39. Ações tipadas

Preferir ações estruturadas e schemas definidos.

Evitar comandos externos puramente em texto livre quando houver consequências reais.

---

# 40. Sistemas autônomos

Todo agente autônomo deve possuir:

```text
OBSERVAÇÃO
ESTADO
OBJETIVO
POLÍTICA
AÇÃO
VALIDAÇÃO
FEEDBACK
```

Não confundir agente conversacional com agente operacional.

---

# 41. Critério para uso de LLM

LLM é apropriado para:

- interpretação;
- linguagem natural;
- classificação semântica;
- planejamento de alto nível;
- geração de alternativas;
- interação humana;
- recuperação contextual.

Não deve substituir diretamente:

- validação matemática;
- cálculo determinístico;
- regras críticas;
- restrições duras;
- autorização;
- contabilização de estado.

---

# 42. Sistemas multiagente

Só usar múltiplos agentes quando houver justificativa estrutural.

Exemplos:

- decomposição natural;
- competências distintas;
- paralelismo útil;
- autoridades separadas;
- ambientes competitivos ou cooperativos.

Não multiplicar agentes apenas para aumentar aparência de sofisticação.

---

# 43. Hierarquia de decisão

Quando o problema possui escalas distintas, decompor quando adequado:

```text
ESTRATÉGICO
↓
TÁTICO
↓
OPERACIONAL
```

Não obrigar um único algoritmo a resolver todas as escalas simultaneamente.

---

# 44. Integração com sistemas externos

Manter adaptadores explícitos para:

- APIs;
- banco de dados;
- arquivos;
- mensageria;
- sensores;
- serviços externos.

O domínio não deve depender diretamente dessas interfaces.

---

# 45. Contratos de interface

Toda interface relevante deve definir:

```text
INPUT
OUTPUT
ERRORS
TIMEOUT
RETRY
VERSION
```

Não depender de comportamento informal.

---

# 46. Versionamento de estado

Quando ações concorrentes ou persistência importarem, associar versões ao estado.

Evitar sobrescrita silenciosa.

---

# 47. Reprodutibilidade operacional

Toda execução relevante deve conseguir registrar:

```text
MODEL_VERSION
CODE_VERSION
CONFIGURATION
INPUTS
SEED
START_STATE
OUTPUT
FINAL_STATE
```

---

# 48. Performance

Otimizar somente depois de localizar gargalo.

Sequência:

```text
MEDIR
↓
LOCALIZAR
↓
ENTENDER
↓
OTIMIZAR
↓
MEDIR NOVAMENTE
```

Não otimizar por intuição.

---

# 49. Profiling

Usar profiling para identificar:

- CPU hotspots;
- uso de memória;
- alocações;
- IO;
- locks;
- waits;
- chamadas redundantes.

---

# 50. CPU, GPU e paralelismo

Não presumir que GPU é superior.

Avaliar:

- tamanho do problema;
- transferência de dados;
- paralelismo;
- memória;
- overhead;
- intensidade aritmética.

GPU deve ser utilizada quando o padrão computacional justificar.

Recursos computacionais são voláteis por sessão, aba, executor ou conector. Verificar o envelope real antes de fixar estratégia.

---

# 51. Estruturas de dados

Escolher estruturas com base no padrão real de acesso.

Considerar:

- arrays;
- hash maps;
- heaps;
- trees;
- graphs;
- sparse matrices;
- queues;
- priority queues;
- ring buffers.

Estrutura inadequada pode custar mais que algoritmo inadequado.

---

# 52. Cache

Cache só deve existir quando:

- custo de recomputação é significativo;
- chave é corretamente definida;
- invalidação possui semântica clara.

Evitar cache sem estratégia de invalidação.

---

# 53. Persistência

Separar:

```text
CURRENT_STATE
HISTORY
CONFIGURATION
DERIVED_DATA
CACHE
```

Não transformar banco de dados em depósito indiferenciado.

---

# 54. Testes

Construir:

- unit tests;
- integration tests;
- property-based tests;
- regression tests;
- invariant tests;
- end-to-end tests quando necessários.

---

# 55. Property-based testing

Quando possível, testar propriedades em vez de somente exemplos.

Exemplo:

```text
para todo estado válido:
    transição válida mantém invariantes
```

---

# 56. Testes diferenciais

Quando houver duas implementações da mesma função, compará-las automaticamente.

Útil para:

- otimizações;
- refactors;
- algoritmos novos;
- implementação GPU vs CPU.

---

# 57. Oráculos

Para problemas complexos, criar pequenos casos com resposta conhecida.

Eles servem como âncoras de corretude.

---

# 58. Fuzzing

Utilizar quando entradas complexas ou interfaces externas puderem gerar estados inesperados.

---

# 59. Validação de dados

Nunca assumir dados externos corretos.

Validar:

- tipo;
- domínio;
- integridade;
- unidade;
- cardinalidade;
- relações;
- consistência temporal.

---

# 60. Unidades

Quando houver grandezas físicas, usar unidades explicitamente.

Não misturar valores dimensionalmente incompatíveis.

---

# 61. Provenance

Resultados relevantes devem informar de onde vieram.

Preservar:

- input;
- transformação;
- versão;
- algoritmo;
- execução.

---

# 62. Critério de promoção

Uma técnica experimental só deve ser promovida quando demonstrar:

```text
CORRETUDE
GANHO
ROBUSTEZ
REPRODUTIBILIDADE
COMPATIBILIDADE
OBSERVABILIDADE
RECUPERAÇÃO
```

---

# 63. Critério contra sofisticação gratuita

Antes de adicionar:

```text
IA
MICROSERVIÇO
AGENTE
SOLVER
CACHE
CONCORRÊNCIA
GPU
METAHEURÍSTICA
```

perguntar:

```text
QUAL PROBLEMA MEDIDO ISTO RESOLVE?
```

Sem resposta objetiva, não adicionar.

---

# 64. Regra de fronteira

Quando um problema parecer difícil, buscar primeiro:

```text
ESTRUTURA
↓
DECOMPOSIÇÃO
↓
INVARIANTES
↓
ALGORITMO
↓
REDUÇÃO
↓
EXPERIMENTO MÍNIMO
↓
ESCALA
```

Não começar aumentando poder computacional.

---

# 65. Gate antes de implementação

Antes de construir solução relevante, formalizar:

```text
PROBLEMA
MODELO
ENTIDADES
ESTADOS
AÇÕES
TRANSIÇÕES
RESTRIÇÕES
OBJETIVOS
EVENTOS
INCERTEZAS
ALGORITMO PROPOSTO
BASELINE
CRITÉRIO DE VALIDAÇÃO
CUSTO COMPUTACIONAL
```

Se algum ponto essencial for desconhecido, marcar como:

```text
UNRESOLVED
```

Não inventar.

Este gate não deve impedir inspeções, checks, manutenção ou execução já explicitamente autorizada por contrato local; aplica-se à criação ou alteração material de solução, modelo, arquitetura ou política.

---

# 66. Regra final

O objetivo não é produzir o sistema mais sofisticado.

É produzir o sistema mais simples que seja:

- correto;
- suficientemente fiel;
- eficiente;
- robusto;
- observável;
- verificável;
- reproduzível;
- extensível.

Sempre priorizar:

```text
MODELO ANTES DE CÓDIGO
ESTADO ANTES DE EFEITO COLATERAL
RESTRIÇÃO ANTES DE OTIMIZAÇÃO
BASELINE ANTES DE IA
MEDIÇÃO ANTES DE OTIMIZAÇÃO
REPRODUTIBILIDADE ANTES DE ESCALA
VALIDAÇÃO ANTES DE AUTONOMIA
```
