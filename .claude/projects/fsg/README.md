# FSG — Fire Services Group

E-commerce B2B de alarme de incêndio (Hyva DS). Marcas: Honeywell, Gamewell-FCI, System Sensor, Vesda, Fiplex etc.

## Figma
- **Arquivo:** [Fire-Services-Group](https://www.figma.com/design/FcT5hOoA4LaSE3qTekDgfp/Fire-Services-Group) · `fileKey` `FcT5hOoA4LaSE3qTekDgfp`
- **Bibliotecas** (use em `includeLibraryKeys`):
  - SITE JEM REBRANDING (estilos Hyva DS): `lk-121b2df97c66188567d384e07245b32acb2a52b663dc22d8b90fca3cbe9306fd7b1310c3668e693abc1b6809acab7bddfc966078b745b9fabc9c9da2e9ec81ea`
  - Fire Services Group: `lk-3fb92c28ee03fb17fdcae9bdd364f3b3f07a67e2b6ee3b2fa48e3c294dd701bd7f62b61ece7a11ee8ac7498db119f055834508297fec9cd9b7c0c84aa3728840`
  - Ignorar as de iOS, macOS, watchOS, visionOS e Material 3.
- **Limite de chamadas do Figma MCP:** o plano Professional já estourou uma vez. Agrupe chamadas e rode agents um de cada vez.

## Páginas do arquivo
| Página | nodeId | Observação |
|---|---|---|
| 🟢 Handoff - Home | `1:123` | 18 anotações ainda não lidas |
| 🟢 Handoff - PDP | `462:3910` | parcialmente lida |
| 🟢 Handoff - Brands | `804:415` | só a seção Gamewell |
| 🟢 Handoff - Linecard | `934:2808` | header e footer reutilizáveis |
| 🟢 Handoff - Tags + Mensagerias + Tabela de Estoque | `1745:501` | regras de estoque lidas; Mensageria e Tabela de Estoque não |
| 🟠 Sugestões e Melhorias | `1448:524` | benchmarks, não são padrão aprovado |
| 🟢 Contact Us | `2049:15` | criada por nós (ver `screens.md`) |
| 🟠 Heating Season (réplica do print) | `2067:4` | criada por nós (ver `screens.md`) |
| 🟠 Workspace / 📱 Prototype | `1:124` / `1:125` | não exploradas |
| 🔴 OFF | `59:930` | legado, ignorar |

## Arquivos do projeto
- [design-patterns.md](design-patterns.md): tokens, componentes, comportamento, acessibilidade e pendências.
- [screens.md](screens.md): telas criadas e analisadas.

## Referências externas
| Referência | Uso | Data |
|---|---|---|
| [thehousesupplier.com/pages/contact-us](https://www.thehousesupplier.com/pages/contact-us) | Estrutura da página Contact Us (canais, perguntas, formulário de cotação, benefícios) | 2026-10-21 |
| Print de banners "Heating season" (código HEAT7, da mesma loja acima) | Réplica fiel no Figma | 2026-10-21 |

## Contas e ferramentas
- ClickUp conectado (tarefas chegam por link). Skill: `fsg-figma-prototype`. Agents: `fsg-a11y-auditor`, `fidelity-checker`, `figma-extractor`.
- Python não está instalado nesta máquina: use `node` e PowerShell.
