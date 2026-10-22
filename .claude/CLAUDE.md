# CLAUDE.md

Instruções gerais para o Claude neste projeto.

## Estrutura da pasta .claude

- `skills/`: todas as skills instaladas ou criadas por nós.
- `memories/`: memórias de tarefas e informações que precisam ser guardadas para uso futuro.
- `templates/`: templates criados para devolutivas.
- `agents/`: agents personalizados que criarmos.
- `projects/`: uma pasta por projeto/cliente com tudo o que aprendemos de Figma e afins (índice, padrões de design, telas criadas e referências). Veja `projects/README.md`.

## Instruções gerais

- Responder em português (Brasil), salvo pedido em contrário.
- Salvar novas skills em `skills/`, memórias em `memories/`, templates em `templates/`, agents em `agents/` e conhecimento de um projeto (Figma, referências, padrões) em `projects/<slug>/`.
- Antes de criar uma devolutiva, verificar se existe um template adequado em `templates/`.
- Consultar `memories/` no início de tarefas que possam depender de contexto anterior.
- No início de uma tarefa de um projeto, ler `projects/<slug>/README.md`, `instructions.md` e a seção relevante de `design-patterns.md`. Ao terminar, registrar a tela em `screens.md` e atualizar `design-patterns.md` se algo novo foi aprendido.
- Projeto novo: copiar `projects/_template/` para `projects/<slug>/` e acrescentar a linha na tabela de `projects/README.md`.
