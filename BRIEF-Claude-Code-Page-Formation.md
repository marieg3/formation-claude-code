# Brief technique — Page HTML de formation
## Formation : Claude Code — La Fusée
> Document à fournir tel quel à Claude Code pour générer la page HTML complète de la formation.

---

## 🎯 Objectif

Créer un fichier `index.html` unique (tout-en-un : HTML + CSS + JS) qui remplace les slides de formation. La page est utilisée **par le formateur ET par chaque participant** sur son propre ordinateur pendant la formation en virtuel. Elle doit être claire, lisible sur écran, navigable entre les modules, et permettre aux participants de cocher les étapes des ateliers.

---

## 📁 Structure de fichiers attendue

```
formation-claude-code/
├── index.html          ← fichier principal (tout intégré)
└── assets/
    └── logo-la-fusee.png   ← logo fourni séparément
```

---

## 🎨 Charte graphique — La Fusée

### Couleurs
| Nom | Hex | Usage |
|---|---|---|
| Violet principal | `#742cff` | Titres, boutons principaux, accents forts, éléments actifs |
| Violet moyen | `#ab80ff` | Hover, badges, éléments secondaires |
| Violet clair | `#e3d5ff` | Fonds de cartes, highlights, séparateurs |
| Blanc cassé / fond général | `#f5f5f5` | Fond de page (pas blanc pur — confort visuel sur écran) |
| Blanc pur | `#ffffff` | Fond des cartes et contenus sur fond gris |
| Noir | `#000000` | Texte courant sur fond clair |

> ⚠️ Le fond général de la page est `#f5f5f5` (blanc cassé légèrement gris), pas blanc pur. Les formations sont suivies en virtuel sur écran — éviter la fatigue visuelle.

### Typographie
- **Police unique : Poppins** (Google Fonts)
- Import à inclure : `<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">`
- H1 : Poppins 700, 28–32px
- H2 : Poppins 700, 20–24px
- H3 : Poppins 700, 16–18px
- Texte courant : Poppins 400, 15px
- Labels/badges : Poppins 400, 12–13px

### Composants UI
- **Boutons principaux** : fond `#742cff`, texte blanc, `border-radius: 4px`
- **Boutons secondaires** : fond `#ab80ff`, texte blanc, `border-radius: 4px`
- **Cartes** : fond blanc `#ffffff`, `border-radius: 8px`, ombre légère `box-shadow: 0 2px 8px rgba(0,0,0,0.07)`
- **Badges / durée** : fond `#e3d5ff`, texte `#742cff`, `border-radius: 4px`, padding `4px 10px`
- **Séparateurs** : couleur `#e3d5ff`, jamais de bordures grises épaisses
- **Cases à cocher (ateliers)** : custom styled, violet `#742cff` au coche, coins arrondis `4px`
- **Logo** : fichier `assets/logo-la-fusee.png`, placé en haut à gauche, hauteur max 48px, espacement 16px

---

## 🗂️ Architecture de navigation

La page est organisée en **sections** (pas de rechargement de page). Navigation par menu fixe en haut ou sidebar.

### Sections à créer (dans l'ordre) :

1. **Accueil** — Hero de la formation
2. **Vue d'ensemble** — 4 modules en un coup d'œil
3. **Module 1** — Comprendre Claude Code
4. **Module 2** — Donner une mission à Claude Code
5. **Module 3** — Créer un outil intelligent
6. **Module 4** — Confiance & autonomie
7. **Ressources** — Documentation et liens utiles

Navigation : boutons ou onglets permettant de passer d'une section à l'autre. La section active est mise en évidence (`#742cff`). Les autres sections sont masquées (`display: none`), affichées au clic.

---

## 📄 Contenu détaillé par section

---

### SECTION 1 — Accueil (Hero)

**Éléments à afficher :**
- Logo La Fusée (`assets/logo-la-fusee.png`) en haut à gauche
- Titre principal : `Formation : Claude Code`
- Sous-titre accrocheur : `De l'intention à l'exécution — sans écrire une seule ligne de code.`
- Trois badges informatifs en ligne :
  - 🎓 Niveau : Débutant
  - ⏱️ Durée : 6 heures
  - 💻 Format : Virtuel
- Texte d'introduction (court, en carte) :
  > *Vous n'avez pas besoin de savoir coder. Claude Code est un agent IA qui lit vos fichiers, écrit du code, l'exécute et se corrige lui-même. Il vous suffit de lui donner des instructions en Français. Cette formation vous donne les clés pour devenir le chef de projet d'un développeur IA qui ne dort jamais.*
