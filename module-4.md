# Module 4 — Confiance & autonomie
**Durée estimée : 1h15**

> Objectif : Repartir avec une vraie victoire personnelle et la confiance de continuer seul. Ce module n'est pas technique — il est humain.

---

## L'erreur fait partie du processus

> Dans un workflow agentique, l'erreur n'est pas un échec. C'est une étape normale de la boucle.

| Ce qu'on croit | La réalité |
|---|---|
| "Si ça plante, j'ai mal fait quelque chose" | Claude Code plante souvent à la première tentative — c'est prévu |
| "Une erreur = recommencer depuis zéro" | Une erreur = une information pour corriger |
| "Il faut comprendre l'erreur pour avancer" | Il faut juste la copier-coller à Claude Code |
| "L'IA devrait être parfaite du premier coup" | Même les développeurs expérimentés itèrent |

**Ce que l'erreur vous apprend :**
- Que Claude Code a besoin de plus de contexte
- Que votre prompt manque de précision sur un point
- Que le fichier d'entrée n'est pas dans le format attendu

> 💡 **Une erreur que Claude Code peut lire, c'est une erreur que Claude Code peut corriger.** Votre seul rôle : ne pas paniquer et lui redonner l'information.

---

## Lire un message d'erreur sans paniquer : les 3 informations clés

> Vous n'avez pas besoin de comprendre le code d'erreur. Vous avez besoin de repérer 3 choses.

**Les 3 informations à chercher dans un message d'erreur :**

```
❶ Quel fichier est concerné ?
   → Cherchez un nom de fichier avec une extension (.csv, .py, .md)

❷ Quelle ligne du problème ?
   → Cherchez "line XX" ou "ligne XX"

❸ Quel est le mot clé de l'erreur ?
   → Cherchez : "not found", "permission denied", "invalid", 
     "cannot read", "does not exist"
```

**Ce que vous faites ensuite :**

| Message d'erreur contient | Ce que ça veut dire | Ce que vous dites à Claude Code |
|---|---|---|
| "not found" / "does not exist" | Le fichier n'est pas au bon endroit | "Le fichier n'existe pas à cet endroit, voici où il est : [chemin]" |
| "permission denied" | Claude Code n'a pas accès au fichier | "Vous n'avez pas accès à ce fichier, essayez avec ce dossier à la place" |
| "invalid format" | Le fichier n'est pas dans le bon format | "Le format est incorrect, voici un exemple de fichier correct" |

> 💡 **Ne cherchez pas à comprendre le message d'erreur en entier.** Copiez-le intégralement et donnez-le à Claude Code — il sait quoi en faire.

---

## Forcer Claude Code à s'auto-corriger : les prompts de débogage qui marchent

> Quand quelque chose ne fonctionne pas, vous n'avez pas à trouver la solution. Vous avez à bien poser le problème.

**Les 3 prompts de débogage à connaître :**

**Prompt 1 — Donner l'erreur et demander la correction :**
```
"Voici l'erreur que j'obtiens : [coller le message d'erreur complet]
Corrige le problème et réessaie."
```

**Prompt 2 — Quand le résultat est incorrect sans erreur visible :**
```
"Le résultat ne correspond pas à ce que j'attendais.
Voici ce que j'ai obtenu : [décrire]
Voici ce que j'attendais : [décrire]
Identifie ce qui a mal fonctionné et corrige."
```

**Prompt 3 — Quand Claude Code tourne en rond :**
```
"Stop. Reviens à zéro sur cette étape.
Décrivez-moi votre nouvelle approche avant de l'exécuter."
```

**Ce qu'il ne faut pas faire :**

| ❌ À éviter | ✅ À faire à la place |
|---|---|
| "Ça marche pas, répare" | Décrire précisément ce qui ne va pas |
| Relancer exactement le même prompt | Ajouter l'information manquante |
| Laisser Claude Code boucler plus de 3 fois | Utiliser le Prompt 3 pour repartir proprement |

> 💡 **Si Claude Code échoue 3 fois de suite sur la même étape, arrêtez-le.** Reformulez la demande différemment plutôt que d'insister.

---

## Les 3 réflexes pour ne pas se bloquer seul

> Quand vous êtes bloqué, vous avez toujours une porte de sortie. En voici trois.

**Réflexe 1 — Reformuler**
```
Au lieu de : "Génère un rapport de mes fichiers"
Essayez : "Lis le fichier rapport-janvier.csv et liste 
les 5 valeurs les plus élevées de la colonne 'montant'"
```
Plus c'est précis, moins Claude Code improvise.

**Réflexe 2 — Simplifier**
```
Au lieu de : demander l'outil complet d'un coup
Essayez : "Fais juste la première étape : lire le fichier 
et m'afficher son contenu. Rien d'autre pour l'instant."
```
Réduire la portée de la tâche révèle souvent où est le vrai problème.

