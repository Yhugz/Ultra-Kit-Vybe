# ✦ VYBE WORKFLOW — TODO TEMPLATE
> Template universel pour projets web Next.js App Router · Copier, adapter, cocher.

---

## 0. BRIEF & DÉCOUVERTE

- [ ] Définir le nom du projet / client
- [ ] Identifier le secteur d'activité et les concurrents directs
- [ ] Définir les objectifs principaux (SEO local, vitrine, e-commerce, SaaS…)
- [ ] Identifier la cible (particuliers, professionnels, B2B…)
- [ ] Définir le ton éditorial (premium, jeune, corporate, technique…)
- [ ] Lister les pages nécessaires (homepage, services, contact, légales…)
- [ ] Collecter les contenus existants (textes, images, logos, couleurs)
- [ ] Recueillir les infos de contact (téléphone, email, adresse, horaires)
- [ ] Recueillir les comptes sociaux (Instagram, Facebook, LinkedIn…)
- [ ] Définir le domaine cible (ex : mon-projet.fr)

---

## 1. ARCHITECTURE

- [ ] Initialiser le projet Next.js App Router + TypeScript strict
  ```bash
  npx create-next-app@latest --typescript --app --tailwind=false
  ```
- [ ] Configurer `tsconfig.json` avec les paths absolus (`@/`)
- [ ] Définir l'arborescence `src/`
  ```
  src/
  ├── app/            # Routes App Router
  ├── components/     # Composants réutilisables
  ├── lib/            # Données, helpers, utils
  ├── styles/         # globals.css + tokens
  └── types/          # index.ts avec interfaces
  ```
- [ ] Créer `types/index.ts` avec les interfaces clés du projet
- [ ] Identifier les Server Components vs Client Components
- [ ] Créer les layouts nécessaires (`layout.tsx` racine, layouts de sections)
- [ ] Lister les routes statiques et dynamiques (`generateStaticParams`)
- [ ] Installer les dépendances essentielles
  - [ ] `lucide-react` — icônes
  - [ ] `next/font` — polices optimisées
  - [ ] GSAP CDN (animations) ou `npm install gsap`
  - [ ] `react-hook-form` + `zod` si formulaires
  - [ ] `zustand` si state global
  - [ ] `next-intl` si i18n
- [ ] Configurer les variables d'environnement
  - [ ] Créer `.env.local` à la racine avec toutes les variables nécessaires
  - [ ] Créer `.env.example` (sans valeurs) — à versionner sur Git
  - [ ] Vérifier que `.env.local` est bien dans `.gitignore`
  - [ ] Documenter chaque variable avec un commentaire inline
  ```bash
  # Exemple .env.example
  NEXT_PUBLIC_SITE_URL=        # URL publique du site
  NEXT_PUBLIC_GA_ID=           # Google Analytics 4 (G-XXXXXXXXXX)
  RESEND_API_KEY=              # API key formulaire de contact
  NEXT_PUBLIC_WHATSAPP_NUMBER= # Numéro WhatsApp international
  ```

---

## 2. DESIGN SYSTEM

- [ ] Définir les design tokens dans `styles/tokens.css`
  - [ ] Couleurs (primaire, secondaire, accent, neutres)
  - [ ] Espacements (4px, 8px, 16px, 24px, 32px, 48px, 64px…)
  - [ ] Typographies (font-family, tailles, line-heights, letter-spacing)
  - [ ] Breakpoints (375px / 768px / 1024px / 1440px)
  - [ ] Border-radius standards
  - [ ] Ombres / box-shadow
- [ ] Valider la palette en contraste WCAG 2.1 AA (ratio ≥ 4.5:1)
- [ ] Définir les variables CSS natives dans `:root`
- [ ] Créer les composants atoms
  - [ ] Boutons (primary, secondary, outline, ghost)
  - [ ] Inputs / textarea
  - [ ] Badge / tag
  - [ ] Icône wrapper
- [ ] Créer les composants molecules
  - [ ] Card
  - [ ] Navigation item
  - [ ] Form field avec label + error
- [ ] Documenter la convention BEM (`.bloc__element--modificateur`)

---

## 3. COMPOSANTS GLOBAUX

### Header / Navigation
- [ ] Logo cliquable → `/`
- [ ] Liens desktop avec dropdowns si nécessaire
- [ ] Tous les liens anchor sur page hors-homepage → `/#section` (pas `#section`)
- [ ] Bouton CTA principal visible
- [ ] Menu burger mobile + drawer animé
- [ ] Effet scroll (navbar transparente → fond flouté au scroll)
- [ ] Accessibilité : `aria-label` sur burger, focus trap sur drawer

### Footer
- [ ] Liens légaux (Mentions légales, Politique de confidentialité)
- [ ] Infos de contact (téléphone, email, adresse)
- [ ] Liens sociaux
- [ ] Copyright + année dynamique

