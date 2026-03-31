# Module 2 — Donner une mission à Claude Code
**Durée estimée : 1h30**

> Objectif : Apprendre à transformer n'importe quelle tâche répétitive en mission agentique claire et exécutable. Structurer un prompt qui produit un résultat fiable.

---

## Quelle tâche confier à Claude Code ?

<!-- VISUEL : undraw_random-thoughts_spw5.svg — à droite du tableau -->

Pas toutes les tâches sont bonnes candidates. Voici comment repérer les bonnes :

| ✅ Bonne candidate | ❌ Mauvaise candidate |
|---|---|
| Vous la faites souvent (hebdo, mensuel) | Vous la faites une seule fois |
| Elle implique des fichiers ou des données | Elle nécessite un jugement humain complexe |
| Le résultat attendu est toujours le même | Le résultat varie selon le contexte |
| Elle vous ennuie ou vous prend trop de temps | Elle est courte et déjà simple |

**Les 3 questions à se poser :**
- Est-ce que je fais ça plus d'une fois par mois ?
- Est-ce que je pourrais l'expliquer en 3 phrases à quelqu'un ?
- Est-ce que le résultat ressemble toujours au même format ?

> 💡 **Si vous répondez oui aux 3 : c'est une tâche pour Claude Code.**

---

## Les 5 éléments d'un prompt agentique solide

> Un bon prompt agentique n'est pas une question — c'est une mission complète.

| # | Élément | Exemple concret |
|---|---|---|
| **1** | **Contexte** | "Je suis gestionnaire d'une équipe de 8 personnes" |
| **2** | **Fichiers concernés** | "Les fichiers sont dans le dossier /reunions" |
| **3** | **Résultat attendu** | "Génère un fichier resume.md par réunion" |
| **4** | **Critères de succès** | "Chaque résumé doit inclure : décisions, actions, responsables" |
| **5** | **Format de sortie** | "Un fichier par réunion, nommé AAAA-MM-JJ_resume.md" |

**Le template à réutiliser :**
```
Contexte : [qui tu es, quel est le projet]
Fichiers concernés : [chemin ou description]
Résultat attendu : [ce que vous voulez obtenir]
Critères de succès : [comment savoir que c'est réussi]
Format de sortie : [fichier, tableau, rapport, etc.]
```

> 💡 **Plus votre mission est précise, moins Claude Code improvise.** Un prompt flou donne un résultat flou.

---

## Demander un plan avant d'exécuter — pourquoi c'est crucial

<!-- VISUEL : undraw_warning_tl76.svg — à droite du bloc "Comment faire" -->

> Avant de lancer une tâche importante, demandez toujours un plan. C'est 30 secondes qui évitent des erreurs irréversibles.

**Comment faire :**
```
"Avant d'exécuter, décrivez-moi les étapes que vous allez suivre 
et les fichiers que vous allez modifier. Attendez ma confirmation 
avant de commencer."
```

**Ce que ça vous permet :**
- Repérer une incompréhension avant qu'elle devienne un problème
- Valider que Claude Code a bien compris votre intention
- Modifier le plan si une étape ne vous convient pas
- Garder le contrôle sur ce qui touche à vos fichiers

| Sans plan | Avec plan |
|---|---|
| Claude Code exécute immédiatement | Claude Code décrit ce qu'il va faire |
| Vous découvrez les erreurs après | Vous validez avant |
| Difficile à corriger si mauvaise direction | Facile d'ajuster avant le lancement |

> 💡 **Règle d'or : plus la tâche touche à des fichiers importants, plus le plan est indispensable.**

---

## Valider, exécuter, vérifier — la boucle en 3 temps

```
👀 Valider le plan        ▶️ Lancer l'exécution        ✅ Vérifier le résultat
Lire chaque étape,        "C'est bon, vas-y"            Ouvrir le fichier produit,
poser des questions                                      comparer avec ce qu'on
si besoin                                                voulait obtenir
```

**À la validation — les questions à se poser :**
- Est-ce que Claude Code a bien compris ma demande ?
- Y a-t-il une étape qui me semble risquée ou imprévue ?
- Les fichiers mentionnés sont-ils les bons ?

