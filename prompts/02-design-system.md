# Prompt 2 — Design system

Tu es un Design Director senior. Je t'envoie le cahier des charges d'un client.  
Génère le design system complet pour ce projet Next.js 14.

CAHIER DES CHARGES CLIENT  
[COLLER LE PDF ICI — ou les infos clés]

---

> **Si le client n'a pas de charte graphique** (pas de couleurs ni de typos définies), coller ici le contenu du fichier `design-system/MASTER.md` généré par UUPM (voir Étape 0 du WORKFLOW.md). Ce fichier contient : palette recommandée par secteur, font pairing justifié, pattern de landing et anti-patterns à éviter.

RÉFÉRENCE SECTORIELLE UUPM *(si disponible — supprimer sinon)*  
[COLLER ICI LE CONTENU DE design-system/MASTER.md]

---

Génère les fichiers suivants :

1. /styles/tokens.css
   - Toutes les couleurs en CSS variables (primary, secondary, neutral, semantic)
   - Version dark mode si pertinent
   - Couleurs d'état : success, error, warning

2. /styles/typography.css
   - Échelle typographique complète (h1 → h6, body, caption, label)
   - Font pairing justifié selon la personnalité de la marque
   - Line-height, letter-spacing, font-weight pour chaque niveau

3. /styles/spacing.css
   - Grille basée sur 8px
   - Tokens de spacing : xs, sm, md, lg, xl, 2xl, 3xl
   - Breakpoints responsive : mobile, tablet, desktop

4. /styles/components.css
   - Styles de base pour : boutons (primary, secondary, ghost),
     cards, inputs, badges, tags

5. MOTION PRINCIPLES (commentaires dans le code)
   - Durées : fast (150ms), normal (300ms), slow (600ms)
   - Courbes GSAP recommandées selon le style de la marque
   - Philosophie d'animation en 2-3 lignes

Contraintes :
- Compatible Next.js 14 App Router
- Accessible WCAG AA (contrastes validés)
- Commentaires en français
- Zéro dépendance externe sauf GSAP

6. ANTI-PATTERNS À ÉVITER (selon secteur)
   - Liste explicitement 5 à 8 choix visuels à proscrire pour ce type de projet
   - Exemples : gradients IA violet/rose pour une banque, dark mode brutal pour un médecin,
     emojis comme icônes, fond blanc pur pour un SaaS, animations > 600ms sans réduction de mouvement
   - Justifie chaque anti-pattern en une ligne

7. RÉFÉRENCE PALETTES & FONT PAIRINGS (si client sans charte)
   - Si aucune couleur n'est fournie : proposer 3 palettes candidates (primaire, secondaire, neutre, sémantique)
     avec justification sectorielle
   - Si aucune typo n'est fournie : proposer 2 font pairings Google Fonts adaptés à la personnalité de marque,
     avec import prêt à coller