### Composants utilitaires
- [ ] `Loader` — animation de chargement initial
- [ ] `WhatsAppButton` — bouton flottant (si numéro WhatsApp disponible)
- [ ] `CookieConsent` — bandeau RGPD
- [ ] `ScrollAnimations` — GSAP ScrollTrigger (si animations scroll)
- [ ] `ClientScripts` — JS interactif côté client (accordéon FAQ, etc.)

---

## 4. PAGES

### Homepage
- [ ] **Hero** — titre H1 fort, tagline, CTA principal, image/vidéo
  - [ ] H1 optimisé SEO (mot-clé principal + localisation)
  - [ ] CTA → section contact ou page service principale
  - [ ] Image avec `alt` descriptif
- [ ] **Section présentation / À propos**
  - [ ] Manifesto title percutant
  - [ ] Lead paragraph (conviction / positionnement)
  - [ ] 3 piliers ou valeurs clés numérotés
  - [ ] Image illustrative
- [ ] **Section services / expertises**
  - [ ] Liste ou slider des services
  - [ ] Lien vers chaque page service
- [ ] **Section FAQ**
  - [ ] 6 questions minimum orientées intentions de recherche
  - [ ] Accordéon JS fonctionnel
- [ ] **Section contact**
  - [ ] Téléphone cliquable (`tel:`)
  - [ ] Email cliquable (`mailto:`)
  - [ ] Adresse / zone d'intervention
- [ ] **Section carte** (si adresse physique)

### Pages services / expertises
- [ ] `generateStaticParams` pour génération statique
- [ ] `generateMetadata` dynamique (title + description uniques par page)
- [ ] Breadcrumb cliquable
- [ ] Hero avec titre H1 + image
- [ ] Contenu détaillé (description, avantages, process)
- [ ] CTA WhatsApp / contact en fin de page
- [ ] Lien retour vers catalogue

### Page catalogue (si plusieurs services)
- [ ] Design éditorial (chapitres, numérotation, familles)
- [ ] Cards numérotées avec lien vers chaque page
- [ ] CTA final

### Pages légales
- [ ] Mentions légales
  - [ ] Éditeur, hébergeur, SIRET
  - [ ] Directeur de publication
- [ ] Politique de confidentialité
  - [ ] Données collectées, durée de conservation
  - [ ] Droits RGPD (accès, rectification, suppression)
  - [ ] Contact DPO / email de contact
- [ ] Vérifier : pas de header/banner dupliqué sur ces pages

### Page 404
- [ ] Message clair + lien retour accueil

---

## 5. COPYWRITING

Pour chaque page, valider :

| Élément | Contrainte |
|---|---|
| H1 / Titre principal | 40–65 caractères, mot-clé principal |
| H2 / Sous-titres | 30–55 caractères |
| Paragraphes | 2–3 phrases max, 80–120 mots par bloc |
| CTA | 2–5 mots, verbe d'action |
| Meta title | 50–60 caractères |
| Meta description | 140–155 caractères, intent clair |
| Alt text images | Descriptif + mot-clé naturel |

- [ ] Ton cohérent sur toutes les pages
- [ ] Pas de jargon inutile
- [ ] Phrases courtes, structure en F ou Z
- [ ] Questions FAQ orientées intentions de recherche Google

---

## 6. SEO TECHNIQUE

### Metadonnées
- [ ] `metadata` export sur chaque page (title + description uniques)
- [ ] `openGraph` sur les pages clés (title, description, image, url, locale)
- [ ] `verification.google` dans le layout racine
- [ ] Favicon + apple-touch-icon
- [ ] `canonical` si duplication possible

