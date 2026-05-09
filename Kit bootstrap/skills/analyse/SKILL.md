---
name: analyse
description: Synthese transversale de notes wiki pour detecter les themes communs, les tensions, les opportunites et les questions ouvertes.
---

# Skill - analyse

> **Resume en une phrase** : Ce skill aide l'agent IA a relire plusieurs notes structurees pour produire une synthese utile, citee et reliee.

## Objectif

Produire une note de synthese a partir de plusieurs notes existantes, sans inventer d'information et sans remplacer les sources.

## Declencheur

Utiliser `/analyse` quand :

- plusieurs notes traitent d'un meme theme ;
- l'utilisateur demande une synthese ;
- une ingestion ajoute plusieurs sources proches ;
- un projet a besoin d'un bilan, d'une decision ou d'une vue d'ensemble.

## Fichiers lus

- `wiki/index.md`
- notes pertinentes dans `wiki/`
- `AIOS/Me.md` si la synthese doit etre contextualisee pour l'utilisateur
- `AIOS/Note Types.md`
- `AIOS/Edge Types.md`

## Fichiers modifies

- une note de synthese dans `wiki/Intelligence/` ou dans le dossier wiki le plus pertinent ;
- `wiki/index.md` si une nouvelle note importante est creee ;
- `wiki/Daily/YYYY-MM-DD.md` ;
- `wiki/log.md`.

## Etapes

1. Identifier les notes sources pertinentes.
2. Verifier leur `status`.
3. Ignorer les notes archivees sauf si l'utilisateur demande l'historique.
4. Regrouper les idees communes.
5. Distinguer faits, hypotheses, decisions, questions et interpretations.
6. Creer ou enrichir une note de synthese.
7. Ajouter un resume en une phrase.
8. Ajouter les liens types vers les sources.
9. Mettre a jour daily et log.

## Format recommande

```markdown
# Analyse - <Sujet>

> **Resume en une phrase** : ...

## Synthese

## Ce qui revient souvent

## Tensions ou contradictions

## Opportunites

## Questions ouvertes

## Notes sources

- [[Note source 1]]
- [[Note source 2]]

## Liens types

- derive-de -> [[Note source 1]]
- derive-de -> [[Note source 2]]
- fait-partie-de -> [[Sujet parent]]
- redige-par -> humain+ia
```

## Regles

- Ne pas creer une synthese durable pour une seule note source, sauf demande explicite.
- Ne pas inventer de conclusion absente des sources.
- Citer les notes sources.
- Expliquer les incertitudes.
- Ne pas supprimer ou remplacer les notes sources.
- Si la synthese est contextualisee, utiliser `AIOS/Me.md` sans y ajouter d'information non validee.

## Sortie attendue

Rapport final :

- notes lues ;
- themes detectes ;
- note creee ou enrichie ;
- incertitudes ;
- fichiers mis a jour.
