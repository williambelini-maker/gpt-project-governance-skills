# Referência expandida de retomada

`DOCUMENT_ROLE = REFERENCE`

**Não usar como boot padrão.** Novos chats devem começar por `NOVO_CHAT/README.md`.

Consulte este guia apenas quando a retomada mínima não bastar, por exemplo:

- owner macro ausente/ambíguo;
- autoridade/owner ambíguo;
- múltiplos STATUS ou handoffs concorrentes;
- legado sem mapa claro;
- blocker/NOGO com escopo incerto;
- bases importantes enterradas em histórico;
- conflito entre especificações;
- `NEXT` encontrado mas sem justificativa macro;
- casa canônica de arquivos/outputs ambígua;
- entregável humano difícil de localizar;
- dúvida sobre qual documentação ou estrutura deve ser atualizada.

## Estratégia de recuperação

```text
INVENTÁRIO RASO
-> README/OWNERS
-> STRUCTURE_OWNER + USER_ACCESS_ZONE
-> MACRO_STATUS/ORIENTAÇÃO MACRO
-> STATUS DA FRENTE
-> BASES/CONTRATO/MAPA pertinentes
-> SKILL ROUTER
-> EVIDÊNCIA DIRECIONADA
-> ANTI_TUNNEL_GATE
-> NEXT
```

Não faça varredura ampla antes de seguir os ponteiros existentes.

Se houver divergência, determine owner e evidência; não escolha verdade por nome de arquivo, `mtime`, "final" ou pelo primeiro resultado encontrado.

Se o `NEXT` estiver claro mas `WHY_THIS_FRONT_NOW` não estiver, a recuperação **ainda não terminou**.

Se o agente vai criar artefatos mas não sabe onde a classe correspondente mora ou onde o usuário encontra a saída corrente, a recuperação estrutural também não terminou.

Quando a recuperação terminar e a próxima ação estiver globalmente justificada, volte ao fluxo de produção. Este documento não deve permanecer carregado por inércia.
