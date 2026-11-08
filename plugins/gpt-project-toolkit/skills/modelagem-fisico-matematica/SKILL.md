---
name: modelagem-fisico-matematica
description: Formule, reduza, derive e valide problemas físico-matemáticos envolvendo equações, dinâmica, EDO/EDP, variacionais, estabilidade, assintótica, problemas inversos, condicionamento, identificabilidade e redução de ordem. Use quando houver conteúdo matemático/físico material e redução estrutural puder substituir força bruta.
---

# Modelagem Físico-Matemática

Leia `references/COORDENACAO_SKILLS.md`. Esta skill governa **formulação, redução e validação matemática**, não prioridade macro nem estrutura física do repositório.

## Gate epistemológico

Diferencie explicitamente dado/observação, resultado verificado, evidência parcial e hipótese.

Se uma derivação depende materialmente de hipótese não validada, primeiro investigue a hipótese ou mantenha o resultado estritamente condicional:

```text
IF HYPOTHESIS H IS TRUE -> RESULT R
```

Não promova R a resultado do sistema até validar H.

```text
HYPOTHESIS_VALIDATION_GATE
-> SOURCE/TEST
-> EVIDENCE
-> ALTERNATIVES
-> STATUS UPDATE
```

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

Antes de escalar, procure consistência dimensional, restrições, identidades, conservação, simetrias, reparametrização, redução algébrica/dimensional, solução analítica/assintótica e numérico reduzido.

```text
BRUTE_FORCE_ALLOWED
IFF REDUCTION_ATTEMPTED
AND REMAINING_SEARCH_SPACE_JUSTIFIED
```

Não invente variável, parâmetro, unidade, condição inicial/contorno ou recurso computacional ausente.

Valide, conforme aplicável: existência/unicidade/estabilidade, unidades, domínio de validade, invariantes, limites, sensibilidade, condicionamento, convergência e plausibilidade física.

Leia `references/REFERENCIA_APROFUNDADA.md` quando precisar de módulos avançados.

## Fechamento de verificação acessível

Se detectar inconsistência, obsolescência ou incerteza material que possa verificar com os acessos atuais, investigue na tarefa corrente até identificar a fonte/estado corrente e delimitar o impacto material. Não devolva ao usuário uma verificação que o próprio agente pode executar. Siga owner/fonte, referências diretas e dependentes materiais e pare quando o impacto estiver delimitado.

`NO_UNRESOLVED_VERIFICATION_HANDOFF = TRUE`
