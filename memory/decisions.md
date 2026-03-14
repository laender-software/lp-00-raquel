# Decisões — site-nyres

## Astro puro (sem React/Vue)
- **Data:** 2026-03-05
- **Contexto:** Landing page estática com animações CSS
- **Decisão:** Astro 5 + Tailwind v4, sem frameworks JS
- **Razão:** Performance máxima, mesmo stack do site-julia

## Paleta extraída da marca real
- **Data:** 2026-03-05
- **Contexto:** Análise de logo, Instagram (@nyresedim) e fotos profissionais
- **Decisão:** Teal-deep (#1A5C5A) como primária, sand (#D4BFA0) como secundária, brown (#4A2810) para texto
- **Razão:** Consistência com identidade visual existente — Instagram usa teal overlay, logo é sand/cream

## Cormorant Garamond + Lato
- **Data:** 2026-03-05
- **Contexto:** Logo usa script fino/elegante; Instagram usa serif editorial + sans clean
- **Decisão:** Cormorant Garamond (serif refinada) + Lato (sans limpa)
- **Razão:** Combina com o tom sofisticado e acolhedor da marca

## Landing page única com seções (não multi-page)
- **Data:** 2026-03-05
- **Contexto:** Pedro perguntou se seriam páginas separadas
- **Decisão:** Home (/) = landing page autossuficiente com todas as seções. Páginas internas futuras como bônus.
- **Razão:** 90% dos visitantes resolvem tudo na home. Páginas extras são pra SEO e aprofundamento.

## Conteúdo reaproveitado do WordPress
- **Data:** 2026-03-05
- **Contexto:** Site WordPress na HostGator visualmente quebrado, mas conteúdo intacto
- **Decisão:** Extrair tudo via WP REST API e recriar em Astro
- **Razão:** Conteúdo bem escrito (irmã do Pedro), só o visual estava quebrado

## Deploy Vercel + DNS via Registro.br (endereçamento A)
- **Data:** 2026-03-05
- **Decisão:** Registro.br não aceita nameservers externos — usou DNS próprio com registro tipo A apontando para 76.76.21.21 (Vercel)
- **Razão:** Única forma que funcionou. Nameservers externos eram revertidos automaticamente pelo Registro.br.

## Seção "O Método" (Pathwork) removida da landing page
- **Data:** 2026-03-05
- **Decisão:** Remover seção verde escura com texto sobre o método Pathwork
- **Razão:** Conteúdo redundante com FAQ; landing mais limpa sem ela. Conteúdo sobre o método vai para FAQ expandido (próxima sessão).

## Header todo em teal-deep
- **Data:** 2026-03-05
- **Decisão:** Header fixo 100% teal-deep, links brancos, CTA em sand
- **Razão:** Solicitação do Pedro para dar mais presença visual ao cabeçalho.

## CSS scoping do Astro quebra seletores descendentes cross-component
- **Data:** 2026-03-05
- **Decisão:** Usar classes Tailwind com `group`/`group-hover` em vez de `.photo-zoom img` no global.css
- **Razão:** Astro escopa CSS com `data-astro-cid-*`. Seletores `.wrapper img` não funcionam quando wrapper e img estão em componentes diferentes.

## Labels de seção: teal-deep + 18px
- **Data:** 2026-03-05
- **Decisão:** Labels uppercase de seção mudaram de `text-teal text-base` para `text-teal-deep text-lg`
- **Razão:** Pedro achou o verde pálido demais; queria o mesmo verde do header. Fonte 18px para mais presença.

## Link underlines removidos globalmente
- **Data:** 2026-03-05
- **Decisão:** `a { text-decoration: none }` via `<style is:global>` no Layout.astro
- **Razão:** Tailwind v4 preflight não remove underlines por padrão. Regra no global.css era escopada pelo Astro e não atingia componentes filhos. Precisou de `<style is:global>` separado.
