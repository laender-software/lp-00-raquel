# Lições — site-nyres

## WP REST API funciona mesmo com tema quebrado
- **Data:** 2026-03-05
- **Descoberta:** Site WordPress visualmente destruído, mas API REST retorna todo o conteúdo estruturado
- **Aplicação:** Sempre tentar WP REST API antes de scraping manual

## Fotos profissionais no WordPress são acessíveis via /wp-json/wp/v2/media
- **Data:** 2026-03-05
- **Descoberta:** Endpoint retorna todas as imagens com URLs diretas, títulos e metadados
- **Aplicação:** Boa forma de extrair assets de sites WordPress antes de migrar

## Instagram API (RapidAPI) retorna dados em formato diferente do esperado
- **Data:** 2026-03-05
- **Descoberta:** instagram120 retorna `result.edges[].node` (não `items[]`). Precisa navegar a estrutura.
- **Aplicação:** Sempre testar o formato de resposta antes de parsear

## Vercel bloqueia deploys de commits sem Git user associado à conta
- **Data:** 2026-03-05
- **Descoberta:** Commits feitos pelo servidor (root) são bloqueados no plano Hobby
- **Solução:** Configurar `git config user.email` com o email do dono da conta Vercel
- **Aplicação:** Sempre configurar Git user correto no servidor antes de fazer push

## Registro.br não aceita nameservers externos — usar DNS próprio com registro A
- **Data:** 2026-03-05
- **Descoberta:** Registro.br reverte automaticamente para HostGator ao tentar salvar ns1/ns2.vercel-dns.com. A solução foi ativar "DNS do Registro.br" e configurar endereçamento tipo A para 76.76.21.21.
- **Aplicação:** Para domínios .br.com.br na Vercel: DNS do Registro.br + registro A = 76.76.21.21. Não tentar trocar nameservers.

## Astro escopa CSS global causando falha em seletores cross-component
- **Data:** 2026-03-05
- **Descoberta:** CSS importado em Layout.astro via `<style>@import</style>` recebe `[data-astro-cid-XXXX]` em todos os seletores. Seletor `.photo-zoom img` não funciona quando `.photo-zoom` está em Hero.astro e `<img>` é gerado por astro:assets — cada um tem seu próprio cid.
- **Solução 1:** Usar `group` + `group-hover:scale-105` no Tailwind (inline no componente).
- **Solução 2:** Para regras CSS verdadeiramente globais (ex: `a { text-decoration: none }`), usar `<style is:global>` separado no Layout.astro. Regras no `global.css` importado via `<style>` são ESCOPADAS.
- **Aplicação:** Nunca assumir que global.css é global no Astro — depende de COMO é importado. `<style>` = scoped. `<style is:global>` = global real.