**Réflexe 3 — Demander un plan**
```
"Avant de continuer, expliquez-moi comment vous comptez 
résoudre ce problème étape par étape. 
N'exécutez rien tant que je n'ai pas validé."
```
Le plan force Claude Code à réfléchir avant d'agir.

**Quand utiliser lequel :**

| Situation | Réflexe à utiliser |
|---|---|
| Le résultat n'est pas ce que vous vouliez | Reformuler |
| Claude Code plante sur une tâche complexe | Simplifier |
| Vous ne savez plus où vous en êtes | Demander un plan |

> 💡 **Ces 3 réflexes couvrent 90% des situations de blocage.** Affichez-les quelque part pendant que vous travaillez.

---

## Mettre à jour son CLAUDE.md : documenter ce qu'on a appris

> Chaque fois que vous réexpliquez quelque chose à Claude Code, c'est un signe que votre CLAUDE.md est incomplet.

**La règle simple :**

```
Vous réexpliquez quelque chose pour la 2e fois ?
→ Ajoutez-le dans votre CLAUDE.md immédiatement.
```

**Ce que vous ajoutez après chaque session :**

| Ce qui s'est passé | Ce que vous ajoutez au CLAUDE.md |
|---|---|
| Claude Code a utilisé le mauvais format | La règle de format exacte |
| Claude Code a modifié un fichier qu'il ne fallait pas toucher | "Ne jamais modifier [nom du fichier]" |
| Vous avez dû préciser la langue à plusieurs reprises | "Toujours répondre en français" |
| Un skill a bien fonctionné | Référence au skill dans le CLAUDE.md |

**La routine de fin de session :**
```
"Avant de terminer, dites-moi ce que vous avez appris sur ce projet 
aujourd'hui qui devrait être ajouté au CLAUDE.md."
```

> 💡 **Un CLAUDE.md qui grandit à chaque session, c'est un agent qui devient plus intelligent à chaque utilisation.** C'est votre principal actif à long terme.

---

## Construire sa routine Claude Code : intégrer l'agent dans sa semaine

> Claude Code est plus puissant quand il fait partie de votre flux de travail régulier, pas quand vous l'utilisez de façon ponctuelle.

**La routine suggérée :**

| Fréquence | Action | Durée |
|---|---|---|
| **Chaque utilisation** | Relire le CLAUDE.md avant de commencer | 2 minutes |
| **Chaque utilisation** | Demander un plan avant d'exécuter | 1 minute |
| **Fin de session** | Mettre à jour le CLAUDE.md avec ce qu'on a appris | 5 minutes |
| **Hebdomadaire** | Lancer les tâches récurrentes automatisées | 10 minutes |
| **Mensuel** | Revoir les skills et vérifier s'ils sont encore pertinents | 15 minutes |

**Les 3 premières tâches à automatiser dès cette semaine :**
- La tâche que vous faites le plus souvent
- La tâche que vous détestez le plus
- La tâche qui prend le plus de temps pour peu de valeur ajoutée

**Ce que ça ressemble après 30 jours :**
```
Semaine 1 : 1 tâche automatisée, CLAUDE.md de base
Semaine 2 : 2-3 skills créés, routine installée
Semaine 3 : premiers outils stables, gains de temps visibles
Semaine 4 : vous ne vous souvenez plus comment vous faisiez avant
```

> 💡 **Le meilleur moment pour commencer sa routine Claude Code, c'est maintenant. Le deuxième meilleur moment, c'est demain matin.**

---

## 🧩 Atelier final — Ma victoire personnelle

**Objectif :** choisir une micro-victoire concrète et la compléter avant la fin de la formation.

**Choisir son défi**

| Défi | Ce que vous repartez avec |
|---|---|
| ✉️ Créer une signature de courriel HTML personnalisée | Un fichier HTML prêt à coller dans Outlook ou Gmail |
| 🤖 Créer un agent pour une tâche récurrente personnelle | Un script qui tourne chaque semaine sans intervention |
| 📝 Rédiger et enrichir son CLAUDE.md personnel | Un fichier de contexte qui rend Claude Code plus intelligent à chaque session |
| 📊 Améliorer l'outil construit en Module 2 ou 3 | Une version améliorée, plus robuste, prête à réutiliser |

Cases à cocher :
- [ ] J'ai choisi mon défi
- [ ] J'ai rédigé mon prompt de départ
- [ ] J'ai demandé un plan à Claude Code avant d'exécuter
- [ ] J'ai validé et lancé l'exécution
- [ ] J'ai vérifié le résultat
- [ ] Ma victoire est complète ✨

---

## 🎉 Clôture — Tour de table des victoires

Chaque participant partage en 60 secondes :
- Ce qu'il a créé
- Ce que ça lui permettra de faire différemment

> Pas de jugement, pas de perfection — juste la fierté d'avoir construit quelque chose de concret avec l'IA.

---

## 🎉 Fin du Module 4

<!-- VISUEL : undraw_launch-event_aur1.svg — centré, écran de fin de module -->
