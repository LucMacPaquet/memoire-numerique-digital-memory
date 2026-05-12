---
date: 2026-05-09
tags: [ressource, entretien, sauvegarde, mémoire-numérique]
type: processus
status: active
author: humain+claude
---

# 11 - Entretien de la mémoire numérique

> **Résumé en une phrase** : Entretenir la mémoire numérique exige des sauvegardes régulières, des retraits contrôlés par l'agent IA et une compréhension claire des limites des automatismes locaux.

## Synchronisation n'est pas sauvegarde

Un service de synchronisation rend les fichiers disponibles sur plusieurs appareils. Ce n'est pas une vraie sauvegarde historique. Une erreur synchronisée peut se propager partout.

Il faut donc prévoir des copies de sécurité indépendantes.

## Sauvegarde recommandée

Procédure simple :

1. Attendre que les fichiers soient synchronisés.
2. Fermer Obsidian ou s'assurer qu'aucune opération d'écriture n'est en cours.
3. Créer un fichier `.zip` daté du dossier complet du vault.
4. Conserver ce zip dans un emplacement différent du dossier synchronisé.
5. Tester périodiquement qu'il est possible de restaurer le zip.

Le zip devrait inclure :

- `AIOS/`
- `wiki/`
- `raw/`
- `archives/`
- `skills/`
- `.obsidian/`
- `.claude/`
- `.agents/`
- `CLAUDE.md`
- `AGENTS.md`
- `Inbox.md`

## Fichiers hors vault

Certains éléments utiles peuvent vivre hors du vault. Ils doivent être sauvegardés séparément s'ils sont nécessaires pour reproduire le kit :

- clés API et secrets conservés hors notes ;
- configurations globales d'outils IA ;
- scripts système ou services planifiés ;
- dossiers de projets reliés ;
- configurations d'automatisation ;
- fichiers `.env` exclus volontairement de la mémoire.

Ne jamais copier des secrets dans une note wiki pour "ne pas les perdre". Les documenter comme dépendances, pas comme valeurs.

## Retirer un sujet de la mémoire

Ne jamais effacer ou déplacer manuellement un sujet, projet ou dossier dans `wiki/`. Cela rendrait la mémoire numérique incohérente : index, liens, daily, log, sources et archives ne raconteraient plus la même histoire.

Il faut demander à l'agent IA de faire le retrait. Exemple :

> Je n'ai plus besoin du projet achat de vélo. Ne garde qu'une note synthèse de ce projet et efface tout le reste.

L'agent IA doit alors gérer la cohérence :

- créer ou enrichir une note synthèse ;
- mettre les notes retirées hors du chemin actif selon la règle du vault ;
- mettre à jour `wiki/index.md` ;
- ajouter une entrée à `wiki/log.md` ;
- mettre à jour la daily ;
- corriger les liens typés ;
- préserver la traçabilité vers les sources et archives.

## Automatismes et disponibilité

Les automatismes horodatés ne sont fiables que si l'environnement d'exécution est disponible. Si l'ordinateur est fermé, en veille profonde, hors réseau ou si l'outil requis n'est pas lancé, l'automatisme ne partira pas.

Une option à étudier est de déléguer les automatismes vers :

- un ordinateur local toujours allumé ;
- un petit serveur local ;
- une machine dans le nuage ;
- un orchestrateur comme n8n.

Ce choix augmente la fiabilité, mais ajoute de la complexité : sécurité, mises à jour, coûts, sauvegardes, accès réseau et surveillance.

## Sources

- [Obsidian — Back up your Obsidian files](https://help.obsidian.md/backup)
- [Obsidian — Sync notes](https://help.obsidian.md/sync-notes)
- [Microsoft — Sync files with OneDrive](https://support.microsoft.com/en-us/office/sync-your-computer-s-files-and-folders-with-onedrive-615391c4-2bd3-4aae-a42a-858262e42a49)

## Liens typés

- fait-partie-de → [[Fonctionnement-complet-du-vault-Obsidian-AIOS]]
- soutient → [[10-Maintenance-et-choses-automatiques]]
- soutient → [[03-Architecture-du-vault]]
- rédigé-par → humain+claude
