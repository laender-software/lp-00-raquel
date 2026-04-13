# CLAUDE.md — Site Dra. Raquel Cosso (Endocrinologista)

Landing page profissional para **Dra. Raquel Cosso** — Endocrinologista e Metabologista. Conversion-focused: cada seção direciona para agendamento (WhatsApp ou sistema de agendamento). Static only, NO SSR.

**Goals:** Lighthouse 95+, mobile-first, accessibility AA, tom profissional, acolhedor e confiável.

## O Projeto

Site institucional para endocrinologista. Público-alvo: pacientes que buscam consulta com especialista em hormônios, tireoide, diabetes, obesidade, menopausa, etc. Atendimento particular only (reembolso possível).

**Dados reais:**
- Nome: Dra. Raquel Cosso
- CRM: CRM-MG 82239 | RQE 68237
- Especialidades: Endocrinologia e Metabologia — obesidade, diabetes, tireoide, SOP, climatério/menopausa, osteoporose, colesterol/risco cardiovascular, doenças hipófise/adrenais
- Formação: Medicina (FCMMG), Clínica Médica + Endocrinologia (Santa Casa BH), Hospital Madre Teresa (equipe + preceptora)
- Localização: Av. do Contorno, 8000 — Sala 1012, Santo Agostinho, BH/MG
- WhatsApp: (31) 99997-2136
- Instagram: a confirmar
- Site de agendamento: a confirmar
- **Ficha completa:** `docs/ficha.md`

---

## Stack

- **Framework:** Astro 5 (static)
- **Estilos:** Tailwind CSS v4 via `@tailwindcss/vite` (NOT `@astrojs/tailwind`)
- **Fontes:** Self-hosted woff2 (NUNCA Google Fonts CDN) — serif elegante para headings, sans clean para corpo
- **Deploy:** Vercel (recomendado)
- **Dev server:** `npm run dev` → localhost:4321

### Estrutura de arquivos

```
src/
├── layouts/
│   └── Layout.astro     ← HTML base, SEO, OG tags
├── pages/
│   └── index.astro      ← Página principal
├── components/          ← Seções como componentes .astro
└── styles/
    └── global.css       ← @theme tokens + animações CSS
public/
└── images/              ← Fotos da médica, logo
```

---

## Identidade Visual

**Paleta (referência enviada pela Raquel — aguardando definitiva):**
- Fundo: nude quente (`#EAD4C9` — ref) — ajustar pra não ficar pesado, talvez diluir pra off-white rosado
- Primária: marsala/terracota (`#A2584B` — ref) — botões, nav, headings
- Accent: dourado/caramelo (`#B68766` — ref) — detalhes pequenos, padrões geométricos, dividers (NUNCA em botões ou elementos grandes)
- Texto principal: `#1a1a1a`
- Texto secundário: `#6B7280`

**Tipografia:**
- Headings: fonte serif elegante (Cormorant Garamond ou similar — a definir)
- Body: fonte sans limpa (Lato ou DM Sans — a definir)
- Regras: tight tracking (-0.03em) em headings grandes, line-height 1.7 no body

**Estética:** Editorial sofisticada, quente, feminina premium. Personal branding / lifestyle (sem jaleco). Transmite competência + acolhimento. Padrões geométricos dourados como diferencial sutil (dividers, backgrounds de seção).

**Referências visuais (sites que a Raquel gosta):**
- dramariliaalmeida.med.br — principal ref estética (marsala + nude, personal brand)
- draanaeduardatanios.com.br — ref de foto/lifestyle (verde musgo + terracota, foto dominante)
- flavioendocrinologista.com.br — marido (azul-petróleo + dourado, mais institucional)
- Screenshots full-page em: `C:\Users\Pedro PC\OneDrive\Desktop\GoFullPage\`

**Estilo de foto:** Personal Branding / Lifestyle — sem jaleco. Fotos atuais: look marrom + bege em ambiente de consultório.

---

## Tom de Linguagem

**Tom da Raquel (extraído do docx):** pessoal, caloroso, narrativo. Ela conta sua história em primeira pessoa ("Brinco que a endocrinologia me escolheu..."). Fala de paixão, família, cuidado. O site precisa soar como ela, não como uma clínica genérica.

**Como falar:**
- 1a pessoa: "Acredito em um atendimento individualizado, acolhedor e pautado em evidências científicas"
- Narrativo: história pessoal como diferencial (filha de endocrinologista)
- Educativo: explicar o que o endocrinologista faz sem jargão
- Acolhedor: "vamos construir juntos um plano terapêutico"
- CTAs claros: "Agendar Consulta", "Fale Comigo"

**Evitar:**
- Linguagem excessivamente técnica / CID-10 / jargões sem explicação
- Tom frio e institucional ("Nosso corpo clínico...")
- Promessas de resultado ("Emagreça X kg...")
- 3a pessoa ("A Dra. Raquel oferece...") — ela fala em 1a pessoa

---

## Seções Planejadas (index.astro)

Baseado no docx da Raquel + padrões das referências (Marília, Ana Eduarda):

1. **Header/Navbar** — nav minimalista: nome/logo + links + CTA marsala pill (ref: Marília)
2. **Hero** — foto editorial grande da Raquel + H1 display + subtitle + CTA agendar (ref: Ana Eduarda — foto dominante)
3. **Sobre a Dra. Raquel** — história pessoal (filha de endocrinologista) + foto editorial (look diferente do hero) + credenciais em grid (ref: Marília)
4. **Especialidades** — 10 áreas em cards (3 colunas desktop, stack mobile) com ícone/ilustração + título + descrição curta
5. **Como é o Atendimento** — seção narrativa humanizada (ref: Ana Eduarda "Como funciona minha consulta?")
6. **O que faz o Endocrinologista** — seção educativa (copy pronta no docx)
7. **Formação** — bullets de credenciais + logos institucionais (FCMMG, Santa Casa, Madre Teresa)
8. **Depoimentos** — relatos de pacientes (a coletar)
9. **FAQ** — 5 perguntas (copy pronta no docx), accordion
10. **CTA Final** — WhatsApp + agendamento + localização
11. **Footer**

**Copy:** 100% pronta no docx (`assets-raquel/home_page_consultorio_raquel_cosso.docx`). Transcrita na `docs/ficha.md` seção "Copy Aprovada".

---

## Styling — Regras Obrigatórias

- ALL Tailwind config em `src/styles/global.css` via `@theme`
- **NUNCA** criar `tailwind.config.js`
- **NUNCA** usar `@astrojs/tailwind`
- **NUNCA** usar `@apply`
- **NUNCA** hardcodar hex fora do `@theme`
- Inline Tailwind classes apenas
- Mobile-first (`sm:` up)
- Import global.css APENAS em `Layout.astro`

## JS Policy

Client JS APENAS para:
1. Intersection Observer (scroll-reveal)
2. Header scroll effect
3. Mobile menu toggle

NO frameworks, NO heavy bundles.

## Acessibilidade

- Semantic HTML (`<section>`, `<nav>`, `<main>`, `<footer>`)
- `aria-label` em ícones/botões
- `alt` descritivo em PT-BR
- Focus rings: `focus:ring-2`
- `prefers-reduced-motion` respeitado

## SEO

- Meta tags em PT-BR + Open Graph em `Layout.astro`
- JSON-LD schema (Physician / LocalBusiness)
- Sitemap via `@astrojs/sitemap`
- robots.txt em `public/`

## Convenções

Commits: `feat:` / `fix:` / `refactor:`

**SEMPRE:** build passar antes de commitar | `npm run build` | mobile-first
