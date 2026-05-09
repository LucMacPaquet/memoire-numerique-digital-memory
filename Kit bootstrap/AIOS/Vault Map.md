# Vault Map - Memoire numerique

> **Resume en une phrase** : Cette carte explique la structure du vault, le role de chaque dossier et les regles que l'agent IA doit suivre pour maintenir une memoire numerique coherente.

## Architecture generale

Ce vault suit une architecture en couches simples :

```text
raw/        -> entrees brutes a traiter
wiki/       -> memoire numerique structuree
archives/   -> sources traitees et conservees
AIOS/       -> cartes, regles et contexte pour l'agent IA
skills/     -> procedures reutilisables
```

La regle centrale est : l'utilisateur capture vite dans `raw/`, l'agent IA structure dans `wiki/`, puis les sources traitees sont deplacees dans `archives/`.

## Role des dossiers

| Dossier | Role | Qui ecrit normalement |
| --- | --- | --- |
| `raw/` | Boite d'entree : notes rapides, captures web, documents et idees non classees | Utilisateur, Obsidian, Web Clipper ou automatisation |
| `wiki/` | Memoire durable : notes propres, reliees, datees et maintenues | Agent IA |
| `wiki/idées/` | Idees detectees pendant `/ingest`, reliees aux projets et autres idees | Agent IA |
| `archives/` | Sources brutes deja traitees, conservees pour la tracabilite | Agent IA apres `/ingest` |
| `AIOS/` | Manuel portable pour les agents IA | Agent IA, avec prudence |
| `skills/` | Procedures operationnelles : `/prime`, `/ingest`, `/save`, `/query`, `/lint` | Agent IA ou personne responsable du kit |

## Sous-dossiers recommandes

### `raw/`

| Dossier | Usage |
| --- | --- |
| `raw/notes/` | Notes rapides, pensees, observations, idees |
| `raw/clippings/` | Captures web, articles, pages, extraits |
| `raw/docs/` | Documents, PDF, fichiers exportes |

Le contenu de `raw/` ne doit pas etre modifie. Apres un `/ingest` reussi, le fichier source est deplace dans le sous-dossier correspondant de `archives/`.

### `wiki/`

| Dossier | Usage |
| --- | --- |
| `wiki/index.md` | Point d'entree de la memoire |
| `wiki/log.md` | Journal append-only des operations |
| `wiki/Daily/` | Notes quotidiennes |
| `wiki/Context/` | Profil, objectifs, contraintes, contexte durable |
| `wiki/Intelligence/` | Recherches, analyses, syntheses transversales |
| `wiki/Projets/` | Notes par projet |
| `wiki/Resources/` | Guides, modeles, references et procedures |
| `wiki/idées/` | Idees structurees et reliees |

## Fichiers AIOS essentiels

| Fichier | Role |
| --- | --- |
| `AIOS/Me.md` | Profil de l'utilisateur : role, objectifs, preferences, contraintes |
| `AIOS/Vault Map.md` | Cette carte de structure |
| `AIOS/Skills Map.md` | Carte des workflows et commandes |
| `AIOS/Note Types.md` | Reference des 16 types de notes |
| `AIOS/Edge Types.md` | Reference des 10 liens types |
| `AIOS/Codex Config.md` | Note generique sur les outils IA et configurations non secretes |

## Format obligatoire des notes wiki

Chaque note durable dans `wiki/` doit commencer par un frontmatter YAML :

```yaml
---
date: YYYY-MM-DD
tags: []
type: concept
status: active
source: archives/notes/source.md
author: humain+claude
---
```

Champs importants :

- `date` : date de creation ou de derniere structuration importante.
- `tags` : mots-cles utiles.
- `type` : un des 16 types documentes dans [[AIOS/Note Types]].
- `status` : `active` ou `archive`.
- `source` : obligatoire si la note vient de `raw/`.
- `author` : `humain`, `ia` ou `humain+ia`.

## Structure d'une note durable

```markdown
# Titre de la note

> **Resume en une phrase** : Phrase courte qui explique pourquoi cette note existe.

## Resume

Quelques phrases de contexte.

## Contenu

Sections utiles, liens internes, decisions, faits et questions.

## Liens types

- fait-partie-de -> [[Nom du parent]]
- derive-de -> [[archives/notes/source.md]]
- redige-par -> humain+ia
```

## Regles de creation

1. Chercher d'abord si une note existante couvre deja le sujet.
2. Enrichir une note existante plutot que creer un doublon.
3. Creer une nouvelle note seulement si le sujet merite un noeud durable.
4. Ajouter un resume en une phrase.
5. Ajouter au moins un lien type.
6. Mettre a jour `wiki/index.md` si la note devient importante.
7. Journaliser dans `wiki/Daily/YYYY-MM-DD.md` et `wiki/log.md` quand l'operation est significative.

## Cas special : idees

Quand une source dans `raw/` parle d'une idee, `/ingest` cree une note dans `wiki/idées/`.

Convention de nommage :

```text
wiki/idées/(YYYY-MM-DD_HHhMM)-(nom-de-l-idee).md
```

La note d'idee doit contenir :

- le contexte de l'idee ;
- ce qu'elle permettrait ;
- les projets ou sujets relies ;
- les risques ou questions ouvertes ;
- un lien `derive-de -> [[archives/...]]` vers la source traitee.

## Regles de retrait

Ne pas effacer manuellement une note de `wiki/`. Si un sujet n'est plus utile, demander a l'agent IA de :

- creer ou conserver une synthese utile ;
- passer les notes non actives a `status: archive` ;
- mettre a jour les index, liens, daily et log ;
- conserver la tracabilite dans `archives/`.

## Liens types

- fait-partie-de -> [[AIOS/Me]]
- soutient -> [[AIOS/Skills Map]]
- soutient -> [[AIOS/Note Types]]
- soutient -> [[AIOS/Edge Types]]
- redige-par -> humain+ia
