# CLAUDE.md — Site Raquel (Endocrinologista)

Landing page profissional para **Dra. Raquel** — Endocrinologista. Conversion-focused: cada seção direciona para agendamento (WhatsApp ou sistema de agendamento). Static only, NO SSR.

**Goals:** Lighthouse 95+, mobile-first, accessibility AA, tom profissional, acolhedor e confiável.

## O Projeto

Site institucional para endocrinologista. Público-alvo: pacientes que buscam consulta com especialista em hormônios, tireoide, diabetes, obesidade, menopausa, etc.

**Dados reais (preencher conforme briefing):**
- Nome: Dra. Raquel [sobrenome a confirmar]
- CRM: a confirmar
- Especialidades: Endocrinologia + [subespecialidades a confirmar]
- Localização: a confirmar
- WhatsApp: a confirmar
- Instagram: a confirmar
- Site de agendamento: a confirmar

---

## Stack

- **Framework:** Astro 5 (static)
- **Estilos:** Tailwind CSS v4 via `@tailwindcss/vite` (NOT `@astrojs/tailwind`)
- **Fontes:** Google Fonts — serif elegante para headings (ex: Cormorant Garamond), sans clean para corpo (ex: Lato ou Inter)
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

**Paleta (a definir com Pedro/Raquel — sugestão inicial):**
- Fundo: branco / off-white suave (`#FAFAF8`)
- Primária: azul-cinza médico / verde-teal suave (transmite saúde, confiança)
- Accent: dourado suave ou verde-salva (elegância + saúde)
- Texto principal: `#1a1a1a`
- Texto secundário: `#6B7280`

**Tipografia:**
- Headings: fonte serif elegante (Cormorant Garamond ou Playfair Display)
- Body: fonte sans limpa (Lato, Inter ou DM Sans)

**Estética:** Clínica premium, acolhedora, feminina/neutra. Transmite competência sem ser fria. Inspiração: consultórios premium, marcas de saúde de alto padrão.

---

## Tom de Linguagem

**Como falar:**
- Empático e profissional: "Cuidamos do seu equilíbrio hormonal com atenção personalizada"
- Educativo: explicar brevemente o que é endocrinologia sem ser técnico demais
- Acolhedor: paciente precisa se sentir seguro antes de agendar
- CTAs claros: "Agendar Consulta", "Fale Comigo", "Marque sua Consulta"

**Evitar:**
- ❌ Linguagem excessivamente técnica / CID-10 / jargões médicos sem explicação
- ❌ Tom frio e institucional ("Nosso corpo clínico...")
- ❌ Promessas de resultado ("Emagreça X kg...")

---

## Seções Planejadas (index.astro)

1. **Header/Navbar** — logo + CTA "Agendar Consulta"
2. **Hero** — foto da Dra. Raquel, headline principal, CTA
3. **Especialidades** — cards com as áreas de atuação (tireoide, diabetes, obesidade, hormônios, menopausa, etc.)
4. **Dores do Público** — problemas que os pacientes chegam com (fadiga, ganho de peso, alterações hormonais, etc.)
5. **Sobre a Dra. Raquel** — formação, CRM, experiência, diferenciais
6. **Como Funciona** — processo de agendamento / consulta (etapas simples)
7. **Depoimentos** — relatos de pacientes (a coletar)
8. **FAQ** — dúvidas frequentes sobre endocrinologia / consulta
9. **CTA Final** — WhatsApp + agendamento + localização
10. **Footer**

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
