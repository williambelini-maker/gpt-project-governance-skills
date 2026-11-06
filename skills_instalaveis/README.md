# Skills instaláveis

Esta pasta contém **bundles autocontidos** derivados da política e das skills-fonte deste repositório.

```text
skills_instalaveis/
├── README.md
├── ROTEAMENTO_E_PRECEDENCIA.md
└── pacotes/
    ├── governanca-projetos-continuidade/
    ├── organizacao-higiene-repositorio/
    ├── alinhamento-macro-priorizacao/
    ├── modelagem-fisico-matematica/
    └── engenharia-simulacao-sistemas-automacao/
```

Cada pasta em `pacotes/` contém **exatamente um `SKILL.md`** e seus recursos. Esse é o formato esperado para descoberta de skills. O `name` e o `description` no front matter são deliberadamente diferentes entre os pacotes para reduzir colisões de roteamento.

## Fonte de verdade

Os arquivos fora de `skills_instalaveis/` continuam sendo a fonte metodológica canônica. Os pacotes instaláveis são distribuições derivadas.

Ao alterar a política-fonte, reconcilie o bundle correspondente antes de publicar nova versão.

## Coordenação

Não trate os números, nomes de pasta ou ordem alfabética como prioridade de execução. Use `ROTEAMENTO_E_PRECEDENCIA.md`.

## Instalação

Cada diretório de `pacotes/` é um bundle individual. Carregue/empacote **uma skill por vez**; não envie a pasta `pacotes/` inteira como uma única skill, porque cada bundle possui seu próprio `SKILL.md`.
