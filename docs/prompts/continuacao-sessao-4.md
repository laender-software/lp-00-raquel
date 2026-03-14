# Prompt de Continuacao — Sessao 4

## Contexto
Site nyresedim.com.br LIVE. Stack: Astro 5.18 + Tailwind v4, deploy Vercel, repo privado pedrolaender/site-nyres.

Leia STATUS.md, BACKLOG.md e memory/ antes de comecar.

## Prioridade 1 — FAQ expandido

Depende das respostas do questionario (docs/questionario-nyres.md). Se Nyres ja respondeu:
- Usar respostas para criar novas perguntas/respostas pro FAQ
- Expandir de 4 para ~10 perguntas
- Incluir: o que e Pathwork, primeira sessao, modalidades (individual vs grupo), online vs presencial
- Validar com Pedro antes de publicar

Se Nyres ainda nao respondeu, seguir com prioridade 2.

## Prioridade 2 — Contraste WCAG AA

- Testar contraste de todas as combinacoes de cor do site
- Ferramenta sugerida: WebAIM Contrast Checker ou similar
- Foco: texto sobre fundos cream/warm, labels teal-deep, botoes

## Prioridade 3 — SSL/HTTPS

- Confirmar que nyresedim.com.br roda com HTTPS via Vercel
- Verificar redirect HTTP → HTTPS

## Estado atual do codigo

Componentes ativos na landing:
1. Header (teal-deep, sticky)
2. Hero (foto + 2 CTAs, sem underline)
3. Dores (6 cards, label teal-deep)
4. ComoFunciona (5 etapas)
5. Depoimentos (4 reais)
6. Sobre
7. FAQ (4 perguntas — accordion nativo)
8. CTAFinal
9. Footer
10. WhatsAppButton

CSS global em global.css (escopado pelo Astro).
Link underlines removidos via `<style is:global>` no Layout.astro.
Secao Pathwork.astro existe no repo mas nao esta em uso.
