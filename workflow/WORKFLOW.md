# Workflow complet — Cahier des charges → Prompts → GitHub → Netlify

## Objectif

Standardiser un process **propre, méthodique et reproductible** pour créer et livrer des projets (stack cible : Next.js 14 / TypeScript / CSS modern / GSAP si besoin), puis déployer sur Netlify.

## Workflow (macro)

CAHIER DES CHARGES SIGNÉ  
↓  
Étape 0 — Raisonnement sectoriel UUPM *(si client sans charte ou secteur inconnu)*  
↓  
Prompt 1 — Architecture  
↓  
Prompt 2 — Design System  
↓  
Prompt 2.5 — Composant Créatif *(pour chaque composant visuel à fort impact)*  
↓  
Prompt 3 — Exécution Créative  
↓  
Prompt 4 — Copywriting  
↓  
Prompt 5 — Modules complexes (si besoin)  
↓  
Gate QA — Pré-livraison  
↓  
Push Git → Netlify

## Checklist — CAHIER DES CHARGES (avant tout)

- **Validation** : cahier des charges signé ou validation écrite (email / message).
- **Objectifs** : objectif principal + objectifs secondaires.
- **Cible** : audience, objections, déclencheurs, contexte d’usage.
- **Contenu** : pages nécessaires, contenus fournis vs à rédiger.
- **SEO** : mots-clés, zones géographiques, pages prioritaires.
- **Contraintes** : délai, RGPD, mentions légales, tracking.
- **Design** : références, couleurs, typographies, assets existants.
- **Technique** : domaine, hébergement (Netlify), formulaires, intégrations.

> Astuce : utiliser `workflow/CAHIER_DES_CHARGES_TEMPLATE.md` pour structurer la collecte quand le PDF n’est pas encore rempli.
## Étape 0 — Raisonnement sectoriel UUPM *(optionnel)*

> Déclencher **uniquement si** le client n'a pas de charte graphique, ou si le secteur est peu familier.

**Quand l'utiliser**
- Client sans logo ni charte → UUPM recommande palette + font pairing
- Secteur inconnu (médical, fintech, juridique…) → UUPM donne le bon pattern de landing + anti-patterns à éviter
- Besoin d'un brief design rapid pour aligner client avant Prompt 2

**Commande**
```bash
# Installer UUPM une seule fois dans le projet
npm install -g uipro-cli
uipro init --ai copilot   # ou --ai cursor / --ai claude

# Générer le design system sectoriel et le persister
python3 .claude/skills/ui-ux-pro-max/scripts/search.py \
  "[SECTEUR CLIENT ex: vitrine lead gen B2B]" \
  --design-system --persist \
  -p "[NOM CLIENT]"
```

**Sortie** : `design-system/MASTER.md` — à coller en entrée du **Prompt 2** à la place ou en complément de la charte client.

**Anti-patterns sectoriels notables**
- Finance / Banque → Pas de gradient AI violet/rose, pas d'animations rapides
- Santé / Médical → Pas de dark mode agressif, pas de Brutalism
- Vitrine B2B → Pas de couleurs saturées néon, pas de scroll-jacking intrusif
- Luxe → Pas d'emojis, pas de Claymorphism, pas de Bento Grid chargé
- SaaS → Pas de serif lourd, pas de fond blanc pur (préférer off-white)

> Pour accéder à la liste complète des 100 règles : `python3 .claude/skills/ui-ux-pro-max/scripts/search.py "[secteur]" --domain style`
## Étape 1 — Prompt 1 (Architecture)

**Entrées**
- Cahier des charges (PDF ou texte)

**Sorties attendues**
- Sitemap complet (slugs FR)
- 3 parcours utilisateurs (entrée → conversion)
- Inventaire des sections (par page)
- Liste de composants UI réutilisables
- Liste d’intégrations (formulaires, APIs, outils)

**Fichier**
- `prompts/01-architecture.md`

## Étape 2 — Prompt 2 (Design System)

**Entrées**
- Cahier des charges

**Sorties attendues**
- `tokens.css`, `typography.css`, `spacing.css`, `components.css`
- Principes motion (durées + easings recommandées GSAP)
- Contraintes : Next.js 14 App Router, WCAG AA, zéro dépendance (sauf GSAP)

**Fichier**
- `prompts/02-design-system.md`

## Étape 2.5 — Prompt 2.5 (Composant Créatif — single-shot)

