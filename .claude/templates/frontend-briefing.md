# Briefing Front-end: <Nome da tela ou componente>

**Objetivo:** <uma frase: o que será desenvolvido e para quê>
**Figma:** [frame principal](<url com node-id>) · [estados e acessibilidade](<url>) · [notas de handoff](<url>)
**Escopo do design:** <breakpoints desenhados, ex.: só desktop 1536px>. <Observação sobre imagens: placeholders ou finais>.

## Estrutura
<Árvore do componente em tópicos: seção, painéis, elementos internos, com o texto exato de cada rótulo.>

<Se houver variações do mesmo componente, uma tabela:>

| Variação | <atributo 1> | <atributo 2> | <atributo 3> |
|---|---|---|---|
| <1> | | | |

## Especificação

**Cores**

| Uso | Hex |
|---|---|
| <fundo da página> | `#` |
| <ação principal> | `#` |
| <texto principal> | `#` |

**Tipografia (<família>)**

| Elemento | Tamanho / altura de linha | Peso | Letter-spacing |
|---|---|---|---|
| <título> | <px> / <px> | <peso> | <px> |
| <corpo> | | | |

**Medidas**
- <Container, margens e gaps entre blocos>
- <Largura e padding dos painéis>
- <Altura, raio e borda dos controles>
- <Cards: colunas, gap, raio, altura>

## Comportamento
- **<Controle 1>:** <o que acontece ao interagir>
- **<Controle 2>:** <o que acontece ao interagir>
- **Links e destinos:** <para onde cada clique leva>

## Acessibilidade (WCAG 2.1 AA)
- **Contrastes:** <resultado geral e o menor valor, com a razão e se é texto grande>
- **Exceção:** <par de cores que falha, com a razão medida e a cor proposta com sua razão>
- **Semântica:** <roles, aria-selected, aria-label, hierarquia de títulos>
- **Foco:** `:focus-visible` com anel de 2px e offset de 2px (<cor sobre fundo escuro>, <cor sobre fundo claro>), como no frame de estados.
- **Imagens e ícones:** `alt` descritivo; ícones decorativos com `aria-hidden="true"`.
- **Alvos de toque:** <tamanho atual e o mínimo recomendado no mobile>

## Critérios de aceite
- [ ] <Tela confere com o Figma (cores, tipografia e medidas).>
- [ ] <Interações principais funcionam com mouse, teclado e toque.>
- [ ] <Ação crítica (ex.: adicionar ao carrinho) funciona sem recarregar a página.>
- [ ] Foco visível em todos os controles.
