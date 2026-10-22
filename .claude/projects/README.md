# Projects

Uma pasta por projeto/cliente, com tudo o que aprendemos de Figma, ClickUp e referências. Use o slug em minúsculas (`fsg`, `cliente-x`).

## Projetos
| Slug | Projeto | Figma |
|---|---|---|
| [fsg](fsg/README.md) | Fire Services Group (e-commerce B2B, Hyva DS) | [Fire-Services-Group](https://www.figma.com/design/FcT5hOoA4LaSE3qTekDgfp/Fire-Services-Group) |

## Estrutura de cada projeto
- `README.md`: índice do projeto (arquivo Figma e `fileKey`, páginas e `node-id`, bibliotecas, links, ClickUp).
- `design-patterns.md`: tokens, componentes, regras de comportamento, acessibilidade e **pendências**. Cada valor marcado **[C]** confirmado, **[I]** inferido ou **[N]** não confirmado.
- `screens.md`: registro de cada tela criada ou analisada (página, `node-id`, breakpoints, estado, decisões e desvios).

## Como usar
- **Novo projeto:** copie `_template/` para `projects/<slug>/` e preencha o `README.md`. Depois acrescente uma linha na tabela acima.
- **Início de qualquer tarefa de um projeto:** leia `projects/<slug>/README.md` e a seção do `design-patterns.md` que a tarefa toca.
- **Fim da tarefa:** registre a tela em `screens.md`. Se aprendeu um padrão novo ou confirmou um **[N]**, atualize `design-patterns.md` (não crie arquivo duplicado).
- **Referências externas** (sites, prints, concorrentes) vão no `README.md` do projeto, com data e o que foi aproveitado.
- Não guarde segredos nem tokens aqui. Links temporários do Figma (assets) expiram em 7 dias e não devem ser salvos.