**À la vérification — ce qu'on contrôle :**
- Le résultat correspond-il au format demandé ?
- Les données sont-elles exactes ?
- Est-ce qu'un collègue pourrait utiliser ce fichier tel quel ?

> 💡 **Ne dites jamais "parfait" sans avoir ouvert le fichier produit.** Claude Code peut générer quelque chose de structurellement correct mais avec des données incorrectes.

---

## Introduction aux skills : créer un module d'expertise réutilisable

> Un skill, c'est une instruction permanente que vous enseignez une fois à Claude Code — et qu'il applique automatiquement à chaque fois.

**Ce que c'est concrètement :**
Un fichier texte que vous créez dans un dossier `/skills` de votre projet. Claude Code le lit et applique les règles qu'il contient sans que vous ayez à les répéter.

**Exemple — skill "format-rapport" :**
```
# Skill : Format des rapports

Chaque rapport généré doit toujours :
- Commencer par un résumé exécutif de 3 lignes maximum
- Utiliser des titres en français
- Inclure une section "Actions recommandées" à la fin
- Être nommé AAAA-MM-JJ_rapport-[sujet].md
```

**La différence avec le CLAUDE.md :**

| CLAUDE.md | Skill |
|---|---|
| Contexte général du projet | Règle spécifique à une tâche |
| Lu à chaque session | Appelé quand pertinent |
| Un seul par projet | Plusieurs skills possibles |

> 💡 **Pensez aux skills comme à des recettes.** Vous les écrivez une fois, Claude Code les suit à chaque fois qu'il cuisine ce plat.

---

## La mémoire persistante : comment Claude Code retient le contexte entre les sessions

> Sans mémoire persistante, Claude Code repart de zéro à chaque session. Avec, il se souvient de tout ce que vous lui avez appris.

**Les 3 niveaux de mémoire :**

| Niveau | Outil | Ce qu'il retient |
|---|---|---|
| **Projet** | CLAUDE.md | Le contexte général, les règles permanentes |
| **Tâche** | Skills | Les formats, conventions, standards métier |
| **Session** | Historique de conversation | Ce qui a été dit dans la session en cours |

**Ce que ça change en pratique :**
```
❌ Sans mémoire persistante
Session 1 : "Mes rapports sont toujours en français, format PDF"
Session 2 : Claude Code a oublié — vous réexpliquez

✅ Avec mémoire persistante (CLAUDE.md + skills)
Session 1 : vous configurez une fois
Session 2, 3, 4... : Claude Code applique automatiquement
```

> 💡 **La mémoire persistante se construit progressivement.** À chaque fois que vous réexpliquez quelque chose à Claude Code, demandez-vous : est-ce que ça devrait être dans mon CLAUDE.md ou dans un skill ?

---

## 🧩 Atelier 2 — De la tâche au script agentique

**Objectif :** transformer une tâche réelle en mission agentique complète et l'exécuter.

**Étape 1 — Identification**

Chaque participant choisit une tâche réelle à automatiser.

Cases à cocher :
- [ ] J'ai identifié ma tâche répétitive
- [ ] Elle répond aux 3 questions (fréquente, explicable, format stable)
- [ ] Je sais où sont les fichiers concernés

**Étape 2 — Structuration**

Rédiger le prompt avec le template des 5 éléments.

Cases à cocher :
- [ ] J'ai rédigé mon contexte
- [ ] J'ai indiqué les fichiers concernés
- [ ] J'ai décrit le résultat attendu
- [ ] J'ai défini mes critères de succès
- [ ] J'ai précisé le format de sortie

**Étape 3 — Exécution**

Cases à cocher :
- [ ] J'ai demandé un plan avant d'exécuter
- [ ] J'ai validé le plan proposé
- [ ] J'ai lancé l'exécution
- [ ] J'ai vérifié le résultat produit

**Exemples par profil**

*Marketing :*
- Nettoyage d'un export CRM en CSV
- Génération d'un rapport mensuel automatisé
- Reformatage d'une liste de leads

*Gestion :*
- Classement automatique de fichiers par type et date
- Résumé de 20 comptes rendus de réunion
- Génération d'un rapport PDF synthétique

---

## 🎉 Fin du Module 2

<!-- VISUEL : undraw_launch-event_aur1.svg — centré, écran de fin de module -->