- Bouton CTA : `Commencer la formation →` (violet principal, amène à la section Vue d'ensemble)

---

### SECTION 2 — Vue d'ensemble

**Titre de section :** `🗺️ Vue d'ensemble des modules`

**4 cartes modules côte à côte (ou en grille 2×2 sur petit écran) :**

| Module | Titre | Description courte | Durée |
|---|---|---|---|
| Module 1 | Comprendre Claude Code | Démystifier le terminal, le vibe coding et l'environnement agentique. Poser les bases sans jargon. | 1h15 |
| Module 2 | Donner une mission à Claude Code | Transformer une tâche métier réelle en prompt structuré. Générer, valider, exécuter. | 1h30 |
| Module 3 | Créer un outil intelligent | Construire un mini-système reproductible : skills, mémoire, sous-agents. Du prototype au livrable. | 1h15 |
| Module 4 | Confiance & autonomie | Corriger sans paniquer, bâtir sa routine Claude Code, repartir avec une vraie victoire personnelle. | 1h15 |

Chaque carte est cliquable et amène à la section du module correspondant.

---

### SECTION 3 — Module 1

**En-tête de module :**
- Badge : `Module 1` (violet principal)
- Badge durée : `1h15`
- Titre : `Comprendre Claude Code et démystifier`
- Objectif pédagogique (encadré violet clair) :
  > Retirer la peur technique, comprendre le principe du vibe coding et poser le cadre d'utilisation de Claude Code. Repartir avec une première victoire concrète.

**Contenu (liste à puces) :**
- Chatbot vs LLM vs Agent IA : quelle est vraiment la différence ?
- Ce que fait Claude Code en coulisses (lecture de fichiers, écriture de code, exécution, boucle de correction)
- Terminal vs interface web : quand utiliser l'un ou l'autre
- Le fichier CLAUDE.md : donner une mémoire de contexte permanente à votre agent
- Pourquoi Claude Code et pas Copilot, Cursor ou ChatGPT ?
- Ce que vous n'avez PAS besoin de comprendre pour être efficace
- Le vibe coding en pratique : décrire → générer → exécuter → corriger
- Démonstration spectaculaire en direct
- Démystification du terminal (version ultra simple)

**Atelier 1 — Première expérience de vibe coding** (carte distincte, fond violet clair) :

Titre : `🧩 Atelier 1 — Première expérience de vibe coding`

Texte d'intro :
> Les participants installent Claude Code, ouvrent leur terminal pour la première fois et lui confient une tâche réelle sur un dossier fourni (10–15 fichiers variés).

Cases à cocher (checkboxes interactives) :
- [ ] Installer Claude Code sur mon ordinateur
- [ ] Ouvrir le terminal pour la première fois
- [ ] Demander un résumé structuré du dossier fourni
- [ ] Renommer des fichiers avec Claude Code
- [ ] Générer un fichier de synthèse
- [ ] Vivre ma première exécution réussie ✨

---

### SECTION 4 — Module 2

**En-tête de module :**
- Badge : `Module 2` | Badge durée : `1h30`
- Titre : `Donner une mission à Claude Code`
- Objectif (encadré violet clair) :
  > Apprendre à transformer n'importe quelle tâche répétitive en mission agentique claire et exécutable. Structurer un prompt qui produit un résultat fiable.

**Contenu (liste à puces) :**
- Identifier une tâche répétitive à fort potentiel d'automatisation
- Les 5 éléments d'un prompt agentique solide : contexte, fichiers concernés, résultat attendu, critères de succès, format de sortie
- Demander un plan avant d'exécuter — pourquoi c'est crucial
- Valider le plan, lancer l'exécution, vérifier le résultat
- Introduction aux skills : créer un module d'expertise réutilisable (ex. : « toujours formater les rapports ainsi »)
- Introduction à la mémoire persistante : comment Claude Code retient le contexte d'un projet entre les sessions

**Encart spécial — Template prompt agentique** (carte avec fond violet clair, police monospace) :
```
Contexte : [qui vous êtes, quel est le projet]
Fichiers concernés : [chemin ou description des fichiers]
Résultat attendu : [ce que vous voulez obtenir]
Critères de succès : [comment savoir que c'est réussi]
Format de sortie : [fichier, tableau, rapport, etc.]
```

**Atelier 2** (carte distincte, fond violet clair) :

Titre : `🧩 Atelier 2 — De la tâche au script agentique`

Cases à cocher :
- [ ] Identifier ma tâche répétitive à automatiser
- [ ] Rédiger mon prompt avec le template (contexte + fichiers + résultat + critères)
- [ ] Demander un plan à Claude Code avant d'exécuter
- [ ] Valider le plan proposé
- [ ] Lancer l'exécution et vérifier le résultat

**Exemples par profil** (2 colonnes, cartes compactes) :

*Marketing :*
- Nettoyage d'un export CRM en CSV
- Génération d'un rapport mensuel automatisé
- Reformatage d'une liste de leads

*Gestion :*
- Classement automatique de fichiers par type et date
- Résumé de 20 comptes rendus de réunion
- Génération d'un rapport PDF synthétique

---

### SECTION 5 — Module 3

**En-tête de module :**
- Badge : `Module 3` | Badge durée : `1h15`
- Titre : `Créer un outil intelligent avec Claude Code`
- Objectif (encadré violet clair) :
  > Aller plus loin que le script ponctuel : construire un mini-système reproductible, avec une logique métier, des skills personnalisés et une structure qui tient dans le temps.

**Contenu (liste à puces) :**
- Clarifier le livrable avant de coder : qu'est-ce qu'un "outil" vs un "script" ?
- Construire un CLAUDE.md de projet : définir les règles, le contexte, les contraintes permanentes
- Créer des skills personnalisés : enseigner à Claude Code vos conventions, formats et standards métier
- Introduction aux sous-agents (sub-agents) : déléguer des tâches en parallèle pour aller plus vite
- Demander un plan détaillé, générer par étapes, tester à chaque étape
- Stabiliser l'outil : le rendre robuste et utilisable par d'autres

**Exemples d'outils construits en atelier** (grille de 4 cartes compactes) :
- 📊 Agent d'analyse automatique d'un dossier de rapports (résumé + scoring)
- 🔄 Outil de transformation massive de fichiers CSV avec règles métier personnalisées
- 🗂️ Système de classement et renommage automatique de documents avec mémoire
- 🔔 Mini-agent de veille : surveille un dossier et génère une alerte synthétique

**Atelier 3** (carte distincte, fond violet clair) :

Titre : `🧩 Atelier 3 — Construire son premier outil local`

Cases à cocher :
- [ ] Définir ma problématique : quel outil je veux construire ?
- [ ] Créer mon fichier CLAUDE.md de projet
- [ ] Définir la logique métier de l'outil
- [ ] Créer un skill personnalisé réutilisable
- [ ] Tester l'outil et vérifier le résultat
- [ ] Stabiliser : l'outil peut être réutilisé demain ✅

---

### SECTION 6 — Module 4

**En-tête de module :**
- Badge : `Module 4` | Badge durée : `1h15`
- Titre : `Confiance & autonomie`
- Objectif (encadré violet clair) :
  > Repartir avec une vraie victoire personnelle et la confiance de continuer seul. Ce module n'est pas technique — il est humain.

**La boucle de correction** (composant visuel horizontal, 5 étapes) :

```
✏️ Générer  →  🧪 Tester  →  🔍 Lire l'erreur  →  🔧 Corriger  →  ✅ Retester
```
Chaque étape dans une carte compacte reliée par une flèche. Fond alterné blanc / violet clair.

**Contenu (liste à puces) :**
- Pourquoi l'erreur est normale — et même utile — dans un workflow agentique
- Lire un message d'erreur sans paniquer : les 3 informations clés à repérer
- Forcer Claude Code à s'auto-corriger : les prompts de débogage qui marchent
- Les 3 réflexes pour ne pas se bloquer seul (reformuler, simplifier, demander un plan)
- Mettre à jour son CLAUDE.md : documenter ce qu'on a appris pour que Claude s'en souvienne
- Construire sa routine Claude Code : intégrer l'agent dans sa semaine de travail

**Atelier final — Ma victoire personnelle** (carte principale, mise en valeur) :

Titre : `🧩 Atelier final — Ma victoire personnelle`

Intro : *Choisir une micro-victoire concrète à compléter avant la fin de la journée.*

4 cartes de défi (sélectionnable visuellement, fond violet clair au clic) :
| Défi | Ce que vous repartez avec |
|---|---|
| ✉️ Créer une signature de courriel HTML personnalisée | Un fichier HTML prêt à coller dans Outlook ou Gmail |
| 🤖 Créer un agent pour une tâche récurrente personnelle | Un script qui tourne chaque semaine sans intervention |
| 📝 Rédiger et enrichir son CLAUDE.md personnel | Un fichier de contexte qui rend Claude Code plus intelligent à chaque session |
| 📊 Améliorer l'outil construit en Module 2 ou 3 | Une version améliorée, plus robuste, prête à réutiliser |

**Clôture** (carte finale, fond violet principal, texte blanc) :
> 🎉 Tour de table des victoires — Chaque participant partage en 60 secondes : ce qu'il a créé, ce que ça lui permettra de faire différemment.

---

### SECTION 7 — Ressources

**Titre :** `📚 Ressources pour aller plus loin`

**3 groupes de liens (cartes) :**

*Documentation officielle :*
- [docs.anthropic.com](https://docs.anthropic.com) — Documentation Claude Code (installation, commandes, CLAUDE.md)
- [claude.ai/code](https://claude.ai/code) — Interface web Claude Code pour démarrer sans terminal

*Pour progresser :*
- Formation niveau 2 : Orchestration multi-agents & sub-agents (La Fusée — à venir)
- Communauté Claude Code sur Reddit : r/ClaudeAI
- Chaîne YouTube Anthropic — démos et tutoriels officiels

*Outils complémentaires :*
- LearnUpon — Guide d'installation Claude Code + ressources La Fusée
- GitHub — Pour versionner ses scripts et outils Claude Code
- Make.com — Pour connecter ses agents Claude Code à ses outils métier (Slack, HubSpot, Google Sheets…)

---

## ⚙️ Comportements JavaScript requis

### Navigation entre sections
```javascript
// Au clic sur un item de navigation :
// 1. Masquer toutes les sections (display: none)
// 2. Afficher la section cible (display: block)
// 3. Mettre à jour l'état actif du menu (classe CSS "active")
// 4. Scroll to top de la section
```

### Cases à cocher (ateliers)
```javascript
// Chaque checkbox :
// - Au coche : fond violet #742cff, coche blanche visible, label barré (text-decoration: line-through, opacité réduite)
// - Au décoche : retour à l'état initial
// - Compteur de progression : "X / N étapes complétées" par atelier (mise à jour dynamique)
// - État persisté dans localStorage par atelier (clé : "module-X-checks")
```

### Cartes de défi (Module 4)
```javascript
// Au clic sur une carte de défi :
// - Ajouter classe "selected" : bordure violette épaisse, fond violet clair
// - Une seule carte sélectionnable à la fois
```

---

Dans contenu-formation-claude-code.html, modifie la navigation de la façon suivante :

1. À l'intérieur de chaque module, chaque sujet devient un écran 
   séparé (pas de scroll continu). Un seul sujet visible à la fois.

2. Ajoute des flèches gauche / droite pour naviguer entre les sujets 
   du module actif. La flèche droite sur le dernier sujet amène 
   au module suivant.

3. Ajoute une barre de progression sous le header :
   - Hauteur 4px, couleur #742cff
   - Se remplit proportionnellement selon le sujet en cours
     (ex. sujet 3/9 = 33% de la barre remplie)
   - Pas de texte ni chiffres, juste la barre visuelle

Ne touche pas au menu de navigation principal ni au CSS global.


---

## 📐 Layout général

```
┌─────────────────────────────────────────┐
│  Logo La Fusée    [Nav: M1 M2 M3 M4 …]  │  ← Header fixe
├─────────────────────────────────────────┤
│                                         │
│           Contenu de la section         │  ← Zone scrollable
│           active (1 section à la fois)  │
│                                         │
└─────────────────────────────────────────┘
```

- **Header fixe** en haut : logo à gauche, navigation à droite (ou centrée)
- **Max-width** du contenu : `860px`, centré avec `margin: 0 auto`
- **Padding** général : `24px` sur les côtés
- **Espacement entre blocs** : `32px`
- Responsive : sur mobile (< 768px), la navigation devient un menu déroulant ou passe en 2 lignes

---

## ✅ Checklist de validation avant livraison

- [ ] Page fonctionne en ouvrant `index.html` directement dans un navigateur (pas de serveur requis)
- [ ] Logo chargé depuis `assets/logo-la-fusee.png`
- [ ] Navigation entre les 7 sections fonctionne sans rechargement
- [ ] Toutes les cases à cocher des ateliers sont fonctionnelles
- [ ] Compteurs de progression s'affichent et se mettent à jour
- [ ] État des cases persisté dans localStorage
- [ ] Police Poppins chargée (via Google Fonts)
- [ ] Couleurs conformes à la charte (#742cff, #ab80ff, #e3d5ff, #f5f5f5)
- [ ] Fond général #f5f5f5 (pas blanc pur)
- [ ] Responsive mobile basique
- [ ] Aucune dépendance externe sauf Google Fonts (pas de framework JS)
