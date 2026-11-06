# Skill — Modelagem Físico-Matemática: Derivação, Redução e Validação

`SKILL_ROLE = CORE`

Pergunta central: **como compreender, reduzir e resolver matematicamente com o menor custo necessário?**

Use quando houver conteúdo físico-matemático material: equações, dinâmica, EDO/EDP, variacionais, estabilidade, assintótica, problemas inversos, condicionamento ou redução.

## Estratégia central

```text
FORMULAR
-> VERIFICAR ESTRUTURA
-> REDUZIR
-> DERIVAR
-> APROXIMAR SE NECESSÁRIO
-> CALCULAR
-> VALIDAR
-> IMPLEMENTAR
```

Computação não substitui estrutura matemática.

## Gate epistemológico

Antes de derivar sobre hipótese material, diferencie:

```text
GIVEN/OBSERVED
VERIFIED
SUPPORTED
HYPOTHESIS
UNKNOWN
```

Não trate hipótese física, condição, parâmetro, mecanismo causal ou regime assumido como fato porque produz uma derivação coerente.

Se a validade da solução depende materialmente de uma hipótese não verificada, primeiro defina e execute teste, inspeção ou pesquisa capaz de discriminá-la. A derivação pode ser exploratória apenas se rotulada como condicional:

```text
IF HYPOTHESIS H IS TRUE -> RESULT R
```

e não deve ser promovida a resultado do sistema antes da validação de H.

## Antes de escalar método

Classifique o problema conforme necessário:

```text
static/dynamic
discrete/continuous
deterministic/stochastic
direct/inverse
linear/nonlinear
well-posed/potentially ill-posed
```

Procure primeiro:

1. consistência dimensional e restrições físicas;
2. identidades, conservação, simetrias/invariantes;
3. mudança de coordenadas/adimensionalização;
4. eliminação/redução algébrica e dimensional;
5. solução analítica/variacional/espectral/assintótica;
6. método semianalítico ou numérico reduzido;
7. otimização/exploração pesada somente se necessária.

### STRUCTURE_FIRST

```text
BASES
-> IDENTIDADES/RESTRIÇÕES/INVARIANTES
-> SIMETRIAS
-> ELIMINAÇÃO ALGÉBRICA
-> REPARAMETRIZAÇÃO/ADIMENSIONALIZAÇÃO
-> REDUÇÃO DIMENSIONAL
-> ANALÍTICO/SEMIANALÍTICO
-> NUMÉRICO REDUZIDO
-> OTIMIZAÇÃO
-> FORÇA BRUTA
```

```text
BRUTE_FORCE_ALLOWED
IFF REDUCTION_ATTEMPTED
AND REMAINING_SEARCH_SPACE_JUSTIFIED
```

Se não consegue explicar o que não pôde ser reduzido e por quê, não escale a busca.

## Checks estruturais obrigatórios quando pertinentes

- existência/unicidade/estabilidade;
- condicionamento e identificabilidade;
- unidades e domínio de validade;
- invariantes e limites conhecidos;
- sensitividade aos parâmetros relevantes;
- separação entre erro de modelo e erro numérico.

Não invente variável, parâmetro, unidade, condição inicial/contorno ou recurso computacional ausente.

## Gate antes de nova solução em código

Apresente e valide com o usuário quando o contrato exigir nova tese/modelo:

```text
MATHEMATICAL_THESIS
STRUCTURAL_ASSUMPTIONS
VARIABLES/DOMAIN/UNITS
GOVERNING_EQUATIONS
PROPOSED_REDUCTION
VALIDATION/FALSIFICATION_CRITERIA
COMPUTATIONAL_ENVELOPE
```

Checks, inspeções e execução já autorizada não devem ser bloqueados artificialmente por esse gate.

## Validação

Conforme aplicável, teste:

```text
DIMENSIONAL_CONSISTENCY
KNOWN_LIMITS
SPECIAL_CASES
INVARIANTS
BOUNDARY/INITIAL_CONDITIONS
STABILITY
RESIDUAL/ERROR_ORDER
NUMERICAL_CONVERGENCE
PHYSICAL_PLAUSIBILITY
```

## Recursos

CPU/GPU são propriedades do runtime atual, não do projeto. Verifique o envelope real. Com VRAM extrema, prefira CPU para simbólico/dedutivo e GPU apenas onde a operação matricial justificar memória e transferência.

## Referência sob demanda

Consulte `references/MODELAGEM_FISICO_MATEMATICA_DERIVACAO_REDUCAO_VALIDACAO_REFERENCIA.md` somente quando precisar escolher ou aprofundar módulos como:

- Lagrangiana/Hamiltoniana, Noether, Lie;
- sistemas dinâmicos, EDO/EDP;
- controle ótimo e adjuntos;
- problemas inversos/regularização;
- análise espectral;
- perturbações, múltiplas escalas, WKB/homogeneização;
- geometria diferencial;
- redução de ordem;
- álgebra linear numérica e métodos especializados.

> Use o método mais simples capaz de responder rigorosamente à pergunta atual.
