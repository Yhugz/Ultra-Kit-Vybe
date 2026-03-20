# Prompt 5 — Modules complexes

## MISSION

Tu es un Senior Frontend Engineer spécialisé Next.js 14 / TypeScript.
Je dois développer un module fonctionnel avancé pour le projet suivant.

## CONTEXTE PROJET

[COLLER ICI LE CAHIER DES CHARGES CLIENT]
[COLLER ICI L'ARCHITECTURE GÉNÉRÉE AU PROMPT 1]

## MODULE À DÉVELOPPER

[DÉCRIRE LE MODULE — exemples ci-dessous]

Exemples de modules disponibles :
- Formulaire multi-étapes avec validation et progress bar
- Calculateur de prix dynamique en temps réel
- Système de filtres / recherche / pagination
- Intégration avis Google (widget ou API)
- Formulaire de contact avec envoi email (Resend / Nodemailer)
- Carte interactive (Google Maps / Mapbox)
- Galerie photos avec lightbox
- Menu de restaurant interactif avec catégories

## POUR CHAQUE MODULE, GÉNÈRE

1. ARCHITECTURE DU COMPOSANT
   - Structure des fichiers dans /components
   - Props TypeScript typées
   - Hooks custom nécessaires

2. STATE MANAGEMENT
   - Schéma des états (idle / loading / success / error)
   - useState / useReducer selon la complexité

3. LOGIQUE MÉTIER
   - Fonctions et handlers commentés en français
   - Validation des données
   - Gestion des cas limites

4. UX DES ÉTATS
   - État de chargement (skeleton ou spinner)
   - État vide (empty state)
   - État d'erreur (message utilisateur)
   - État de succès

5. INTÉGRATIONS EXTERNES
   - APIs tierces nécessaires
   - Variables d'environnement à configurer dans .env.local
   - Documentation des endpoints utilisés

## CONTRAINTES

- Zero dépendance inutile
- Accessible WCAG AA
- Compatible GSAP pour les transitions d'états
- Commentaires en français
- Mobile first