### Schema.org JSON-LD
- [ ] `LocalBusiness` — nom, adresse, téléphone, email, horaires, coordonnées GPS
- [ ] Type métier spécifique (`AutoDealer`, `Restaurant`, `LegalService`…)
- [ ] `WebSite` — url, nom, publisher
- [ ] `FAQPage` — toutes les questions/réponses de la FAQ homepage
- [ ] `BreadcrumbList` — sur toutes les pages profondes
- [ ] `Service` — sur chaque page service/expertise
- [ ] Vérification : [search.google.com/test/rich-results](https://search.google.com/test/rich-results)

### Sitemap & Robots
- [ ] `src/app/sitemap.ts` — sitemap dynamique incluant toutes les routes
  ```ts
  export default function sitemap(): MetadataRoute.Sitemap { ... }
  ```
- [ ] `src/app/robots.ts` — allow all + pointer vers sitemap
- [ ] Vérifier le sitemap après déploiement : `https://domaine.fr/sitemap.xml`

### Performance
- [ ] Migrer tous les `<img>` → `next/image` (automatique lazy loading + optimisation)
- [ ] Polices via `next/font` (pas de Google Fonts CDN externe)
- [ ] Vérifier qu'il n'y a pas de layout shift (CLS) sur les images
- [ ] Lighthouse score ≥ 90 en Performance, Accessibilité, SEO
- [ ] Vérifier dans Chrome DevTools : pas de ressources bloquantes

---

## 7. ACCESSIBILITÉ

- [ ] Tous les boutons ont un `aria-label` si pas de texte visible
- [ ] Images décoratives : `alt=""`
- [ ] Focus visible sur tous les éléments interactifs (`:focus-visible`)
- [ ] Contraste couleurs ≥ 4.5:1 (texte normal) / 3:1 (texte large)
- [ ] Navigation au clavier fonctionnelle (tab order logique)
- [ ] `lang="fr"` sur la balise `<html>`
- [ ] Rôles ARIA corrects sur les composants custom (drawer, accordéon)
- [ ] Pas de `tabindex` positif

---

## 8. RESPONSIVE

- [ ] Mobile-first (styles de base = mobile, media queries = desktop)
- [ ] Tester sur 375px (iPhone SE), 768px (tablette), 1280px, 1440px
- [ ] Pas de scroll horizontal sur mobile
- [ ] Tailles de texte lisibles sans zoom (≥ 14px)
- [ ] Touch targets ≥ 44px (boutons, liens)
- [ ] Navigation mobile : menu burger + drawer fonctionnel
- [ ] Images fluides (`width: 100%; max-width: Xpx`)

---

## 9. ANALYTICS & TRACKING

- [ ] Google Analytics 4 — `G-XXXXXXXXXX`
  - [ ] Script dans `layout.tsx` avec `strategy="afterInteractive"`
  - [ ] Vérifier la réception des events dans GA4 après déploiement
- [ ] Google Search Console
  - [ ] Vérification propriété (DNS ou meta tag)
  - [ ] Soumettre le sitemap
- [ ] Google Business Profile
  - [ ] Créer / réclamer la fiche si non existante
  - [ ] Ajouter URL du site, horaires, photos, catégorie
- [ ] Vérifier que le cookie consent bloque les scripts tiers avant accord

---

## 10. QUALITÉ CODE

- [ ] TypeScript sans erreur (`npm run build` propre)
- [ ] Pas de `any` sans justification
- [ ] `'use client'` uniquement là où c'est nécessaire
- [ ] Imports absolus via `@/` partout
- [ ] Pas de `console.log` en production
- [ ] ESLint propre (`npm run lint`)
- [ ] Composants > 200 lignes découpés
- [ ] Pas de styles inline sauf valeurs dynamiques
- [ ] Pas de `useEffect` pour le data fetching (Server Components)
- [ ] Commentaires en français sur les blocs complexes

---

## 11. PRÉ-LANCEMENT

- [ ] Relire tous les textes (fautes, cohérence, ton)
- [ ] Vérifier tous les liens internes (pas de 404)
- [ ] Vérifier tous les liens externes (tel:, mailto:, WhatsApp)
- [ ] Vérifier le formulaire de contact si existant (envoi + réception)
- [ ] Vérifier les métadonnées avec [metatags.io](https://metatags.io)
- [ ] Vérifier le Schema.org avec [Rich Results Test](https://search.google.com/test/rich-results)
- [ ] Vérifier les performances avec Lighthouse (DevTools)
- [ ] Vérifier le rendu sur iOS Safari + Chrome Android
- [ ] Vérifier le favicon dans l'onglet navigateur
- [ ] Vérifier le comportement du cookie consent RGPD
- [ ] Supprimer les pages / composants non utilisés
- [ ] `npm run build` final — 0 erreur, 0 warning TypeScript

---

## 12. DÉPLOIEMENT

- [ ] Choisir la plateforme de déploiement
  - [ ] **Vercel** — recommandé pour Next.js (SSR natif, Edge Functions, analytics)
  - [ ] **Netlify** — alternative viable (attention : Next.js SSR via plugin `@netlify/plugin-nextjs`)
- [ ] Créer un compte / projet sur la plateforme choisie
- [ ] Connecter le repo GitHub
- [ ] Reporter toutes les vars de `.env.example` dans la plateforme
  - [ ] Vercel : Settings > Environment Variables
  - [ ] Netlify : Site configuration > Environment variables
- [ ] Configurer le domaine custom
  - [ ] Ajouter les DNS (A record ou CNAME) chez le registrar
  - [ ] Activer HTTPS automatique (les deux plateformes le gèrent)
  - [ ] Vérifier la redirection `www` → racine (ou inverse)
- [ ] Premier déploiement — vérifier toutes les pages en prod
- [ ] Soumettre l'URL dans Google Search Console
- [ ] Soumettre le sitemap dans Google Search Console
- [ ] Vérifier la fiche Google Business Profile avec la nouvelle URL

---

## 13. POST-LANCEMENT

- [ ] Surveiller les Core Web Vitals dans Search Console (J+30)
- [ ] Vérifier l'indexation des pages principales (J+14)
- [ ] Surveiller les erreurs 404 dans Search Console
- [ ] Mettre en place un suivi mensuel des positions SEO
- [ ] Planifier les mises à jour de contenu (blog, nouveautés…)

---

*Template Vybe Workflow Kit — github.com/Yhugz/To-do*
