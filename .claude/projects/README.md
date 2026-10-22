# Projects

Uma pasta por projeto/cliente, com tudo o que aprendemos de Figma, ClickUp e referências. Use o slug em minúsculas (`cliente-x`, `loja-y`). A skill `figma-prototype` descobre o projeto por aqui e lê as regras dele.

## Projetos
| Slug | Projeto | Figma |
|---|---|---|
| _nenhum ainda_ | | |

## Estrutura de cada projeto
- `README.md`: índice do projeto (arquivo Figma e `fileKey`, páginas e `node-id`, bibliotecas, links, ClickUp, referências externas).
- `instructions.md`: **regras de construção** que a skill aplica (idioma, breakpoints e containers, grade, tipografia e cores base, estados obrigatórios, foco, pares de cor reprovados, formato das Notes, seções a ignorar).
- `design-patterns.md`: tokens, componentes, regras de comportamento, acessibilidade e **pendências**. Cada valor marcado **[C]** confirmado, **[I]** inferido ou **[N]** não confirmado.
- `screens.md`: registro de cada tela criada ou analisada (página, `node-id`, breakpoints, estado, decisões e desvios).

## Como usar
- **Novo projeto:** copie `_template/` para `projects/<slug>/`, preencha `README.md` e `instructions.md`, e acrescente uma linha na tabela acima. Depois levante os padrões com o agent `figma-extractor`.
- **Início de qualquer tarefa de um projeto:** leia `README.md`, `instructions.md` e a seção do `design-patterns.md` que a tarefa toca.
- **Fim da tarefa:** registre a tela em `screens.md`. Se aprendeu um padrão novo ou confirmou um **[N]**, atualize `design-patterns.md`; se recebeu uma regra de construção nova, grave em `instructions.md`. Não crie arquivos duplicados.
- **Referências externas** (sites, prints, concorrentes) vão no `README.md` do projeto, com data e o que foi aproveitado.
- Não guarde segredos nem tokens aqui. Links temporários de assets do Figma expiram em 7 dias e não devem ser salvos.
