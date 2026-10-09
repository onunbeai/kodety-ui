# Kodety UI

Skill para criar e refinar interfaces de produto com composição cuidadosa, tipografia precisa, superfícies em camadas e controles personalizados.

## Instalação

Com Node.js e npm instalados:

```sh
npx skills add matusaelhorch/kodety-ui --skill kodety-ui
```

Para instalar globalmente no Codex:

```sh
npx skills add matusaelhorch/kodety-ui --skill kodety-ui --agent codex --global
```

Opções documentadas no [CLI Skills](https://github.com/vercel-labs/skills#install-a-skill).

## Uso

Peça ao agente:

```text
Use $kodety-ui para criar ou refinar esta interface.
```

## Conteúdo

- `SKILL.md`: direção visual, requisitos e fluxo de trabalho.
- `references/`: receitas para sidebars, cards, controles, tokens, acessibilidade e revisão visual.
- `references/images/`: imagens de referência para calibrar a composição.
- `assets/kodety-ui.css`: tokens e primitivas visuais opcionais.
- `agents/openai.yaml`: metadados para o Codex.

A skill exige Keyline Icons para ícones de interface e SVGs autênticos para marcas. Os arquivos de ícones devem ser obtidos na fonte indicada em [ícones e logos](references/icons-and-logos.md).

Consulte [SKILL.md](SKILL.md) para as instruções completas.
