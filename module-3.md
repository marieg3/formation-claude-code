# Module 3 — Créer un outil intelligent avec Claude Code
**Durée estimée : 1h15**

> Objectif : Aller plus loin que le script ponctuel : construire un mini-système reproductible, avec une logique métier, des skills personnalisés et une structure qui tient dans le temps.

---

## Qu'est-ce qu'un "outil" vs un "script" ?

> Avant de construire, clarifier ce que vous voulez vraiment. Ce n'est pas la même chose.

| | Script | Outil |
|---|---|---|
| **Durée de vie** | Usage unique ou ponctuel | Réutilisé régulièrement |
| **Qui l'utilise** | Vous seulement | Vous et potentiellement d'autres |
| **Niveau de robustesse** | Peut être approximatif | Doit fonctionner à chaque fois |
| **Exemple** | Nettoyer un fichier CSV une fois | Agent qui nettoie les exports CRM chaque semaine |

**Les 2 questions à se poser avant de commencer :**
- Est-ce que je vais réutiliser ça dans 3 mois ?
- Est-ce que quelqu'un d'autre pourrait avoir besoin de l'utiliser ?

> 💡 **Si oui à l'une des deux : construisez un outil, pas juste un script.** Ça change la façon dont vous briefez Claude Code dès le départ.

---

## Construire un CLAUDE.md de projet : définir les règles permanentes

> Le CLAUDE.md de projet, c'est la constitution de votre outil. Claude Code s'y réfère à chaque session.

**Ce qu'il doit contenir pour un outil :**

```
# Nom du projet

## Ce que fait cet outil
[Description en 2-3 phrases]

## Fichiers et structure
- Les fichiers d'entrée sont dans : [dossier]
- Les fichiers de sortie vont dans : [dossier]
- Ne jamais modifier les fichiers originaux

## Règles permanentes
- [Langue, format, conventions spécifiques]
- [Ce qu'il ne faut jamais faire]

## Critères de qualité
- [Comment savoir que le résultat est bon]
```

**La différence avec un CLAUDE.md personnel :**

| CLAUDE.md personnel | CLAUDE.md de projet |
|---|---|
| Vos préférences générales | Les règles de cet outil spécifique |
| Reste d'une session à l'autre | Reste d'une version à l'autre |
| À la racine de votre ordinateur | À la racine du dossier du projet |

> 💡 **Plus votre CLAUDE.md de projet est précis, plus l'outil est stable.** C'est ce qui fait la différence entre un prototype et un vrai livrable.

---

## Créer des skills personnalisés : enseigner vos standards à Claude Code

> Un skill personnalisé, c'est votre expertise métier traduite en instructions que Claude Code suit automatiquement.

**Comment créer un skill :**

```
formation-claude-code/
└── .claude/
    └── skills/
        ├── format-rapport.md
        ├── nettoyage-csv.md
        └── nommage-fichiers.md
```

**Exemple — skill "nettoyage-csv" :**
```
# Skill : Nettoyage de fichiers CSV

Quand vous nettoyez un fichier CSV, toujours :
1. Supprimer les lignes vides
2. Uniformiser les majuscules dans la colonne "Nom"
3. Formater les numéros de téléphone : +1 (XXX) XXX-XXXX
4. Signaler les doublons sans les supprimer automatiquement
5. Générer un rapport de nettoyage : nb lignes traitées,
   nb doublons trouvés, nb erreurs corrigées
```

**Les bons candidats pour un skill :**
- Un format de rapport que vous utilisez toujours
- Des règles de nommage de fichiers
- Des conventions de nettoyage de données
- Un style de rédaction spécifique

> 💡 **Un skill bien écrit = une tâche que vous n'expliquez plus jamais.** Investissez 10 minutes à l'écrire, gagnez des heures à chaque utilisation.

---

## Introduction aux sous-agents : déléguer des tâches en parallèle

> Un sous-agent, c'est Claude Code qui crée et supervise d'autres instances de lui-même pour traiter plusieurs tâches simultanément.

**Comment ça fonctionne :**

```
🧠 Agent principal
"Analyse les 50 rapports du dossier"
        │
        ├── 🤖 Sous-agent 1        🤖 Sous-agent 2        🤖 Sous-agent 3
        │   Rapports 1-17          Rapports 18-34          Rapports 35-50
        │
        └── ✅ Résultat consolidé en une fraction du temps
```

**Quand utiliser des sous-agents :**

| ✅ Bon cas d'usage | ❌ Pas nécessaire |
|---|---|
| Traiter un grand volume de fichiers | Traiter 5 fichiers ou moins |
| Tâches indépendantes les unes des autres | Tâches qui dépendent du résultat précédent |
| Gagner du temps sur des traitements longs | Tâche rapide à exécuter en séquence |

