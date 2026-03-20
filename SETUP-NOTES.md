# Notes d'assemblage

Ce repo est la fusion de tes deux repos existants.
Voici les fichiers à copier depuis tes repos actuels :

## Depuis Vybe Workflow Kit
- `prompts/01-architecture.md` → `prompts/01-architecture.md`
- `prompts/02-design-system.md` → `prompts/02-design-system.md`
- `prompts/03-execution-creative.md` → `prompts/03-execution-creative.md` (ajouter le warning en haut)
- `prompts/04-copywriting.md` → `prompts/04-copywriting.md`
- `prompts/05-modules-complexes.md` → `prompts/05-modules-complexes.md`
- `workflow/WORKFLOW.md` → `workflow/WORKFLOW.md` (ajouter l'étape 2.5)
- `workflow/CAHIER_DES_CHARGES_TEMPLATE.md` → `workflow/CAHIER_DES_CHARGES_TEMPLATE.md`
- `.github/ISSUE_TEMPLATE/*` → `.github/ISSUE_TEMPLATE/*`
- `TODO.md` → `TODO.md`

## Depuis Vybe Crew
- `Maestro.agent.md` → `.vscode/prompts/Maestro.agent.md`
- `Stratege.agent.md` → `.vscode/prompts/Stratege.agent.md`
- `Analyste-subagent.agent.md` → `.vscode/prompts/Analyste-subagent.agent.md`
- `Developpeur-subagent.agent.md` → `.vscode/prompts/Developpeur-subagent.agent.md`
- `Explorateur-subagent.agent.md` → `.vscode/prompts/Explorateur-subagent.agent.md`
- `FrontDesigner-subagent.agent.md` → `.vscode/prompts/FrontDesigner-subagent.agent.md`
- `Reviewer-subagent.agent.md` → `.vscode/prompts/Reviewer-subagent.agent.md`

## Nouveau (déjà inclus dans ce repo)
- `VybeAgent.agent.md` → `.vscode/prompts/VybeAgent.agent.md` ✅
- `prompts/02-5-composant-creatif.md` ✅
- `KICKOFF.md` ✅
- `docs/DECISION-GUIDE.md` ✅
- `docs/CONVENTIONS.md` ✅
- `.env.example` ✅

## Modification à faire dans les fichiers copiés

### workflow/WORKFLOW.md
Ajouter l'étape 2.5 entre l'étape 2 et 3 (voir modifications-workflow-vybe.md)

### prompts/03-execution-creative.md
Ajouter en haut :
> ⚠️ Ce prompt est pour la structure globale. Pour les composants visuels
> à fort impact, utiliser le Prompt 2.5 (single-shot).

### Maestro.agent.md
Ajouter la note sur les composants créatifs (voir modifications-workflow-vybe.md)
