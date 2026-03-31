# Charte graphique — La Fusée
> Document de référence à fournir à Claude Code pour tout projet de data viz ou interface web.

---

## Couleurs

### Primaires
| Nom | Hex | Usage |
|---|---|---|
| Violet La Fusée | `#742cff` | Couleur principale — titres, boutons, accents forts, éléments actifs |
| Blanc | `#ffffff` | Fonds, texte sur fond violet |

### Secondaires
| Nom | Hex | Usage |
|---|---|---|
| Violet moyen | `#ab80ff` | Éléments secondaires, hover, badges, barres de graphiques secondaires |
| Violet clair | `#e3d5ff` | Fonds de cartes, highlights, zones de survol légères |
| Noir | `#000000` | Texte courant sur fond clair |

### Palette de données (pour graphiques multi-séries)
Utiliser dans cet ordre pour les séries de données :
1. `#742cff` — série principale
2. `#ab80ff` — série secondaire
3. `#e3d5ff` — série tertiaire
4. `#000000` à 20% d'opacité — grilles et séparateurs

---

## Typographie

| Usage | Police | Graisse | Taille recommandée |
|---|---|---|---|
| Titres principaux (H1) | Poppins | 700 Bold | 24–32px |
| Titres secondaires (H2, H3) | Poppins | 700 Bold | 16–20px |
| Texte courant | Poppins | 400 Regular | 14px |
| Labels de graphiques | Poppins | 400 Regular | 12px |
| Métriques clés (KPI) | Poppins | 700 Bold | 32–48px |

**Import Google Fonts à inclure dans tout projet HTML :**
```html
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
```

---

## Règles d'application

- Le fond général des dashboards est **blanc** (`#ffffff`)
- Les cartes KPI ont un fond **violet clair** (`#e3d5ff`) avec une bordure ou accent **violet principal** (`#742cff`)
- Les boutons principaux sont en **violet principal** (`#742cff`) avec texte blanc
- Les boutons secondaires / filtres sont en **violet moyen** (`#ab80ff`) avec texte blanc
- Les tableaux de données alternent entre fond blanc et fond **violet clair** (`#e3d5ff`) pour les lignes paires
- Pas de bordures grises épaisses — privilégier des séparateurs légers (`#e3d5ff`)
- Coins arrondis : `border-radius: 8px` pour les cartes, `4px` pour les boutons et badges

---

## Logo

- Fournir le fichier logo séparément (PNG avec fond transparent recommandé)
- Placer en haut à gauche de tout dashboard ou document
- Ne jamais modifier les couleurs du logo
- Espacement minimum autour du logo : 16px

---

## Instructions pour Claude Code

Quand tu crées une interface HTML/JS pour La Fusée :
1. Importer Poppins depuis Google Fonts
2. Utiliser exclusivement la palette ci-dessus
3. Appliquer le violet principal `#742cff` comme couleur d'accent dominante
4. Garder les fonds blancs pour maximiser la lisibilité
5. Utiliser `#e3d5ff` pour les zones de fond secondaires (cartes, lignes de tableau)
6. Tous les titres en Poppins 700, tout le reste en Poppins 400
