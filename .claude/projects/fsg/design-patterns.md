# Fire Services Group (FSG) — Padrões de design extraídos do Figma

Fonte: https://www.figma.com/design/FcT5hOoA4LaSE3qTekDgfp/Fire-Services-Group (fileKey `FcT5hOoA4LaSE3qTekDgfp`)
Extraído em: 2026-10-21 via MCP do Figma. Destino previsto: base para uma skill de prototipagem no Figma.

## 0. Como ler este documento

- **[C]** confirmado em valor lido do Figma. **[I]** inferido de hex/px literais, sem vínculo a token. **[N]** não confirmado/não lido.
- A extração é **PARCIAL**: o limite de chamadas do Figma MCP (seat Full, plano Professional) estourou. Ver seção 12 (pendências) antes de tratar qualquer coisa como completa.
- Os frames quase não usam variáveis Figma; os valores são literais. Só as anotações (Notes) usam estilos (Onyx, White, Red, Hard Shadow Large).
- Idioma: UI em **inglês**; anotações de handoff em **português**.
- Contexto: e-commerce B2B de alarme de incêndio (Hyva DS), marcas Honeywell/Gamewell-FCI/System Sensor/Vesda/Fiplex etc.

## 1. Estrutura do arquivo Figma

Páginas (nodeId): 🟢 Handoff - Home `1:123` · Handoff - PDP `462:3910` · Handoff - Brands `804:415` · Handoff - Linecard `934:2808` · Handoff - Tags + Mensagerias + Tabela de Estoque `1745:501` · 🟠 Sugestões e Melhorias `1448:524` · 🟠 Workspace `1:124` · 📱 Prototype `1:125` · 🔴 OFF `59:930` (descartado) · Thumbnail `0:1`.

Bibliotecas assinadas: **SITE JEM REBRANDING** (estilos "Hyva DS/..."), **Fire Services Group**, mais kits de comunidade (Material 3, iOS, macOS etc. — ignorar).

