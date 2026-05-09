# Skills Map - Memoire numerique

> **Resume en une phrase** : Cette carte decrit les routines que l'agent IA doit suivre pour charger le contexte, ingerer les sources, sauvegarder le travail, chercher dans le vault et verifier la sante de la memoire.

## Arbre de decision

```text
Debut de session
  -> /prime

Fichiers presents dans raw/
  -> /ingest

Question sur la memoire
  -> /query

Plusieurs notes a comparer ou synthetiser
  -> /analyse

Fin de session ou pause importante
  -> /save

Entretien periodique
  -> /lint
```

## Skills essentiels

### `/prime` - Charger le contexte

- **Declencheur** : debut de session.
- **Lit** : `AGENTS.md`, `CLAUDE.md` si present, `AIOS/Me.md`, `AIOS/Vault Map.md`, `AIOS/Skills Map.md`, `wiki/index.md`, daily recente.
- **Modifie** : rien.
- **Sortie attendue** : resume du contexte, points d'attention, proposition de prochaine action.

### `/ingest` - Transformer `raw/` en memoire structuree

- **Declencheur** : fichiers dans `raw/notes/`, `raw/clippings/` ou `raw/docs/`.
- **Lit** : sources brutes sans modifier leur contenu.
- **Modifie** : notes dans `wiki/`, `wiki/idées/`, `archives/`, `wiki/index.md`, daily et log.
- **Regle cle** : apres traitement reussi, deplacer la source vers `archives/`.
- **Sortie attendue** : fichiers traites, notes creees ou enrichies, sources archivees, incertitudes.

### `/save` - Journaliser la session

- **Declencheur** : fin de session ou pause importante.
- **Lit** : changements de la session.
- **Modifie** : `wiki/Daily/YYYY-MM-DD.md`, `wiki/log.md`, parfois `wiki/index.md`.
- **Regle cle** : ne jamais toucher a `raw/`.
- **Sortie attendue** : resume des changements et fichiers touches.

### `/query` - Repondre a partir du vault

- **Declencheur** : question sur un sujet, projet, decision ou souvenir.
- **Lit** : `wiki/index.md`, puis les notes pertinentes.
- **Modifie** : rien par defaut.
- **Regle cle** : ne pas inventer. Si l'information manque, le dire.
- **Sortie attendue** : reponse concise avec notes sources citees.

### `/lint` - Verifier la sante de la memoire

- **Declencheur** : entretien periodique ou doute sur la coherence.
- **Lit** : notes `wiki/`, AIOS, index, daily, log.
- **Verifie** : frontmatter, types, liens types, liens casses, notes orphelines, sources archivees, index.
- **Modifie** : corrections simples et documentees, jamais de suppression.
- **Sortie attendue** : rapport d'ecarts et corrections appliquees ou proposees.

### `/analyse` - Produire une synthese transversale

- **Declencheur** : plusieurs notes sur un meme theme ou demande de recul.
- **Lit** : notes pertinentes, souvent dans `wiki/Intelligence/`.
- **Modifie** : cree ou enrichit une note de synthese.
- **Regle cle** : citer les sources et distinguer faits, hypotheses et interpretations.
- **Sortie attendue** : note de synthese avec liens types vers les sources.

## Skills techniques inclus dans le kit

| Skill | Role | Statut |
| --- | --- | --- |
| `obsidian-markdown` | Conventions Markdown compatibles Obsidian : frontmatter, wikilinks, embeds, callouts, Mermaid | Inclus |
| `json-canvas` | Creation et modification de fichiers `.canvas` Obsidian | Inclus |

Les skills avances non inclus peuvent etre ajoutes plus tard au besoin. Le kit de base doit rester simple, portable et comprehensible.

## Sequences recommandees

### Session normale

```text
1. /prime
2. travail demande
3. /save
```

### Session d'ingestion

```text
1. /prime
2. /ingest
3. /save
```

### Entretien

```text
1. /prime
2. /lint
3. /save
```

## Comment ajouter un skill

1. Creer un fichier dans `skills/`.
2. Decrire son objectif, son declencheur, les fichiers lus, les fichiers modifies, les etapes et la sortie attendue.
3. Tester sur un cas simple.
4. Ajouter une entree dans cette Skills Map.
5. Journaliser l'ajout dans daily et log.

## Liens types

- fait-partie-de -> [[AIOS/Vault Map]]
- soutient -> [[skills/README]]
- soutient -> [[AIOS/Note Types]]
- soutient -> [[AIOS/Edge Types]]
- redige-par -> humain+ia
