# Module 1 — Comprendre Claude Code et démystifier
**Durée estimée : 1h15**

> Objectif : Retirer la peur technique, comprendre le principe du vibe coding et poser le cadre d'utilisation de Claude Code. Repartir avec une première victoire concrète.

---

## Chatbot, LLM, Agent IA : quelle différence ?

| | Chatbot | LLM | Agent IA |
|---|---|---|---|
| **Ce que c'est** | Programme à réponses prédéfinies | Modèle qui génère du texte | IA qui agit et exécute |
| **Exemple** | ChatGPT, Claude.ai, Gemini, Copilot | GPT-5, Claude Sonnet 4.6, Gemini 3.1 Pro | Claude Code |
| **Ce qu'il fait** | Répond à des questions | Génère, explique, rédige | Lit vos fichiers, écrit du code, l'exécute, se corrige |
| **Vous devez** | Choisir parmi des options | Rédiger un prompt | Donner une mission |

> 💡 **Claude Code n'est pas un chatbot.** C'est un agent : il prend une mission, la décompose, agit sur vos fichiers, et se corrige seul jusqu'au résultat.

---

## Ce que fait Claude Code en coulisses

<!-- VISUEL : undraw_add-files_s0fz.svg — à droite du schéma -->

Quand vous lui donnez une mission, Claude Code exécute une boucle en 4 étapes :

```
📂 Lire        →      ✍️ Écrire       →      ▶️ Exécuter      →      🔧 Corriger
vos fichiers        du code                  le code                 si erreur
```

> 💡 **Vous ne voyez pas le code.** Vous voyez le résultat. C'est ça, le vibe coding — vous décrivez ce que vous voulez, Claude Code s'occupe du reste.

**Ce que ça veut dire concrètement :**
- Il peut lire 50 fichiers Word et en faire un résumé en 2 minutes
- Il écrit le script, l'exécute, voit l'erreur, se corrige — sans vous demander de comprendre
- Il recommence jusqu'à ce que le résultat corresponde à votre demande

<!-- VISUEL : capture d'écran terminal — assets-claude-code/screen-terminal-execution.png -->

---

## Terminal vs interface web : quand utiliser l'un ou l'autre ?

| | Terminal | Interface web |
|---|---|---|
| **Accès** | `claude` dans votre terminal | claude.ai/code dans le navigateur |
| **Idéal pour** | Travailler sur vos fichiers locaux | Tester, explorer, poser des questions |
| **Peut lire vos fichiers** | ✅ Oui | ❌ Non |
| **Peut exécuter du code** | ✅ Oui | ❌ Non |
| **Sans installation** | ❌ Requiert une installation | ✅ Oui |

> 💡 **Règle simple :** Si vous voulez qu'il agisse sur vos fichiers, utilisez le terminal. Si vous voulez juste lui parler, l'interface web suffit.

---

## Le fichier CLAUDE.md : la mémoire permanente de votre agent

> Par défaut, Claude Code oublie tout entre deux sessions. Le fichier CLAUDE.md règle ce problème.

**C'est quoi ?**
Un simple fichier texte que vous placez à la racine de votre projet. Claude Code le lit automatiquement à chaque session — c'est son briefing permanent.

**Ce que vous y mettez :**
- Qui vous êtes et quel est le projet
- Vos conventions et préférences (langue, format des fichiers, structure des rapports)
- Les règles à toujours respecter
- Ce que vous avez appris et ne voulez plus réexpliquer

<!-- VISUEL : capture d'écran fichier CLAUDE.md ouvert dans VS Code — assets-claude-code/exemple-interface-fichier-claude.png -->

> 💡 **Plus votre CLAUDE.md est précis, moins vous réexpliquez.** C'est un investissement de 10 minutes qui vous fait gagner des heures.

> ✨ **Pro tip :** Vous pouvez même vous aider de l'agent conversationnel Claude.ai pour créer votre fichier de brief CLAUDE.md

