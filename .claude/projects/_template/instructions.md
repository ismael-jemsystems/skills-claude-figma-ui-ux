# <Projeto> — Instruções de construção

Regras que a skill `figma-prototype` aplica ao montar telas deste projeto. Se um campo não se aplica, escreva "não se aplica". Se não for definido, a skill usa o padrão genérico (grade 4/8, alvo 44px) e declara como suposição.

## Idioma e conteúdo
- Idioma da UI: <ex.: inglês>. Idioma das anotações: <ex.: português>.
- Formato de preço, data e moeda: <ex.: $1,199.00>.
- Textos fixos de CTA e rótulos: <lista>.

## Breakpoints, containers e grade
| Breakpoint | Largura do conteúdo | Margem lateral | Observações |
|---|---|---|---|
| Desktop 1920 | | | |
| Desktop 1280 | | | |
| Tablet 768 | | | |
| Mobile 420 | | | |
| Mobile 360 | | | |

- Altura do header (desktop / mobile): <px>
- Grade e escala de espaçamento: <ex.: 4/8; 4, 8, 12, 16, 24, 32, 48>
- Convenção de nome dos frames: `<Tela> — Desktop 1920`.

## Tipografia e cores base
- Família e nomes de peso no Figma: <ex.: Inter, `Semi Bold`>
- Estilos de texto da biblioteca (com keys): veja `design-patterns.md`.
- Cor de ação principal: `#`. Texto principal: `#`. Texto secundário: `#`. Borda padrão: `#`. Raio padrão: <px>.

## Estados e variantes obrigatórios
<Variantes que toda tela deve cobrir. Ex.: tipos de usuário (logado / deslogado, e o que muda), estados de dados (disponível, esgotado, descontinuado), hover, foco, desabilitado, loading, erro, vazio.>

## Acessibilidade específica do projeto
- Anel de foco: <espessura, offset e cores sobre fundo claro e escuro>.
- Alvo de toque recomendado: <px>.
- Pares de cor que o design do projeto usa e **reprovam** (não reproduzir): <lista com hex e razão>.
- Exceções aceitas: <lista, ou "nenhuma">.

## Handoff e Notes
- Formato da anotação de comportamento: <ex.: título em caixa alta + "Comportamento:" com Desktop / Tablet / Mobile>.
- Estilo visual da Note: <ex.: cartão branco, borda 2px preta, sombra 4px 4px 0 #000>.
- Comportamentos recorrentes a lembrar: <ex.: carrossel automático, abas vazias ocultas, clique no card vai para a PDP>.

## Seções do arquivo Figma a ignorar
<Páginas e seções legadas ou marcadas como "não considerar".>
