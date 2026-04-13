# Spec — Producao Site Dra. Raquel Cosso

> Data: 2026-04-13
> Status: aprovado pra execucao
> Foco: qualidade de design, abordagem holistica (site + fotos integrados)

## Contexto

Primeiro cliente real do pipeline LP Medicos. Endocrinologista em BH, particular only.
Briefing completo recebido: copy (docx convertido), 7 fotos de treino, paleta de referencia (marsala/dourado/nude), 3 sites de referencia analisados.

**Decisao chave:** NAO usar template base. Gerar do zero com frontend-design skill + guardrails pra testar as novas ferramentas. Comparar resultado com nossos templates depois.

## Abordagem

### Filosofia

Site e fotos sao pensados juntos, nao sequencialmente. O layout define que fotos cada secao precisa (pose, enquadramento, tom). As fotos sao produzidas pra encaixar no layout, nao o contrario.

### Stack

- **Framework:** Astro 5 (static, NO SSR)
- **Estilos:** Tailwind CSS v4 via `@tailwindcss/vite` (NUNCA `@astrojs/tailwind`, NUNCA `tailwind.config.js`, NUNCA `@apply`)
- **Tokens:** `@theme` em `src/styles/global.css` — unica fonte de verdade pra cores, fontes, spacing
- **Fontes:** Self-hosted woff2 com preload (NUNCA Google Fonts CDN)
- **JS:** Minimal — Intersection Observer, header scroll, mobile menu. Sem frameworks JS.
- **Regras completas:** ver `CLAUDE.md` do repo

### Ferramentas de Qualidade

| Ferramenta | Papel |
|---|---|
| frontend-design skill | Direcao estetica bold, anti-generico |
| Web Design Guardrails | Regras concretas (cores, tipografia, sombras, animacoes) |
| Screenshot Comparison Loop | Iterar visualmente contra referencias (min. 2 rounds por secao) |
| Reference Matching | Clonar layout/spacing das refs antes de aplicar brand |
| Astria FaceID | Gerar fotos sem treino (teste rapido) |
| Astria Flux LoRA | Fine-tuning com 7 fotos (qualidade maxima) |

## Fases de Execucao

### Fase 1 — Direcao Estetica (sem codigo)

1. **Design thinking** (frontend-design skill):
   - Proposito: site de endocrinologista premium, conversao via WhatsApp
   - Tom estetico: editorial sofisticado + quente (marsala/nude/dourado)
   - Diferencial memoravel: padroes geometricos dourados como textura/detalhe
   - Publico: mulheres 30-55, BH, classe A/B, buscando saude hormonal

2. **Definir paleta final** no `@theme`:
   - Usar cores extraidas da ref (`#A2584B`, `#B68766`, `#EAD4C9`) como base
   - Quando Raquel mandar paleta definitiva, substituir
   - Testar no Realtime Colors antes de codar

3. **Escolher tipografia**:
   - Font pairing: serif display (headings) + sans clean (body)
   - NAO usar: Inter, Roboto, Arial, system fonts, Cormorant (ja usado nos templates)
   - Testar 2-3 pairings, escolher o mais distinto
   - Self-hosted woff2 com preload

4. **Mapear foto por secao** — definir briefing visual:

| Secao | Foto necessaria | Enquadramento | Tom |
|---|---|---|---|
| Hero | Portrait editorial, olhando camera | Cintura pra cima ou 3/4 | Confiante, acolhedora |
| Sobre | Lifestyle casual, ambiente natural | Meio corpo, sentada ou em pe | Pessoal, calorosa |
| Atendimento | No consultorio, interagindo | Ambiente de trabalho | Profissional, humana |
| Formacao | Com jaleco, hospital | Meio corpo | Credencial, competente |

### Fase 2 — Producao de Fotos

1. **Testar FaceID primeiro** (instantaneo, centavos):
   - Subir as 7 fotos como referencia
   - Gerar 4 fotos nos enquadramentos mapeados na Fase 1
   - Avaliar qualidade e semelhanca

2. **Se FaceID nao for suficiente → Fine-tuning LoRA**:
   - Treinar modelo Flux portrait com as 7 fotos ($1.50)
   - Gerar fotos com prompts especificos por secao
   - Usar `face_swap + inpaint_faces + super_resolution`

3. **Pos-processamento**:
   - Crop/resize pra dimensoes do layout
   - Tiled upscale V2 se necessario ($0.07/img)
   - Salvar em `assets/photos/ai-generated/`
   - Finais otimizadas em `assets/photos/production/`

### Fase 3 — Codigo (frontend-design + guardrails)

1. **Limpar scaffold antigo** — remover componentes placeholder e fotos que nao sao da Raquel em `src/assets/images/`

2. **Codar secao por secao**, seguindo guardrails:
   - Cada secao: codar → screenshot via Playwright → comparar com ref → corrigir → re-screenshot (min. 2 rounds)
   - Cores derivadas do `@theme`, nunca hex hardcoded
   - Animacoes: so `transform` + `opacity`, spring easing, `.reveal` classes
   - Sombras layered, color-tinted, low opacity
   - Todo clicavel com hover + focus-visible + active

3. **Ordem das secoes**:
   1. Layout.astro + global.css (@theme tokens)
   2. Header/Nav — minimalista, CTA pill marsala
   3. Hero — foto grande + H1 display + CTA
   4. Sobre — historia pessoal + foto lifestyle
   5. Especialidades — 10 areas em cards
   6. Atendimento — secao narrativa humanizada
   7. O que faz o endocrinologista — educativo
   8. Formacao — credenciais + badges
   9. FAQ — accordion (5 perguntas, copy pronta)
   10. CTA Final — WhatsApp + localizacao
   11. Footer

4. **Reference matching** — usar screenshots da Marilia (paleta) e Ana Eduarda (layout/fotos) como alvos visuais. Clonar spacing/proporcoes, depois aplicar brand da Raquel.

### Fase 4 — Validacao

1. **Pedro valida no localhost:4321** — golden path + mobile
2. **Checklist de entrega** (`_opensquad/core/templates/checklist-entrega.md`)
3. **Lighthouse** — Performance 90+, Accessibility 95+, SEO 100
4. Ajustes baseados no feedback

### Fase 5 — Deploy

1. Push GitHub (repo `laender-software/lp-00-raquel` ou similar)
2. Conectar Vercel
3. Dominio: a definir com Raquel
4. OG card + meta tags finais

## Dados Pendentes (nao bloqueiam Fases 1-3)

- WhatsApp da Raquel
- Instagram
- Endereco exato do consultorio
- Paleta definitiva (temos ref, serve pra comecar)
- Depoimentos (secao pode ser placeholder ou omitida)
- Logo (se tiver)

## Arquivos de Referencia

- Copy: `docs/copy-original.md` (docx convertido na integra)
- Ficha: `docs/ficha.md` (dados completos)
- Referencias: `docs/referencias.md` + `docs/referencias/*.png`
- Fotos: `assets/photos/originals/` (7 fotos)
- Paleta ref: `assets/brand/palette-ref-marsala-gold.jpeg`
- Guardrails: Second Brain → `_wiki/concepts/web-design-guardrails.md`
- Image stack: Second Brain → `_wiki/concepts/image-generation-stack.md`

## Cola pra Proxima Sessao

```
Leia o spec em docs/superpowers/specs/2026-04-13-producao-site-raquel-design.md
e os arquivos de referencia listados no final.
Comece pela Fase 1 — direcao estetica.
Repo: C:\Dev\lp-medicos\lp-00-raquel
```
