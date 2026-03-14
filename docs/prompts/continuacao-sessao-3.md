# Prompt de Continuação — Sessão 3

## Contexto
Site nyresedim.com.br está LIVE. Stack: Astro 5.18 + Tailwind v4, deploy Vercel, repo privado pedrolaender/site-nyres.

Leia STATUS.md, BACKLOG.md e memory/ antes de começar.

## Prioridade 1 — Revisão de densidade de texto

Pedro disse que "o texto está muito cheio". Revisar seção a seção e propor versões mais concisas, especialmente:
- Dores (6 cards com bullet points — pode ser mais direto)
- Como Funciona (5 etapas — texto das descrições pode enxugar)
- Sobre (bio está longa)

**Abordagem:** Ler cada seção, propor versões mais curtas, esperar aprovação antes de alterar.

## Prioridade 2 — FAQ expandido

Atual: 4 perguntas básicas. Pedro quer cobrir:
- O que é o Pathwork (foi removido como seção — vai pro FAQ)
- Dúvidas de quem nunca ouviu falar
- Como agendar / como funciona a primeira sessão
- Valores / planos (só incluir se Nyres quiser)
- Modalidades: individual vs grupos
- Online vs presencial

**Abordagem:** Elaborar as novas perguntas/respostas com base no conteúdo já existente no site + o que o Pathwork é. Validar com Pedro antes de publicar.

## Prioridade 3 — Questionnaire para Nyres

Pedro quer um questionário para Nyres responder e ajudar a identificar personas, público-alvo e refinar o conteúdo da landing page. Criar como documento (Notion ou .md) com perguntas sobre:
- Quem são seus clientes atuais (idade, gênero, momento de vida)
- Como eles chegam até ela (indicação, busca, redes sociais)
- Qual dor/desejo os motiva a buscar terapia
- Qual é a principal objeção antes de marcar
- O que os clientes dizem depois de começar
- Modalidades: individual, grupo, online, presencial, duração, frequência

## Estado atual do código

Componentes ativos na landing:
1. Header (teal-deep)
2. Hero (foto + 2 CTAs)
3. Dores (6 cards)
4. ComoFunciona (5 etapas)
5. Depoimentos (4 reais)
6. Sobre
7. FAQ (4 perguntas)
8. CTAFinal
9. Footer
10. WhatsAppButton

Seção Pathwork.astro existe no repo mas não está em uso (removida do index.astro).
