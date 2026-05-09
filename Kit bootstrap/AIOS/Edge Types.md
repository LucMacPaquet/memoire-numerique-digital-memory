# Types d'arêtes — Liens typés Infinite Brain

> **Résumé en une phrase** : Les liens entre notes ne sont plus de simples `[[wiki links]]` — chacun porte un type en français qui dit POURQUOI deux nœuds sont reliés, permettant à l'IA de choisir quelles arêtes suivre selon la nature de la question.

## Convention de langue

**Tous les identifiants d'arêtes sont en français** dans ce vault, en `kebab-case-accentué` pour les termes composés (ex. `dépend-de`, `fait-partie-de`).

## Les 10 types d'arêtes

| Type d'arête | Signification | Quand utiliser |
| ------------ | ------------- | -------------- |
| `soutient` | A renforce l'argument de B | Citation, donnée qui appuie une thèse |
| `contredit` | A s'oppose à B | Conflit d'idées, données opposées |
| `dépend-de` | A vrai seulement si B vrai | Hypothèse conditionnelle, prérequis |
| `dérivé-de` | A créé à partir de l'idée B | Décision issue d'un pilier, note issue d'une source |
| `lié-à` | Lien flou, contexte général | Quand aucune autre arête ne colle (à utiliser avec parcimonie) |
| `fait-partie-de` | A est composant de B | Sous-projet, étape d'un processus, tactique d'une stratégie |
| `précédé-par` | A vient après B dans un flux | Étape N suit étape N-1, daily du lendemain |
| `suivi-par` | A vient avant B dans un flux | Étape N précède étape N+1 |
| `rédigé-par` | Qui a créé ce contenu | `humain`, `claude`, `humain+claude`, `chatgpt`, etc. |
| `catégorisé-par` | Lien de classification générique | Groupe thématique, catégorie transverse |

## Convention syntaxique dans ce vault

Deux niveaux co-existent :

### Liens narratifs (inline)

Pour la lecture humaine, on garde les `[[wiki links]]` standards dans le corps de la note :

> Comme expliqué dans [[Anti-hallucination - Database Rules Pattern]], on combine hard hooks et soft steering.

### Liens typés (formels, pour l'IA)

Section dédiée en **pied de note**, avant les autres méta-sections :

```markdown
## Liens typés

- soutient → [[Note A]], [[Note B]]
- contredit → [[Note C]]
- dépend-de → [[Note D]]
- dérivé-de → [[Note source originale]]
- fait-partie-de → [[Pilier parent]]
- rédigé-par → claude
```

**Règle** : chaque note a au minimum un lien typé `dérivé-de` ou `fait-partie-de` pour éviter les nœuds orphelins dans le graphe.

## Filtrage contextuel par l'IA

L'intérêt du typage : l'IA choisit quelles arêtes suivre selon la question :

| Question type | Arêtes à suivre | Arêtes à ignorer |
| ------------- | --------------- | ---------------- |
| Conceptuelle (pourquoi ?) | `soutient`, `contredit`, `dérivé-de` | `précédé-par`, `suivi-par` |
| Opérationnelle (comment ?) | `fait-partie-de`, `précédé-par`, `suivi-par` | `contredit`, `dérivé-de` |
| Attribution (qui ?) | `rédigé-par` | tout le reste |
| Exhaustivité (tout sur X) | toutes | — |

## Règle pour /ingest

Lors de la création/enrichissement d'une note wiki :
1. Identifier les notes connexes existantes (via grep sur le contenu)
2. Pour chaque lien créé, choisir le type d'arête le plus précis
3. Toujours inclure `rédigé-par` dans les liens typés
4. Section `## Liens typés` placée en pied de note, avant `## Voir aussi` s'il existe

## Voir aussi

- `AIOS/Note Types.md` — les 16 types de nœuds (en français)
- `AIOS/Vault Map.md` — règles du vault
- `wiki/Intelligence/Knowledge-Management/Infinite Brain - Knowledge Graph optimisé pour l'IA.md` — théorie complète