---

## Pourquoi Claude Code et pas Lovable, Bolt ou Replit ?

| | Lovable / Bolt | Replit | Claude Code |
|---|---|---|---|
| **Conçu pour** | Créer des apps web | Créer des apps web | Automatiser vos tâches métier |
| **Travaille sur vos fichiers existants** | ❌ Non | ❌ Non | ✅ Oui |
| **Sans installation** | ✅ Oui | ✅ Oui | ❌ Terminal requis |
| **Ce qu'il produit** | Une application web | Une application web | Un résultat sur vos fichiers |
| **Sans savoir coder** | ✅ Oui | Partiel | ✅ Oui |

> 💡 **Lovable et Bolt créent des apps à partir de zéro.** Claude Code transforme ce que vous avez déjà.

---

## Ce que vous n'avez PAS besoin de comprendre pour être efficace

<!-- VISUEL : undraw_bright-ideas_z7u9.svg — à droite du tableau -->

| ❌ Pas nécessaire | ✅ Ce qui compte vraiment |
|---|---|
| Les langages de programmation | Décrire clairement ce que vous voulez |
| Comment fonctionne le code généré | Vérifier que le résultat correspond à votre demande |
| Les messages d'erreur techniques | Savoir les copier-coller à Claude Code |
| L'architecture des fichiers | Organiser vos fichiers avant de commencer |
| Les commandes terminal avancées | 3 commandes suffisent : `cd`, `ls`, `claude` |

> 💡 **Votre rôle c'est de piloter, pas de conduire.** Vous définissez la destination et les critères de succès — Claude Code trouve le chemin.

---

## Le vibe coding en pratique : décrire → générer → exécuter → corriger

```
📝 Décrire          ⚙️ Générer          ▶️ Exécuter          🔧 Corriger
"Je veux un        Claude Code         Claude Code          Si ce n'est pas
résumé de         écrit le code        lance le code        parfait, vous
mes 20 CR         pour le faire        automatiquement      dites ce qui
de réunion"                                                 cloche
```

**Ce que ça ressemble en vrai :**

> *"Dans le dossier /reunions, lis tous les fichiers Word et génère un fichier resume.md qui liste pour chaque réunion : la date, les décisions prises et les actions à faire."*

C'est tout. Pas de code. Pas de terminal complexe. Une phrase claire.

**Les 3 réflexes à avoir :**
- Donner un exemple du résultat attendu quand c'est possible
- Demander un plan avant d'exécuter sur des tâches importantes
- Vérifier le résultat avant de dire "parfait"

---

## Démonstration en direct

**Ce que vous allez observer :**
- Ouvrir le terminal et lancer Claude Code
- Donner une mission en français, en une phrase
- Claude Code lit les fichiers, écrit le code, l'exécute
- Le résultat apparaît en moins de 2 minutes

> 👀 **À noter :** pas une seule ligne de code tapée. Juste une description — Claude Code exécute.

---

## Démystification du terminal — 3 commandes, c'est tout

```bash
cd nom-du-dossier     # Se déplacer dans un dossier
ls                    # Voir ce qu'il y a dans le dossier
claude                # Lancer Claude Code
```

> 💡 C'est tout ce dont vous avez besoin pour cette formation.

---

## 🧩 Atelier 1 — Première expérience de vibe coding

Les participants installent Claude Code, ouvrent leur terminal pour la première fois et lui confient une tâche réelle sur un dossier fourni (10–15 fichiers variés).

**Objectif :** vivre la magie de la première exécution réussie.

Cases à cocher :
- [ ] Installer Claude Code sur mon ordinateur
- [ ] Ouvrir le terminal pour la première fois
- [ ] Demander un résumé structuré du dossier fourni
- [ ] Renommer des fichiers avec Claude Code
- [ ] Générer un fichier de synthèse
- [ ] Vivre ma première exécution réussie ✨
