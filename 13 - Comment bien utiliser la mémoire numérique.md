---
date: 2026-05-09
tags: [ressource, usages, mémoire-numérique, capture]
type: processus
status: active
author: humain+claude
---

# 13 - Comment bien utiliser la mémoire numérique

> **Résumé en une phrase** : La meilleure utilisation de la mémoire numérique consiste à capturer vite dans `raw/`, puis à laisser l'agent IA structurer, relier et maintenir la connaissance durable.

## Réflexe principal

Capturer maintenant, structurer plus tard.

La mémoire numérique fonctionne bien quand elle réduit la friction. Une idée ne devrait pas attendre que le bon dossier, le bon titre et les bons liens soient trouvés. On capture dans `raw/`, puis `/ingest` transforme la capture en mémoire structurée.

## Exemple 1 — Show techno avec cellulaire

Situation : vous êtes dans un événement techno, téléphone en main. Une présentation déclenche une idée pour un client.

Capture dans Notes Rapides :

```text
2026-05-09 — Idée client
Pendant la présentation sur [sujet], j'ai pensé à [client].
Lien avec son besoin : ...
Question à creuser : ...
Action possible : ...
```

Destination : `raw/notes/`.

Au prochain `/ingest`, l'agent IA :

- détecte l'idée ;
- crée ou enrichit une note dans `wiki/idées/` ou `wiki/Projets/` ;
- lie l'idée au client ou projet pertinent ;
- met à jour index, daily et log ;
- déplace la source vers `archives/`.

## Exemple 2 — Création d'articles LinkedIn

Workflow possible :

1. Capturer des sources avec Obsidian Web Clipper dans `raw/clippings/`.
2. Ajouter une idée ou un angle personnel dans `raw/notes/`.
3. Lancer `/ingest` pour créer les notes structurées.
4. Demander à l'agent IA de produire un angle LinkedIn relié aux sources.
5. Relier le brouillon au style éditorial et aux notes pertinentes.
6. Générer un visuel si un skill image existe.
7. Sauvegarder la session avec `/save`.

Ce workflow transforme la veille et les idées en contenu réutilisable sans perdre la trace des sources.

## Exemple 3 — Suivi de santé

La mémoire numérique peut aider à suivre des observations personnelles :

- symptômes ;
- sommeil ;
- énergie ;
- alimentation ;
- entraînement ;
- questions à poser à un professionnel ;
- effets observés après un changement d'habitude.

Capture dans `raw/notes/`, puis `/ingest` structure les observations. Ce n'est pas un avis médical et ça ne remplace pas un professionnel de santé. C'est une mémoire de suivi pour mieux préparer les discussions et repérer des tendances.

## Exemple 4 — Projet client

Après une réunion ou une idée en déplacement, capturer :

- contexte client ;
- besoin exprimé ;
- contrainte ;
- décision ;
- risque ;
- prochaine action ;
- lien avec une offre ou un projet existant.

Au prochain ingest, l'agent IA peut relier la capture au bon projet, créer une synthèse, identifier une tâche ou mettre à jour une note client.

## Bonnes pratiques de capture

- Écrire court mais avec assez de contexte.
- Nommer les personnes, projets ou clients concernés.
- Ajouter la date si elle n'est pas automatique.
- Ajouter l'origine de l'idée : événement, article, discussion, réunion.
- Ne pas chercher le classement parfait au moment de capturer.

## Liens typés

- fait-partie-de → [[Fonctionnement complet du vault Obsidian + AIOS]]
- soutient → [[06 - Ingest raw vers wiki]]
- soutient → [[08 - Skills et automatisations]]
- soutient → [[Obsidian Web Clipper - Internet en texte brut]]
- rédigé-par → humain+claude
