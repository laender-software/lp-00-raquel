# Session Log — 2026-03-05 — Setup Inicial

## O que foi feito

1. **Extração de conteúdo** do WordPress anterior (nyresedim.com.br na HostGator)
   - Via WP REST API: /wp-json/wp/v2/pages e /wp-json/wp/v2/media
   - Conteúdo: hero, 6 dores, 5 etapas, Pathwork, 4 depoimentos, bio, FAQ, endereço
   - 15 imagens baixadas (fotos Tati Motta, logo, designs)

2. **Análise de identidade visual**
   - Logo, Instagram (@nyresedim), fotos profissionais analisados
   - Paleta extraída: teal (#1A5C5A) + brown (#4A2810) + sand (#D4BFA0) + cream (#F5F0EB)
   - Fonts escolhidas: Cormorant Garamond + Lato

3. **Scaffold Astro 5.18 + Tailwind v4**
   - 11 componentes criados (Header, Hero, Dores, Pathwork, ComoFunciona, Depoimentos, Sobre, FAQ, CTAFinal, Footer, WhatsAppButton)
   - Micro-animações: scroll reveal, hover zoom, card lift, button glow, stagger, float

4. **Deploy**
   - Repo: github.com/pedrolaender/site-nyres (privado)
   - Vercel: auto-deploy configurado
   - DNS: Registro.br → ns1/ns2.vercel-dns.com

## Decisões

- Landing page única (não multi-page) — páginas internas são futuro
- Paleta real da marca (não inventada)
- Conteúdo reaproveitado do WordPress (bem escrito)
- WhatsApp: +55 31 98585-0589

## Pendências pós-sessão

- DNS propagação (pode levar até 48h)
- Feedback da Nyres sobre visual
- Migrar <img> para Astro <Image>
- JSON-LD Schema
- prefers-reduced-motion