**Comment le demander :**
```
"Pour traiter les 50 fichiers plus rapidement, utilise des 
sous-agents pour paralléliser le traitement. Divise le travail 
en groupes égaux et consolide les résultats à la fin."
```

> 💡 **Vous n'avez pas besoin de comprendre comment les sous-agents fonctionnent.** Vous avez juste besoin de savoir quand les demander.

---

## Générer par étapes et tester à chaque étape

> Ne demandez pas tout d'un coup. Un outil solide se construit étape par étape, avec une validation à chaque palier.

**La méthode en 4 paliers :**

```
Palier 1          Palier 2          Palier 3          Palier 4
Prototype         Logique           Skills &           Stabilisation
minimal           métier            mémoire            & livraison
─────────         ─────────         ─────────          ─────────
"Fais une         "Ajoute les       "Crée le           "Teste avec
version           règles de         skill et           de vraies
basique qui       traitement        le CLAUDE.md       données et
fonctionne"       spécifiques"      de projet"         corrige"
    │                 │                 │                  │
    ✅ Valider        ✅ Valider        ✅ Valider         ✅ Livrable
```

**Ce que vous dites à Claude Code à chaque palier :**
- Palier 1 : *"Fais une version simple qui fonctionne, on affinera ensuite"*
- Palier 2 : *"La base fonctionne. Maintenant ajoute [règle spécifique]"*
- Palier 3 : *"Crée le skill correspondant et mets à jour le CLAUDE.md"*
- Palier 4 : *"Teste avec ce fichier réel et dis-moi ce qui ne fonctionne pas"*

> 💡 **Un outil construit en 4 paliers validés vaut mieux qu'un outil parfait demandé d'un coup et jamais livré.**

---

## Stabiliser l'outil : le rendre robuste et utilisable par d'autres

> Un outil stable, c'est un outil que quelqu'un d'autre peut utiliser sans vous appeler.

**Les 4 critères d'un outil stable :**

| Critère | Question à se poser | Comment y répondre |
|---|---|---|
| **Fiable** | Est-ce qu'il produit le même résultat à chaque fois ? | Tester avec 3 jeux de données différents |
| **Documenté** | Est-ce qu'un collègue peut l'utiliser sans explication ? | CLAUDE.md clair + README simple |
| **Sécurisé** | Est-ce qu'il peut effacer des données par erreur ? | Règle "jamais supprimer les originaux" dans le CLAUDE.md |
| **Maintenable** | Est-ce que vous pouvez le modifier dans 6 mois ? | Skills bien nommés, structure de dossier logique |

**Le test final avant de livrer :**
```
"Fais semblant de ne rien savoir de ce projet. 
Lis uniquement le CLAUDE.md et les skills disponibles. 
Exécute l'outil sur ce fichier de test et dis-moi 
si quelque chose manque ou n'est pas clair."
```

> 💡 **Si Claude Code peut l'exécuter correctement avec seulement le CLAUDE.md comme guide, votre outil est prêt.**

---

## 🧩 Atelier 3 — Construire son premier outil local

**Objectif :** repartir avec un mini-outil complet, réutilisable dès le lendemain.

**Étape 1 — Définir le projet**

Cases à cocher :
- [ ] J'ai choisi ma problématique : quel outil je veux construire
- [ ] J'ai clarifié : c'est un outil (réutilisable) et pas juste un script
- [ ] Je sais où sont les fichiers d'entrée et où iront les fichiers de sortie

**Étape 2 — Construire la structure**

Cases à cocher :
- [ ] J'ai créé le CLAUDE.md de projet avec les règles permanentes
- [ ] J'ai créé au moins un skill personnalisé
- [ ] J'ai défini la logique métier de l'outil

**Étape 3 — Générer et tester**

Cases à cocher :
- [ ] J'ai demandé un prototype minimal (palier 1)
- [ ] J'ai validé et ajouté la logique métier (palier 2)
- [ ] J'ai testé avec un fichier réel

**Étape 4 — Stabiliser**

Cases à cocher :
- [ ] L'outil produit le même résultat à chaque exécution
- [ ] Le CLAUDE.md est assez clair pour qu'un collègue l'utilise
- [ ] Je peux réutiliser cet outil dès demain ✅

**Exemples d'outils construits en atelier :**
- 📊 Agent d'analyse automatique d'un dossier de rapports (résumé + scoring)
- 🔄 Outil de transformation massive de fichiers CSV avec règles métier
- 🗂️ Système de classement et renommage automatique de documents
- 🔔 Mini-agent de veille : surveille un dossier et génère une alerte synthétique

---

## 🎉 Fin du Module 3

<!-- VISUEL : undraw_launch-event_aur1.svg — centré, écran de fin de module -->
