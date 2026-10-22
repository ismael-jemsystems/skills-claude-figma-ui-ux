# Skills Claude: Figma, UI/UX e acessibilidade

Configuração do Claude Code para prototipar telas no Figma com padrões de design, acessibilidade (WCAG 2.1 AA) e handoff para front-end. É independente de projeto: cada projeto guarda suas regras e referências em `.claude/projects/<slug>/`.

## O que faz
- Cria telas no Figma a partir de um link do ClickUp, de um texto no chat ou de um print, usando a biblioteca de design e as regras do projeto.
- Mede contraste, alvos de toque, foco e alt, e propõe correções.
- Compara uma réplica com o print original e ajusta as diferenças.
- Entrega um briefing para o time de front-end ao finalizar cada tela.

## Estrutura

```
.claude/
├── CLAUDE.md      instruções gerais para o Claude
├── skills/        skills instaladas e criadas
├── agents/        agents personalizados
├── templates/     templates de devolutiva
├── memories/      memórias de tarefas
└── projects/      conhecimento por projeto
```

### Skills (`.claude/skills/`)
| Skill | Para quê |
|---|---|
| `figma-prototype` | Monta protótipos no Figma lendo as regras de `projects/<slug>/`, valida acessibilidade e devolve o briefing de front-end. Também faz réplicas fiéis de um print. |
| `ui-ux-pro-max` | Biblioteca de regras de UI/UX (estilos, tipografia, guidelines). Os scripts de busca exigem Python. |
| `web-accessibility` | Guia de WCAG 2.1 (contraste, teclado, ARIA). |
| `web-design-guidelines` | Revisa código de UI contra as Web Interface Guidelines da Vercel. |

### Agents (`.claude/agents/`)
Todos são somente leitura, devolvem texto e usam poucas chamadas ao Figma. Rode um de cada vez.

| Agent | Para quê |
|---|---|
| `a11y-auditor` | Audita a acessibilidade de um frame e calcula os contrastes. |
| `fidelity-checker` | Compara o print original com o render do Figma, por região. |
| `figma-extractor` | Extrai tokens, notas de handoff e componentes de uma página do Figma. |

### Templates (`.claude/templates/`)
- `prototype-handoff.md`: resumo do protótipo (frames, componentes, desvios, suposições, pendências).
- `frontend-briefing.md`: briefing para o front-end (estrutura, especificação, comportamento, acessibilidade e critérios de aceite).

### Projects (`.claude/projects/`)
Uma pasta por projeto, com quatro arquivos:
- `README.md`: arquivo Figma, bibliotecas, páginas e referências.
- `instructions.md`: regras de construção (breakpoints, containers, tipografia, estados obrigatórios, foco, formato das Notes).
- `design-patterns.md`: tokens, componentes e regras de comportamento.
- `screens.md`: telas criadas.

Veja [`.claude/projects/README.md`](.claude/projects/README.md). A pasta [`_template/`](.claude/projects/_template/) serve de base para um projeto novo.

## Como usar
1. Abra a pasta no Claude Code (a configuração de `.claude/` é carregada automaticamente).
2. **Projeto novo:** copie `.claude/projects/_template/` para `.claude/projects/<slug>/` e preencha o `README.md` e o `instructions.md`. Peça ao agent `figma-extractor` para levantar os padrões do arquivo Figma.
3. Peça a tela, por exemplo: "prototipe a página X no Figma", com o link da tarefa do ClickUp ou a descrição no chat, e a URL do arquivo Figma de destino.
4. A skill `figma-prototype` lê o projeto, descobre o design system, monta os frames, valida a acessibilidade e devolve o briefing de front-end preenchido no chat.

## Como pedir

Diga sempre o **projeto** (slug) e dê a **URL do arquivo Figma**. Os exemplos abaixo podem ser copiados e adaptados.

### 1. Criar um projeto e mapear o Figma
O mapeamento lê o arquivo Figma e preenche `projects/<slug>/design-patterns.md` (tokens, componentes, notas de handoff, acessibilidade e pendências). Peça **uma página por vez**, porque o plano do Figma tem limite de chamadas.

```
Crie o projeto "cliente-x" a partir do template em .claude/projects/ e preencha o README
com este arquivo Figma: https://www.figma.com/design/<fileKey>/<nome>
```
```
Use o agent figma-extractor para mapear a página "Handoff - Home" (node-id 1:123) do projeto
cliente-x e grave o resultado em projects/cliente-x/design-patterns.md.
```
```
Mapeie as demais páginas do Figma do projeto cliente-x, uma de cada vez, e atualize
o design-patterns.md. Marque como pendente o que não conseguir ler.
```
```
Preencha o projects/cliente-x/instructions.md: breakpoints, containers, tipografia, cores base,
estados obrigatórios e foco. Pergunte o que não estiver no Figma.
```

### 2. Prototipar uma tela
```
Prototipe esta tarefa do ClickUp no Figma do projeto cliente-x: https://app.clickup.com/t/<id>
Arquivo de destino: https://www.figma.com/design/<fileKey>/<nome>
```
```
Prototipe no Figma do projeto cliente-x a tela de <descrição>, versões desktop e mobile.
Arquivo de destino: <url>
```
Ao finalizar, a skill devolve o resumo do protótipo e o **briefing de front-end preenchido** no chat, e registra a tela em `screens.md`.

### 3. Replicar um print
```
Replique este print no Figma do projeto cliente-x, exatamente igual (cores, medidas, tudo).
Use placeholder nas imagens. Arquivo de destino: <url>
```
Depois, para conferir a fidelidade: `Use o agent fidelity-checker para comparar o print <caminho> com o frame <node-id> do arquivo <fileKey>.`

### 4. Acessibilidade
```
Use o agent a11y-auditor no frame <node-id> do arquivo <fileKey> e me devolva as exceções
com a correção proposta.
```

### 5. Briefing de front-end e registros
```
Gere o briefing de front-end do frame <node-id> usando o template, e entregue no chat.
```
```
Registre a tela <nome> (node-id <id>) em projects/cliente-x/screens.md e atualize os padrões
com o que aprendemos.
```

### Dicas
- Cole o link do frame com `?node-id=`: o `fileKey` e o `node-id` saem da URL (`node-id=1-2` vira `1:2`).
- Se aparecer "tool call limit", o limite do plano do Figma estourou. A skill e os agents param e dizem o que ficou sem ler; retome depois.
- Rode **um agent do Figma por vez**; o limite de chamadas é compartilhado.
- Cada valor nos `design-patterns.md` vem marcado como **[C]** confirmado, **[I]** inferido ou **[N]** não confirmado. Peça para confirmar os **[N]** antes de depender deles.

## Requisitos
- [Claude Code](https://claude.com/claude-code).
- Conector do **Figma** com permissão de escrita no arquivo. O plano tem limite de chamadas: se estourar, a skill para e informa o que faltou.
- Conector do **ClickUp**, para pedidos que chegam por link de tarefa.
- Python é opcional (só os scripts do `ui-ux-pro-max` precisam dele). As rotinas de medição usam `node` e PowerShell.

## Origem das skills de terceiros
| Skill | Origem |
|---|---|
| `ui-ux-pro-max` | [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) |
| `web-design-guidelines` | [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) |
| `web-accessibility` | [tech-leads-club/agent-skills](https://github.com/tech-leads-club/agent-skills) (MIT) |

Confira a licença de cada repositório de origem antes de distribuir este projeto.
