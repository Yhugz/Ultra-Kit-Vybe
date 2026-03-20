# Kickoff projet — Checklist de démarrage

> À suivre **dans l'ordre** à chaque nouveau projet client.
> Temps estimé : 30 min avant d'ouvrir VS Code.

## Étape 1 — Collecter le brief (toi seul)

- [ ] Cahier des charges signé ou validé par écrit
- [ ] Contenus réels du client récupérés :
  - [ ] Logo (SVG si possible)
  - [ ] Carte / menu / flyer physique (photo ou scan)
  - [ ] Textes validés (ou brief pour rédaction)
  - [ ] Photos / visuels existants
  - [ ] Horaires, adresse, téléphone, email, réseaux sociaux
- [ ] Couleurs : vérifier la cohérence CDC ↔ identité réelle (carte, logo, lieu)
- [ ] Domaine réservé ou à acheter
- [ ] Objectifs priorisés (visibilité, conversion, saisonnier ?)

## Étape 2 — Préparer le contexte (toi seul)

- [ ] Convertir le CDC PDF en texte (pour le coller dans les prompts)
- [ ] Scanner / photographier la carte / menu si format papier
- [ ] Créer un dossier `assets/` avec logo, photos, captures du site actuel
- [ ] Identifier les 2-3 composants "wow" du site (hero, section signature)
- [ ] Identifier les composants fonctionnels (nav, footer, form, FAQ, légales)

## Étape 3 — Architecture (@Stratege)

```
@Stratege
Voici le CDC du projet [CLIENT].
[COLLER LE CDC COMPLET]
Génère l'architecture complète : sitemap, routes, composants, types.
```

- [ ] Sitemap validé
- [ ] Arborescence `src/` définie
- [ ] Routes App Router listées
- [ ] Composants identifiés (Server vs Client)

## Étape 4 — Design system (@Stratege ou @VybeAgent)

```
@VybeAgent
Voici le CDC du projet [CLIENT].
[COLLER LE CDC + DESCRIPTION IDENTITÉ RÉELLE]
Génère le design system : tokens.css, typography.css, spacing.css, components.css.
Couleurs RÉELLES du client : [DÉCRIRE ce que tu vois sur la carte/le logo].
```

- [ ] `styles/tokens.css` généré
- [ ] Palette vérifiée contre l'identité réelle (pas juste les HEX du CDC)
- [ ] Contrastes WCAG AA validés
- [ ] Typo pairing défini

## Étape 5 — Composants créatifs (@VybeAgent, chat panel)

Pour chaque composant visuel identifié à l'étape 2 :

```
@VybeAgent
[ATTACHER : #file CDC.txt, #file carte.jpg, #file tokens.css]

Crée le composant [Hero / Section About / Galerie] pour [CLIENT].
Direction créative : [2-3 phrases décrivant l'effet voulu]
Contenus réels : [textes, plats, horaires, etc.]
```

- [ ] Hero produit en single-shot
- [ ] Sections signature produites
- [ ] Fichiers copiés dans `components/`
- [ ] Itérations fines en Copilot inline

## Étape 6 — Composants fonctionnels (@Maestro)

```
@Maestro
Implémente les composants fonctionnels du projet [CLIENT] :
- Navigation (desktop + burger mobile)
- Footer (liens, contact, légales)
- [Formulaire de contact / FAQ / Carte Google Maps / ...]
Architecture : [LIEN vers le plan ou résumé]
```

- [ ] Nav implémentée + responsive
- [ ] Footer implémenté
- [ ] Formulaire fonctionnel (si applicable)
- [ ] FAQ avec accordéon (si applicable)

## Étape 7 — Copywriting (@VybeAgent)

```
@VybeAgent
Rédige le copy SEO pour toutes les pages du site [CLIENT].
Sitemap : [COLLER]
Cible : [EXTRAIRE DU CDC]
Ton : [premium / chaleureux / corporate]
Zone : [ville / région]
```

- [ ] H1 + sous-titre + CTA par page
- [ ] Meta title + description par page
- [ ] Alt text images
- [ ] FAQ orientée intentions de recherche

## Étape 8 — QA (toi + @VybeAgent)

- [ ] Ouvrir `TODO.md` et suivre chaque section
- [ ] `npm run build` — 0 erreur
- [ ] Lighthouse ≥ 90 sur les 4 métriques
- [ ] Test mobile 375px + tablette 768px
- [ ] Tous les liens fonctionnels (tel:, mailto:, ancres)
- [ ] RGPD / cookie consent

## Étape 9 — Deploy

- [ ] Variables d'environnement configurées sur Vercel/Netlify
- [ ] DNS configuré
- [ ] HTTPS actif
- [ ] Sitemap soumis dans Search Console
- [ ] Fiche Google Business mise à jour
