# Stack — site-nyres

## Frontend
- **Framework:** Astro 5.18 (puro, sem React/Vue)
- **Estilo:** Tailwind CSS v4 (config via @theme no CSS, não tailwind.config)
- **Plugin Tailwind:** `@tailwindcss/vite` (NOT `@astrojs/tailwind`)
- **Sitemap:** `@astrojs/sitemap`

## Tipografia
- **Serif (títulos):** Cormorant Garamond (Google Fonts)
- **Sans (corpo):** Lato (Google Fonts)

## Paleta de cores
```
teal-deep:    #1A5C5A   (primária — botões, seções escuras)
teal:         #5E8E91   (acentos, links hover)
teal-light:   #89AFA8   (texto secundário em fundo escuro)
teal-soft:    #B5D5D0   (texto terciário)
brown:        #4A2810   (texto principal, logo)
brown-light:  #8A7D72   (texto secundário)
sand:         #D4BFA0   (logo, CTAs em fundo escuro)
cream:        #F5F0EB   (fundo principal)
warm:         #EDE6DD   (fundo alternado)
```

## Deploy
- **Hospedagem:** Vercel (plano gratuito)
- **CI/CD:** Auto-deploy via GitHub push
- **Domínio:** nyresedim.com.br (Registro.br → Vercel DNS)

## Imagens
- Fotos profissionais por Tati Motta Fotografia (2025)
- Armazenadas em `public/images/`
- Logo original em `public/images/logo.png`
