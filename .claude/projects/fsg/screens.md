# FSG — Telas criadas e analisadas

URL base: `https://www.figma.com/design/FcT5hOoA4LaSE3qTekDgfp/Fire-Services-Group?node-id=<id com hífen>` (troque `:` por `-`).

## Contact Us (criada em 2026-10-21)
- **Página:** `2049:15` "🟢 Contact Us".
- **Frames:** Desktop 1920 `2049:16` · Mobile 360 `2049:524` · Estados do campo `2052:8` · Notas `2052:181`.
- **Seção Meet Our Team** (entre o formulário e "Why Buy From Us"): desktop `2060:8`, mobile `2060:218`. As fotos foram recortadas de um print e enviadas com `upload_assets`; trocar pelas originais em alta resolução.
- **Origem:** estrutura da referência da House Supplier, com header e footer da FSG clonados do Linecard (`1066:7514`, `1066:7643`, `1012:2262`, `1012:2416`).
- **Estilos Hyva DS usados:** H1/H2 desktop, H1/H3 mobile, Text Large/Normal/Small, Button/Primary.
- **Dados reais usados:** e-mail `info@fireservicesgroup.com`, telefone `(480) 870-7805`, horário "Mon–Fri 8AM–4PM", endereço de Phoenix, AZ (do footer).
- **Desvios de acessibilidade corrigidos:** borda de campo `#8C8C8C` (3,4:1, no lugar de `#DFDFDF`) e erro `#C41E1E` (5,9:1, no lugar de `#E93030`).
- **A confirmar:** campos obrigatórios (nome, e-mail e mensagem foram uma suposição), textos adaptados da referência, versões 1280/768/420 (não feitas).
- **Pendência:** os nomes e e-mails da equipe seguem um print (ex.: "Ranaael", `andreza.borba@` para Andreza Alves).

## Heating Season — Featured by Category (criada em 2026-10-21)
- **Página:** `2067:4` "🟠 Heating Season (réplica do print)".
- **Frames:** réplica 1536×1024 `2067:5` · Estados e acessibilidade `2068:4` · Notas `2068:74`.
- **Origem:** réplica fiel de um print, com as cores medidas por pixel (JPEG, ±2 a 3 níveis). Visual vermelho/navy do print, não os tokens da FSG. Imagens são placeholders.
- **Calibragem:** letter-spacing ajustado por elemento para igualar as larguras do original (textos a 1 a 3 px). Quebras de linha copiadas do print.
- **Acessibilidade:** textos passam em AA (menor razão 4,18:1, em texto grande). Exceção: borda das abas sem seleção `#48505F` (2,09:1); proposta `#8A93A3` (5,48:1), não aplicada. O link "View All" precisa de área clicável ≥ 24px.
- **Briefing de front-end:** entregue no chat em 2026-10-21 (template em `templates/frontend-briefing.md`).
- **A confirmar:** as 3 variações do painel esquerdo (3 abas com promo, 2 abas com promo, 3 abas sem promo) foram copiadas como estão.
