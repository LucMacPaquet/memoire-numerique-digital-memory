---
date: YYYY-MM-DD
tags: [aios, configuration, outils-ia]
type: référence
status: active
author: humain+ia
---

# Codex Config - Configuration generique

> **Resume en une phrase** : Cette note documente les outils IA et les configurations non secretes utiles au vault, sans jamais conserver de jetons, cles ou mots de passe.

## Objectif

Garder une reference claire des outils utilises pour maintenir la memoire numerique, tout en separant strictement la documentation des valeurs secretes.

Cette note peut servir avec Codex, Claude Code, Gemini CLI, OpenCode ou un autre agent IA compatible avec un dossier local.

## Outils IA possibles

| Outil | Role possible | Obligatoire ? |
| --- | --- | --- |
| Claude Code | Agent IA local pour lire et modifier le vault | Non |
| Codex | Agent IA local pour lire et modifier le vault | Non |
| Gemini CLI | Agent IA local pour lire et modifier le vault | Non |
| OpenCode | Agent IA local ou extensible | Non |

Un seul outil IA est requis pour commencer. Les autres sont optionnels.

## Outils externes

Les outils externes peuvent etre documentes ici si le vault en depend : service de synchronisation, outil de capture web, automatisation, moteur local, scripts, connecteurs, etc.

Regles :

- documenter le nom de l'outil ;
- documenter son role ;
- documenter ou se trouve sa configuration si c'est utile ;
- ne jamais documenter de secret ;
- ne jamais ecrire de jeton, mot de passe, cle privee ou valeur d'authentification.

## Securite

- Les secrets restent hors du vault.
- Les exemples doivent utiliser des placeholders comme `<TOKEN>`, `<CLIENT_ID>` ou `<CHEMIN_LOCAL>`.
- Si une information semble sensible, demander confirmation avant de l'ecrire.
- Si un secret est detecte dans une note, le signaler et proposer une procedure de retrait.

## Regles d'usage pour l'agent IA

- Pour tout travail sur le vault, lire d'abord `AGENTS.md`, `CLAUDE.md` si present, `AIOS/Vault Map.md` et `AIOS/Skills Map.md`.
- Pour les questions sur la memoire, commencer par `wiki/index.md`.
- Pour les changements durables, mettre a jour daily et log.
- Pour les outils externes, documenter la dependance sans ses secrets.

## Liens types

- fait-partie-de -> [[AIOS/Vault Map]]
- soutient -> [[AIOS/Skills Map]]
- soutient -> [[01 - Requis]]
- redige-par -> humain+ia
