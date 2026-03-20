# Conventions Vybe Digital

> Standards de code, nommage et patterns pour tous les projets.

## Stack

- **Framework** : Next.js 14+ App Router
- **Langage** : TypeScript strict
- **Styles** : CSS Modules + Variables CSS natives (pas de Tailwind sauf demande)
- **Animations** : GSAP Core + ScrollTrigger
- **Fonts** : next/font (Google Fonts optimisé)
- **Images** : next/image
- **Forms** : react-hook-form + zod
- **Deploy** : Vercel (recommandé) ou Netlify

## Arborescence

```
src/
├── app/                 # Routes App Router
│   ├── layout.tsx       # Layout racine (fonts, metadata globale)
│   ├── page.tsx         # Homepage
│   ├── [slug]/          # Pages dynamiques
│   ├── sitemap.ts       # Sitemap auto
│   └── robots.ts        # Robots.txt
├── components/          # Composants réutilisables
│   ├── Hero/            # Un dossier par composant complexe
│   │   ├── Hero.tsx
│   │   ├── Hero.module.css
│   │   └── index.ts
│   ├── ui/              # Atoms (Button, Input, Badge, etc.)
│   └── layout/          # Header, Footer, Nav
├── lib/                 # Données, helpers, utils
├── styles/              # Tokens globaux
│   ├── tokens.css
│   ├── typography.css
│   ├── spacing.css
│   └── globals.css
└── types/               # Interfaces TypeScript
    └── index.ts
```

## Nommage

| Élément | Convention | Exemple |
|---|---|---|
| Composants | PascalCase | `HeroSection.tsx` |
| CSS Modules | camelCase dans le code | `styles.heroTitle` |
| Classes CSS | BEM | `.hero__title--italic` |
| Variables | camelCase | `const scrollY = 0` |
| Constantes | SCREAMING_SNAKE | `const API_URL = '...'` |
| Fichiers types | PascalCase | `types/index.ts` |
| Routes | kebab-case | `app/nos-specialites/page.tsx` |

## Composants

- Server Component par défaut
- `'use client'` uniquement si : useState, useEffect, useRef, event handlers, GSAP
- Props typées explicitement (pas de `any`)
- Barrel export via `index.ts`
- Découper si > 200 lignes
- Commentaires en français sur les blocs complexes
- Code (variables, fonctions) en anglais

## CSS

- Variables CSS dans `:root` (tokens.css)
- CSS Modules pour les composants (`.module.css`)
- Mobile-first (styles de base = mobile, media queries = desktop)
- `clamp()` pour les tailles fluides
- Pas de styles inline sauf valeurs dynamiques calculées
- Breakpoints : 375px / 768px / 1024px / 1440px

## GSAP

- Toujours dans un `useEffect` avec cleanup via `gsap.context()`
- `useRef` pour cibler les éléments (pas de querySelector)
- ScrollTrigger avec `scrub: true` pour le parallax
- Timeline nommée pour les séquences d'entrée
- `gsap.registerPlugin(ScrollTrigger)` une seule fois

```tsx
useEffect(() => {
  const ctx = gsap.context(() => {
    const tl = gsap.timeline({ defaults: { ease: 'power3.out' } });
    tl.fromTo(titleRef.current, { opacity: 0, y: 30 }, { opacity: 1, y: 0 });
    // ...
  }, containerRef);
  return () => ctx.revert();
}, []);
```

## SEO

- `metadata` export sur chaque page
- `generateMetadata` pour les pages dynamiques
- Schema.org JSON-LD (LocalBusiness, FAQPage, BreadcrumbList)
- `sitemap.ts` + `robots.ts`
- `alt` descriptif sur toutes les images
- Pas de contenu dupliqué

## Accessibilité (WCAG AA)

- Contraste ≥ 4.5:1
- `aria-label` sur les boutons sans texte visible
- Focus visible (`:focus-visible`)
- Navigation clavier fonctionnelle
- `lang="fr"` sur `<html>`
- Touch targets ≥ 44px