Convenções do handoff:
- Cada seção tem frames por breakpoint: **Desktop 1920, Desktop 1280, Tablet 768, Mobile 420, Mobile 360** (nem todas as páginas cobrem todos).
- Instâncias **"Note"** (cartão branco, borda 2px preta, sombra dura 4px 4px 0 #000, clipe rosa #F3B1AF) são as anotações de comportamento. Formato: título em caixa alta + "Comportamento: Desktop / Tablet / Mobile".
- Seções marcadas "Should not be considered for Development" (ex.: Initial Overview da PDP) e a página OFF são **legado — ignorar**.

## 2. Breakpoints e grid

| Breakpoint | Largura do conteúdo | Margem lateral |
|---|---|---|
| Desktop 1920 | 1632 | 144 |
| Desktop 1280 | 1152 | 64 |
| Tablet 768 | [N] | [N] |
| Mobile 420 | 380 | 20 |
| Mobile 360 | 320 | 20 |

- Conteúdo sempre centralizado dentro do container. Seções de largura total (ex.: Brands) mantêm o conteúdo interno com a mesma margem.
- Header: topbar 48px + barra → **140px** no desktop; **100px** no mobile (faixa 12 + barra 60 em 360 [C]).
- Grid de produtos: 4 cards com gap 16 em 1632 (home/vitrine) [C]; listagem de marca: 5 colunas desktop, 2 mobile [C parcial]; logos de marcas: 3 colunas, gap 24 [C].
- Frames nomeados "Mobile 768p" têm 768px (tablet) — nome enganoso.

## 3. Tokens

### 3.1 Cores
Estilos "Hyva DS" com valor **confirmado**: Neutral/White `#FFFFFF`, Neutral/Gray-dark `#313131`, Neutral/Gray-text `#B0B0B0`, Neutral/Gray-light `#F5F5F5`, Neutral/Gray-medium `#D7D7D7`, Semantic/Link `#0088CC`.

Demais cores são hex literais (uso observado):

| Hex | Uso |
|---|---|
| `#161616` | texto principal, topbar do header, títulos |
| `#5B5B5B` | texto secundário, SKU, breadcrumb, preço riscado |
| `#A4A4A4` | nome da marca no card (**falha contraste**) |
| `#B3B3B3` | eyebrow do hero (sobre fundo escuro) |
| `#1452D6` | ação primária: CTAs, aba ativa, links de ação [I] (Primary/Action provável) |
| `#003CBE` | link "Shipping policy"; possível hover do primário [I] |
| `#3566AF` | marca na PDP, títulos da barra de benefícios |
| `#186BE9` | borda da thumbnail ativa (desktop); no mobile usa `#3566AF` |
| `#5433EB` | CTA "Buy with [logo]" [I] (Secondary/Action provável); na PDP aparece `#403F3F` |
| `#0088CC` | Call for Lead Time, Backorder, Semantic/Link |
| `#1F8705` / bg `#E0FFD8` | In Stock / sucesso |
| `#E93030` / bg `#FFEFEF` | Out of Stock / erro |
| `#099428` / bg rgba(75,255,116,.12) / borda `#9CF4B0` | badge "Save $X" |
| `#777777` / bg rgba(242,242,242,.12) / borda rgba(141,141,141,.32) | badge Discontinued |
| `#DFDFDF` | borda padrão (cards, inputs, thumbs, quantidade) |
| `#F0F0F0` | borda de cards na Home; `#EDEDED` borda do header; `#D7D7D7` tabela; `#E6E8E9` divisor do header |
| `#F5F5F5` / `#F1F1F1` | linhas alternadas de tabela / fundo do input de e-mail |
| `#0A0A0A` | gradiente do hero banner |
| `#262626`, `#2E2E2E` | footer e faixa de assinatura |
| `#515151` | pill do contador do carrinho |
| `#050504`, `#232323`, `#2C2C2C` | blocos escuros do Brand Showcase (texto branco) |

### 3.2 Tipografia — família **Inter** em todo o handoff
- Estilos Hyva DS existentes (valores **[N]**, só nomes): Heading Desktop H1–H4, Heading Mobile H1–H4, Text Large/Normal (Regular, Medium, SemiBold, Bold), Text XS (Medium/SemiBold/Bold), Button/Primary, Button/Small, Button/Underlined, Price/Normal, efeito **Focus in**.
- Valores **confirmados em 2026-10-21** (importando os estilos por key com `figma.importStyleByKeyAsync` e lendo `fontSize/lineHeight`; todos Inter, tracking 0):
  - Heading Desktop H1 = Semi Bold 48/56 · H2 = Semi Bold 36/44 · Heading Mobile H1 = Semi Bold 36/44 · H3 = Semi Bold 24/32.
  - Text/Large/Regular 18/28 · Text/Normal/Regular 16/24 · Text/Normal/SemiBold 16/24 · Text/Small/Regular|Medium|SemiBold 14/20 · Button/Primary = Semi Bold 16/24.
  - Keys (biblioteca SITE JEM REBRANDING, usar em `importStyleByKeyAsync`):
    - H1 desktop `1087c4a0467f3f9f6f20b7bcb422ad254cfc89aa` · H2 desktop `6fdcd7e813012058d0f8f136b0a9ccba89630e85`
    - H1 mobile `eec6fcfe021ab0b85cbd1f3ce6484ef0c1385c83` · H3 mobile `85c43aaef428d3aec21157bbcd9f245486872a32`
    - Large/Regular `6f94864c51fe4350b75edda141baf1c609943567` · Large/SemiBold `9d85df5c92dd956e31f5aea7ec969d2e8ffde50d`
    - Normal/Regular `ba2fce99f434a93f3539ddc8aca9740a64ef9b90` · Normal/SemiBold `aec8b855118fcfc6cd32b26d83d9bdc0bfa3431d`
    - Small/Regular `93e30e742fb3ade76a8bb2debee98e4db425ec99` · Small/Medium `fc9f8e3c9d9896677a24fc6c9ae0f4776066b0af`
    - Button/Primary `244fe6916632a658255a6812dd6e55d6995da385`
  - Header e footer reutilizáveis (clonar, não mover): Linecard desktop header `1066:7514` / footer `1066:7643`; mobile header `1012:2262` / footer `1012:2416`.
  - Dados reais da FSG (vistos no footer): e-mail `info@fireservicesgroup.com`, tel. `(480) 870-7805`, horário "Mon - Fri: 8AM - 4PM / Sat - Sun: Closed", endereço "121410 N 15th Lane, Suite 114, Phoenix, AZ 85027".
  - Aplicar com `await textNode.setTextStyleIdAsync(style.id)` depois de carregar as fontes (`Semi Bold`, não `SemiBold`).
- Escala de tamanhos observada: 11, 12, 14, 16, 18, 20, 24, 30, 32, 48.
- Pesos usados: Regular 400, Medium 500, SemiBold 600 (Bold/ExtraBold pontuais).
- Line-height recorrente: 1.32 (UI geral), 1.4–1.5 (parágrafos), 1.6 (descrições longas).
- Hero: eyebrow Medium 18; título SemiBold 48 (tracking -0.468 aparece nos itens de menu/dropdown; lh 1.32); corpo Regular 16 / 1.5.
- Card: marca Medium 14 · nome Regular 16 (mobile 14) · preço SemiBold 20 (mobile 16) · riscado Regular 16 (mobile 12).
- PDP: título Medium 32 (mobile SemiBold 24) · marca Medium 18 (mobile SemiBold 14) · preço SemiBold 30 (mobile 24) · descrição 16/1.5 (mobile 14/1.4) · CTA Medium 16 (mobile 14).
- Itens de dropdown: Medium 16.8, tracking -0.468, lh 33.6 (herdado do tema Hyva, não arredondar).

### 3.3 Espaçamento
Escala: **4, 8, 12, 16, 20, 24, 32, 40, 48, 64** (mais frequentes na Home: gap 8 ≫ 16 > 24 > 32 > 12; padding 20, 10, 24, 12, 32).
- Card: padding 16, gap 16 (interno 8/12). CTA do card: altura 44, padding 10, gap 8.
- Hero: coluna de texto 480px, gap 24; botões gap 24. Hero 1632×410 (desktop), radius inferior 4.
- PDP desktop: colunas gap 48; galeria gap 32; thumbs 116×116 gap 20; botões gap 16. Mobile 420: padding lateral 20, gap vertical 32, thumbs 74×74 gap 12.
- Alvo mínimo: **44px** (botões, itens de menu desktop). Exceções que ficam abaixo: ver seção 9.

### 3.4 Radius, bordas, sombras
- Radius: **4** (padrão: botões, cards, tags, inputs) · 6 (itens de dropdown, CTA Brands) · 8 (tabela, painel de logos, depoimentos, View Gallery) · 12 (dropdown do header) · 20 (pílulas/badges) · 1000 (setas do carrossel).
- Cards com CTA colado: raio 4 só no topo do corpo e só embaixo do CTA.
- Borda padrão 1px `#DFDFDF`. Aba ativa: linha 2px `#1452D6`.
- Sombras: única de UI = dropdown de marcas `0 8px 20px rgba(0,0,0,.08)`. Cards **não** têm sombra. (A sombra dura 4px 4px 0 #000 é só das Notes.)

## 4. Componentes

### 4.1 Botões
- **Primário** (`#1452D6`, texto branco, raio 4, 44px). Variantes: "View Details" (card, sem ícone), "Add to cart" (ícone carrinho 20, gap 8), "Subscribe" (footer, 14 SemiBold), PDP "Add to cart" (Medium 16, padding 32/12, flex 1; largura total no mobile).
- **Secundário "Buy with [logo]"**: 44px, padding 32/12, raio 4, logo 41×16 (38×15 mobile).
- **Hero "Shop Now"**: fundo branco, texto `#161616` SemiBold 16, 44px. **Hero "Check the Video"**: fundo rgba(255,255,255,.12), borda 1px branca, ícone 20 — abre modal de vídeo.
- **Out of Stock**: CTA vira "Sold out" com opacity 50% (e "Buy in" com opacity 0). Hover/active/disabled/focus **[N]** (não desenhados).
- Biblioteca tem: Button Primary/Secondary/Tertiary/Quarternary (iconless e with icons), Small Button, Mobile Buttons, Button States, Cart Button, User Button, Text Button, Tag Button, Dropdown Button, Radio Button. Valores **[N]**.

### 4.2 Tags e status de estoque
- **Tag principal** (sobre a imagem do card, posição 16/16; mobile top 13): altura 24 (mobile 20), padding 8/4, raio 4, SemiBold 14/20 (mobile 10/20).
  - In Stock · Call for Lead Time · Out of Stock (cores na seção 3.1). Exclusivas entre si.
- **Sub-status** (chip, pode coexistir): padding 6/2, borda 1px, raio 4, Medium 12 — **Discontinued**, **Backorder Available** (bg rgba(246,249,255,.12), borda `#CEDEFF`, texto `#0088CC`; na PDP aparece `#1452D6` → inconsistência).
- **PDP**: linha `SKU: X | ● In stock | [Discontinued]` (divisores 1px, bolinha 6px, gap 12–16).
- **Badge de economia**: "Save $93.26", altura 28, padding 6/8, Medium 14.
- Capitalização inconsistente: "In Stock" (tag) vs "In stock" (PDP).

### 4.3 Product Card
- Desktop 313,6×457,6; mobile 152×325; vitrine 258,67 de largura.
- Estrutura: imagem 1:1 (object-cover) → marca → nome → (preço atual + riscado, se logado) → CTA 44px colado na base.
- Variante com hover (Variant2): borda `#D4D4D4` (a Note diz apenas "muda a cor do stroke").
- Altura dos cards de uma linha acompanha o maior título.
- Card sem foto: placeholder genérico (sugestão, ver seção 10).

### 4.4 Header
- Topbar 48px `#161616`: "Free Shipping on Orders Over $300" + "Shop Now" (sublinhado), 14px.
- Barra branca, borda inferior `#EDEDED`, conteúdo max 1760, padding 64; logo 50×40,5; menu Home, Brands (dropdown: Fiplex, Fire Sentry, Gamewell-FCI, HyperSpike, System Sensor, VESDA, PCTEL), Our Goal, About Us, Contact Us; busca, conta ("Hi, <nome>"), carrinho com contador (pill 24px `#515151`, 11 SemiBold).
- Dropdown: branco, raio 12, padding 12, gap 6, largura 200; itens padding 20/10, raio 6.
- Mobile: hamburger 32px, ícones 32px, logo 44×36; megamenu com variantes logado / não logado / expandido.

### 4.5 Hero Banner
- Imagem de fundo + gradiente horizontal `#0A0A0A` → transparente; texto à esquerda (480px); setas circulares 40px (rgba(0,0,0,.2), chevron 32); bullets 20px.
- Banners de marca: texto em **HTML real** (chip, título ExtraBold de 2 linhas, parágrafo) sobre fundo/produto em imagem; desktop alinhado à esquerda, mobile centralizado.

### 4.6 PDP
- Galeria: thumbs com borda 1px (ativa azul); thumb 4 com overlay rgba(232,232,232,.4) + ícone 32; thumb 5 cortada com degradê (sugere rolagem); imagem principal quadrada com borda `#DFDFDF`; "View Gallery" (ícone 24, padding 8, raio 8; no mobile ícone 36×36 ou ícone+texto 12px).
- Quantidade: altura 44, "−" 40×40, campo 61×40 com bordas só em cima/baixo, "+" 40×40, número Regular 18.
- Preço: 30px + riscado 16 lado a lado (desktop); mobile riscado acima. Parcelamento: "4 interest-free installments, or from $42.09/mo with [logo]". Acima: "Shipping calculated at checkout." + link "Shipping policy".
- Barra de benefícios (3 colunas): "Free U.S Shopping" (provável typo de Shipping), "30-Day Returns", "1-Year Warranty"; título 14 SemiBold `#3566AF`.
- Abas: Product Details / Specifications / Compatibility / Documents (40px, Medium 16, ativa `#1452D6`); mobile = accordion.
- Brand Showcase: blocos alternados imagem + painel escuro, título SemiBold 32; cards com ícone 32.
- Breadcrumb: `Home • Category • Produto`, separador bolinha 5px, atual Medium `#161616`, mobile 12px com ellipsis.

### 4.7 Tabela de estoque ("Available to Ship")
Cabeçalho branco, borda `#D7D7D7`, padding 16/12, raio 8, título SemiBold 14 `#313131`; linhas alternam branco / `#F5F5F5`; quantidade "200+" Medium 14 `#1F8705` à direita. Estrutura completa da seção **[N]**.

### 4.8 Footer
Fundo `#262626`, assinatura `#2E2E2E`, texto branco; newsletter (input `#F1F1F1` 44px + "Subscribe"); mobile com seções colapsáveis (Navigation, Customer Service, Opening Hours) e ícones de pagamento 46,3×29,2.

### 4.9 Outros
- Input de busca: pequeno 36px / padrão 44px, borda `#DFDFDF`, raio 4, botão anexado opcional.
- Logo de marca (Linecard/Brands): cartão branco, borda 1px `#DFDFDF`, raio 4, aspect 160/80, padding 20/12.
- Mensageria (carrinho/minicart/toasts): conteúdo **[N]**; existe mensagem de backorder ("Some items in your order are on backorder...") sem estilo extraído.

## 5. Regras de comportamento (anotações transcritas das Notes)

**Home**
- *More than 1 banner*: desktop — paginador, setas e bullets; troca automática **a cada 6 s**. Mobile — paginador + swipe, sem setas; 6 s mantidos.
- *Video Modal*: abre em "Check the video"; vídeo inicia no Play; hospedado externamente (não usar player nativo do YouTube); fecha no "X" ou clicando fora. Mobile idem.
- *CTA*: desktop — nos CTAs do banner o fundo escurece (texto da nota truncado). Mobile — mesmo padrão, sem hover.
- *Benefits*: desktop centralizado, espaçamento adapta (maior em 1920, menor em 1280); tablet — duas linhas; mobile — **carousel**.
- *Brands*: seção 100% da viewport; conteúdo centralizado com mesma margem (144 em 1920); imagens ocupam 100% da largura disponível mantendo aspect ratio; mobile — duas linhas, padding lateral do mobile.
- *Card behavior*, *Price*, *Image*, *Bullets*, *Hover card*: ver abaixo (idênticas na PDP/Product Showcase).

**Listagem/cards e Product Showcase**
- Card behavior: altura de todos os cards da linha acompanha o maior título (desktop e mobile).
- Price: **usuário deslogado não vê preço**; clique em "Details"/imagem → PDP. Logado com preço: botão "Buy Now" adiciona ao carrinho; clique fora do botão → PDP.
- Image: hover desktop aplica **zoom** (ref. JEM); mobile sem hover.
- Bullets do carrossel: avançam de **3 em 3** (desktop) e **2 em 2** (mobile); bullets acompanham o grupo.
- Hover card: muda a cor do stroke; em "View Details" qualquer parte do card leva à PDP. Mobile sem hover, mesmo comportamento.

**PDP**
- Conteúdo centralizado no container. Galeria navegável com imagem selecionada destacada; **menos imagens que thumbnails → reduzir proporcionalmente**. Clique na imagem principal ou "View Gallery" abre modal. Quantidade por "+"/"−"; "Add to Cart" adiciona a quantidade escolhida.
- Product Details: abas com a ativa em Active; **abas sem conteúdo ficam ocultas**; mobile = accordion (também oculta seções vazias).
- Brand Showcase: conteúdo institucional **reutilizado por linha de produto** (ex.: Elevate); o texto deve ser feito em código, não só imagem.

**Brands / Linecard**
- Hover na marca + clique leva direto à **PLP da marca**. CTA "Shop All Brands" → PLP "All Brands". Mobile mesmo comportamento.
- Linecard: hero (H2 + subtítulo azul + descrição + CTA) + grid 3 colunas de logos (9 marcas). 1280: 2 colunas no hero (gap 40); 1920: 796+796; mobile: coluna única.

**Regras de estoque (Tags)**
- Estoque > 0, **sem backorder**: compra até o estoque; após o pedido, a tag vira **Out of Stock**.
- Estoque > 0, **com backorder**: pode comprar acima do estoque; após o pedido, a tag principal vira **Call for Lead Time** (versão vigente: nó 1928:3516; as demais notas são anteriores/duplicadas).
- Estoque 0 + Call for Lead Time (com ou sem Discontinued): quantidade livre; a tag permanece.
- **Out of Stock** puro (com ou sem Discontinued): não compra, não entra em pedido.
- O critério "backorder ligado" para distinguir Call for Lead Time de Out of Stock é **[I]**. Bug anotado: "ao clicar no + sem backorder" (comportamento esperado não descrito).

## 6. Padrões de conteúdo e UX
- Idioma UI: inglês, Title Case em status e CTAs.
- CTAs: "Add to cart", "Buy with [logo]", "Buy Now", "View Details", "View Gallery", "Shop Now", "Shop All Brands", "Subscribe", "Check the video".
- Preço US: `$99,999.99` (símbolo antes, vírgula de milhar, 2 casas); parcela "from $42.09/mo"; riscado à esquerda no card e à direita na PDP.
- Frete grátis acima de $300, 30 dias de devolução, 1 ano de garantia.
- Deslogado: sem preço, CTA "View Details". Logado: preço + "Buy Now"/"Add to cart".
- Produto descontinuado (sugestão): aviso "A Newer Version is Available" + caixa "Replaced by:" + botão "View New Model".
- Provas sociais (sugestão): "Customer Reviews" — 4 cartões, "Verified Customer".

## 7. Acessibilidade — o que o Figma mostra e o que falta

Contrastes calculados (WCAG 2.x):

| Par | Razão | Resultado |
|---|---|---|
| `#161616` / `#FFF` | 18,1 | AAA |
| `#5B5B5B` / `#FFF` | 6,79 | AA |
| `#FFF` / `#1452D6` (CTA) | 6,55 | AA |
| `#1452D6` / `#FFF` | 6,55 | AA |
| `#3566AF` / `#FFF` | 5,72 | AA |
| `#FFF` / `#403F3F` | 10,5 | AAA |
| `#1F8705` / `#FFF` | 4,64 | AA (raspando) |
| `#1F8705` / `#E0FFD8` (tag In Stock) | 4,30 | **falha AA** |
| `#E93030` / `#FFF` | 4,26 | **falha AA** |
| `#E93030` / `#FFEFEF` (tag Out of Stock) | 3,82 | **falha AA** |
| `#0088CC` / `#EBF2FF` (tag Lead Time) | 3,46 | **falha AA** |
| `#0088CC` / `#FFF` (Backorder) | 3,89 | **falha AA** |
| `#099428` / ~`#E9FFEE` (Save) | ~3,8 | **falha AA** |
| `#777` / `#FFF` (Discontinued 12px) | 4,48 | falha marginal |
| `#A4A4A4` / `#FFF` (marca no card) | 2,49 | **falha AA** |
| borda `#DFDFDF` / `#FFF` | 1,33 | abaixo de 3:1 (WCAG 1.4.11) |

Lacunas de acessibilidade presentes no desenho (a skill deve corrigir ao prototipar):
- **Nenhum estado de foco** desenhado. Sugestão (não vem do Figma): `:focus-visible` com anel 2px `#1452D6`, offset 2px; existe o estilo "Hyva DS/Focus in" para inputs ([N] valor).
- Imagens sem alt definido no código gerado (`alt=""`): produto, thumbs e logos de marca precisam de alt/aria-label (logo-link leva o nome da marca).
- Alvos abaixo de 44px: stepper 40×40; header mobile 32px; View Gallery mobile 36×36 (ou ~28 de altura com texto); logos 360 estimados ~69px (cálculo, não medido).
- Quantidade sem label visível; sem desenho de erro, mensagem de ajuda, loading ou estado vazio.
- Status usa **cor + texto** (bom para daltonismo). Thumb ativa é só cor de borda 1px (reforçar).
- Estrelas de review e avatares decorativos (alt vazio), sem texto da nota.
- Breadcrumb aparece depois do conteúdo no DOM do frame Tags — manter ordem de leitura: anúncio, header, breadcrumb, galeria, marca, título, descrição, SKU/estoque, frete/parcelamento, quantidade/preço, CTAs, benefícios, abas, showcases.
- Reduced motion: carrossel com troca automática de 6 s deve ter pausa e respeitar `prefers-reduced-motion` (recomendação, não está no Figma).

## 8. Responsividade — resumo por componente
- Hero: 1632×410 → mobile com imagem própria (Mobile Background Image 728×410); pagina por swipe no mobile.
- Benefits: 1 linha (desktop) → 2 linhas (768) → carousel (mobile).
- Product Showcase/cards: 3 por vez (desktop) → 2 por vez (mobile).
- PDP: duas colunas (gap 48) → coluna única; CTAs empilhados (gap 16) e largura total; abas → accordion.
- Brands: logos em 2 linhas no mobile.
- Header: megamenu mobile; footer com seções colapsáveis.

## 9. Inconsistências detectadas no Figma
1. Hex literais em vez de variáveis; "Primary/Action", "Semantic/Error/Success" etc. existem como estilos mas sem valor confirmado.
2. Duas famílias de fonte: Inter (padrão) e **IBM Plex Sans** (card "Replaced Products" e Contact Us, ambos em Sugestões); dois azuis de ação `#1452D6` vs `#0060FF`.
3. Cor da thumb ativa difere entre desktop e mobile; gap da linha SKU 16 vs 12; "Backorder Available" azul vs ciano.
4. CTA do Linecard tem largura fixa por frame (242/317/hug) com o mesmo texto; subtítulo nowrap em 1920 e quebra em 1280; grid de logos 3×3 (1280) vs 3×2+3×1 (1920).
5. Tipografia muda de peso entre breakpoints (título/marca da PDP).
6. Out of Stock: CTA ativo em um frame e 50% em outro; nota diz que não entra em pedido.
7. Typos: "Free U.S Shopping", "FCl/FCI", "entega", "testmonial", "escure".
8. Notas duplicadas/obsoletas nas Tags; seção OFF coexiste no arquivo.
9. Mock: e-mail do time não bate com o nome; SKU de "Replaced by" aponta para o item antigo.

## 10. Sugestões e Melhorias (NÃO são padrão aprovado — são benchmarks/propostas)
Página de benchmarks de concorrentes (sem notas de motivo; "porquês" aqui são inferência). Propostas desenhadas: Categoria v1/v2, Customer Reviews (1454:4484), FAQ, Replaced Products, Contact Us (desktop 1920 e mobile 360), card de produto sem foto. Tratar como referência, não como regra.
- Customer Reviews: seção 1152 wide, título SemiBold 24; 4 cartões gap 32, borda 1px `#F0F0F0`, raio 8, padding 32/24; avatar de iniciais 48×48; texto em aspas curvas.
- Replaced Products: container borda `#EAEAEA`, imagem 140×140, tag "A Newer Version is Available" (`#EBF5FF`/`#006DE4`), caixa "Replaced by:" (`#F4F5F7`), botão outline vermelho `#D70202` "View New Model".
- Contact Us: IBM Plex Sans, azul `#0060FF`, contact cards (e-mail/telefone/horário), formulário + mapa lado a lado, equipe 3×2, "Common inquiries" 4 colunas; escala fora da grade 4/8 (fontes 17/21/23/25, gaps 7/17/27/34/38/62). Sem estados de foco/erro.

## 11. Orientações para a skill de prototipagem (derivadas)
1. Sempre usar **Inter**, grade 4/8, container por breakpoint (seção 2), alvo mínimo 44px, borda 1px `#DFDFDF`, raio 4.
2. Primário = `#1452D6`; texto `#161616`/`#5B5B5B`; evitar `#A4A4A4` para texto informativo.
3. Ao prototipar status de estoque, **não** repetir os pares de cor que falham AA (seção 7): escurecer texto ou bg.
4. Sempre prototipar variantes **logado vs deslogado** (preço some deslogado) e os 5 breakpoints (ou 1920, 1280, 768, 420, 360).
5. Incluir estados que o Figma não cobre: hover, focus-visible, disabled, loading, erro, vazio.
6. Adicionar anotações no mesmo formato das Notes (título caixa alta + Comportamento Desktop/Tablet/Mobile) quando o protótipo tiver comportamento.
7. Texto de banners e showcases deve ser HTML/texto real, não imagem.
8. Reusar a biblioteca "SITE JEM REBRANDING" (estilos Hyva DS) via `search_design_system` antes de criar componentes; verificar valores dos estilos [N] antes de depender deles.

## 12. Pendências (para completar quando o limite do Figma MCP renovar)
- **Home**: 18 anotações não lidas — nodeIds `339:10451, 340:10945, 359:1569, 359:1590, 347:543, 340:10955, 409:802, 573:4477, 573:4478, 573:4479, 573:4480, 573:4481, 573:4482, 573:5327, 379:5118, 388:5670, 389:6213, 396:8628` (header, dropdown, busca, megamenu etc.).
- **PDP**: não lidos Specifications `660:1065`, Compatibility `601:14210`, Documents `601:14336`, accordion mobile `708:4668`, hovers das abas `708:4513/708:4528`, Product Showcase desktop `615:1388`, PDP deslogado `676:2531`, frames 1280/768/360 e modal View Gallery (`462:4294, 587:8260, 676:2060, 1515:930`).
- **Tags/Mensageria/Estoque**: Mensageria (carrinho, minicart, toasts), Tabela de Estoque completa, "Call for Lead Time" nos frames mobile — `1940:4876, 1941:5609, 1754:4275, 1953:1075, 1943:6232`.
- **Linecard**: header, footer, breadcrumb, grids mobile 360/420, visual do hover, fundo do painel.
- **Brands**: só a seção Gamewell foi inspecionada (Honeywell: System Sensor, Vesda, Fiplex, Fire Sentry parciais); sem notas "Comportamento" nessa página (só "Padrão para todos os banners"); não há arquivo detalhado salvo, só o resumo.
- **Design system**: valores de Heading, Button, Price, Primary, Secondary, Semantic (Error/Success), Focus in; componentes (Modal, Toast, Pagination, Tabs, Checkbox, Radio, Select) não confirmados. Para obter: `use_figma` (Plugin API) lendo estilos importados, ou `get_design_context` em frames que apliquem o vínculo.
- **Workspace** `1:124`, **Prototype** `1:125`: não explorados.
- Não foram baixados assets (ícones, logos, imagens): URLs do MCP são temporárias (7 dias).
