# Skills Claude: Figma, UI/UX e acessibilidade

Configuração do Claude Code para prototipar telas no Figma com padrões de design, acessibilidade (WCAG 2.1 AA) e handoff para front-end. O primeiro projeto é a **FSG (Fire Services Group)**.

## O que o projeto faz
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
└── projects/      conhecimento por projeto (Figma, padrões, telas, referências)
```

### Skills (`.claude/skills/`)
| Skill | Para quê |
|---|---|
| `fsg-figma-prototype` | Monta protótipos da FSG no Figma, com acessibilidade e briefing de front-end ao final. Também faz réplicas fiéis de um print. |
| `ui-ux-pro-max` | Biblioteca de regras de UI/UX (estilos, tipografia, guidelines). Os scripts de busca exigem Python. |
| `web-accessibility` | Guia de WCAG 2.1 (contraste, teclado, ARIA). |
| `web-design-guidelines` | Revisa código de UI contra as Web Interface Guidelines da Vercel. |

### Agents (`.claude/agents/`)
Todos são somente leitura, devolvem texto e usam poucas chamadas ao Figma. Rode um de cada vez.

| Agent | Para quê |
|---|---|
| `fsg-a11y-auditor` | Audita a acessibilidade de um frame e calcula os contrastes. |
| `fidelity-checker` | Compara o print original com o render do Figma, por região. |
| `figma-extractor` | Extrai tokens, notas de handoff e componentes de uma página do Figma. |

### Templates (`.claude/templates/`)
- `prototype-handoff.md`: resumo do protótipo (frames, componentes, desvios, suposições, pendências).
- `frontend-briefing.md`: briefing para o front-end (estrutura, especificação, comportamento, acessibilidade e critérios de aceite).

### Projects (`.claude/projects/`)
Uma pasta por projeto. Cada uma tem `README.md` (arquivo Figma, bibliotecas e páginas), `design-patterns.md` (tokens, componentes e regras) e `screens.md` (telas criadas).
- [`fsg/`](.claude/projects/fsg/README.md): Fire Services Group.
- [`_template/`](.claude/projects/_template/): copie para começar um projeto novo.

## Como usar
1. Abra a pasta no Claude Code (a configuração de `.claude/` é carregada automaticamente).
2. Peça a tela, por exemplo: "prototipe a página X no Figma" com o link da tarefa do ClickUp, ou descreva a tela no chat. Informe a URL do arquivo Figma de destino.
3. A skill `fsg-figma-prototype` descobre o design system, monta os frames, valida a acessibilidade e devolve o briefing de front-end preenchido no chat.
4. Para um projeto novo, copie `.claude/projects/_template/` para `.claude/projects/<slug>/` e preencha o `README.md`.

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