> À utiliser pour chaque composant visuel à fort impact, **indépendamment** de l'étape 3.
> Remplace la séquence Prompt 2 + Prompt 3 pour CE composant uniquement.

**Quand déclencher**
- Hero section, landing hero, toute section "wow" ou signature
- Section À propos cinématique, galerie immersive
- Tout composant où animation + design + contenu sont **indissociables**

**Entrées**
- Cahier des charges complet
- Contenus réels (textes, plats, horaires, prix — pas de placeholder)
- Identité visuelle réelle (couleurs vérifiées sur carte/logo/lieu, pas juste le CDC)
- Direction créative (2–3 phrases : effet voulu, émotion, référence)
- `styles/tokens.css` si déjà généré

**Sorties attendues**
- Composant TSX complet + CSS Module + sous-composants + `index.ts`
- GSAP intégré (timeline d'entrée + ScrollTrigger si scroll)
- Responsive inclus dans le CSS Module
- Aucun placeholder, aucun TODO, aucun "ATTENDRE GO"

**Agent**
- `@VybeAgent` en mode Chat panel (pas @Maestro)

**Fichier**
- `prompts/02-5-composant-creatif.md`

## Étape 3 — Prompt 3 (Exécution Créative)

**Entrées**
- Cahier des charges
- Design system (Prompt 2)

**Sorties attendues**
- Blueprints (grid + feel + hook) avant code
- Composants atomiques / structure Next.js
- CSS “Swiss style” (clamp, grid areas, util container)
- Orchestration GSAP (intro, batch, parallax, magnetic CTA)

**Fichier**
- `prompts/03-execution-creative.md`

## Étape 4 — Prompt 4 (Copywriting)

**Entrées**
- Cahier des charges
- Sitemap (Prompt 1)

**Sorties attendues (par page)**
- Hero (H1, sous-titre, CTA)
- Sections (H2 + bénéfices)
- Preuve sociale
- CTAs secondaires
- SEO (meta title/description + alts)
- Footer (nav + mentions légales type)

**Fichier**
- `prompts/04-copywriting.md`

## Étape 5 — Prompt 5 (Modules complexes) — si besoin

**Entrées**
- Cahier des charges
- Architecture (Prompt 1)
- Description du module

**Sorties attendues**
- Architecture du composant (+ props TS)
- State management (idle/loading/success/error)
- Logique métier + validation + edge cases
- UX des états (loading/empty/error/success)
- Intégrations externes + variables d’env

**Fichier**
- `prompts/05-modules-complexes.md`

## Gate QA — Pré-livraison

> À valider **avant chaque push** sur `main` / mise en prod Netlify.

### Accessibilité & interactions
- [ ] Contraste texte ≥ 4.5:1 sur fond clair (WCAG AA) — vérifier avec [Colour Contrast Checker](https://colourcontrast.cc)
- [ ] `cursor-pointer` sur tous les éléments cliquables (boutons, liens, cards)
- [ ] Focus states visibles pour la navigation clavier (`:focus-visible` stylé)
- [ ] `prefers-reduced-motion` respecté — GSAP : `gsap.matchMedia()` ou `ScrollTrigger` désactivé
- [ ] Pas d'emoji utilisated comme icône — SVG uniquement (Heroicons / Lucide)

### Interactions visuelles
- [ ] Hover states sur tous les éléments interactifs avec transition 150-300ms
- [ ] État loading / error / empty géré sur les formulaires et modules async
- [ ] Animations GSAP non bloquantes (pas de timeline qui bloque le scroll)

### Responsive
- [ ] Testé à 375px (iPhone SE), 768px (tablette), 1024px, 1440px
- [ ] Aucun overflow horizontal
- [ ] Images avec `width`/`height` définis (pas de CLS)

### Code & performance
- [ ] Pas de `console.log` en production
- [ ] Fonts chargées avec `font-display: swap` (FOIT géré)
- [ ] Variables d'environnement dans Netlify, pas dans Git
- [ ] `npm run build` passe sans erreur en local avant push

## Git & livraison (standard)

### Convention minimale recommandée
- Branche principale : `main`
- Une branche par feature : `feat/...` / `fix/...`
- Messages de commit clairs (FR ok) :
  - `feat: ...`
  - `fix: ...`
  - `docs: ...`

### Déploiement Netlify (principe)
- Repo GitHub connecté à Netlify
- Build command typique : `npm run build`
- Publish directory (Next.js) : géré via l’intégration Next.js Netlify (adapter)
- Variables d’environnement : configurées dans Netlify (pas dans Git)

