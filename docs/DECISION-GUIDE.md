# Guide de décision — Quel agent, quel mode

> Référence rapide. En cas de doute : si c'est visuel → créatif. Si c'est logique → pipeline.

## La question à se poser

**"Est-ce que l'animation, le design et le contenu sont indissociables dans ce composant ?"**

- **OUI** → Mode créatif (@VybeAgent, chat panel, tout le contexte d'un coup)
- **NON** → Mode structuré (@Maestro pipeline ou @VybeAgent itératif)

## Tableau de référence

### Mode créatif (single-shot)

| Composant | Pourquoi créatif | Contexte à attacher |
|---|---|---|
| Hero section | Animation + typo + contenu = indissociables | CDC, carte, tokens.css, direction créative |
| Section "À propos" cinématique | Parallax + photos + storytelling | CDC, photos, tokens.css |
| Galerie immersive | Layout + animation + images = un tout | CDC, photos, tokens.css |
| Section signature du client | Identité forte, effet wow | CDC, carte, assets client |
| Landing page complète | Vision globale nécessaire | CDC complet, tous les contenus |

### Mode structuré (pipeline)

| Composant | Pourquoi structuré | Agent |
|---|---|---|
| Navigation desktop + mobile | Logique (responsive, états, burger) | @Maestro → FrontDesigner |
| Footer | Structure, liens, pas d'émotion | @Maestro → Developpeur |
| Formulaire de contact | Validation, envoi, états loading/error | @Maestro → Developpeur |
| FAQ accordéon | Logique JS, accessibilité | @Maestro → Developpeur |
| Pages légales | Contenu statique, SEO | @VybeAgent (structuré) |
| Carte Google Maps | Intégration API, pas de design | @Maestro → Developpeur |
| Système de filtres | State management, logique | @Maestro → Developpeur |
| Cookie consent RGPD | Logique, conformité | @Maestro → Developpeur |

### Autres tâches

| Tâche | Agent | Mode |
|---|---|---|
| Architecture initiale | @Stratege | Chat panel |
| Design system / tokens | @Stratege ou @VybeAgent | Chat panel |
| Copywriting SEO | @VybeAgent | Chat panel |
| Debug rapide | Copilot natif | Inline |
| Refacto / cleanup | Copilot natif ou @Developpeur | Inline / Chat |
| QA checklist | @VybeAgent + TODO.md | Chat panel |
| Exploration codebase | @Explorateur | Chat panel |

## Modes Copilot

| Mode | Quand | Pourquoi |
|---|---|---|
| **Chat panel** (volet latéral) | Prompts longs, gros contexte, composants complets | Contexte max, vision globale, fichiers attachables |
| **Inline / Edit** (Ctrl+I) | Modifier 5-20 lignes dans un fichier ouvert | Précis, rapide, contexte du fichier |
| **Autocomplete** (Tab) | Écrire du code ligne par ligne | Flow naturel, suggestions contextuelles |

## Erreurs à ne pas reproduire

1. **Ne pas itérer 50 fois sur un composant visuel** → Un prompt riche, un seul tir
2. **Ne pas oublier les couleurs réelles** → Toujours vérifier carte/logo/lieu avant CDC
3. **Ne pas fragmenter le créatif en étapes** → Pas de "ATTENDRE GO" sur un hero
4. **Ne pas utiliser Maestro pour un hero** → Le pipeline TDD tue la vision créative
5. **Ne pas résumer le CDC** → Coller le texte complet, pas un condensé
