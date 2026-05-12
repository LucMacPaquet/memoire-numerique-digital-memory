---
date: 2026-05-09
tags: [ressource, requis, installation, outils-ia]
type: référence
status: active
author: humain+claude
---

# 01 - Requis

> **Résumé en une phrase** : Le kit demande Obsidian, un dossier vault, au moins un outil IA compatible et, idéalement, un service de synchronisation de fichiers.

## Requis essentiels

| Élément | Obligatoire ? | Rôle |
| --- | --- | --- |
| Obsidian | Oui | Lire, visualiser et naviguer dans le vault Markdown |
| Dossier vault | Oui | Contenir `raw/`, `wiki/`, `archives/`, `AIOS/` et les notes |
| Au moins un outil IA | Oui | Maintenir la mémoire numérique structurée |
| Node.js/npm | Souvent | Installer plusieurs outils IA CLI |
| Service de synchronisation | Non, mais fortement utile | Accéder au vault sur plusieurs appareils |
| Obsidian Web Clipper | Non, mais recommandé | Capturer le web vers `raw/clippings/` |

Tous les outils IA ne sont pas nécessaires. Il faut en choisir au moins un : Claude Code CLI, Gemini CLI, Codex CLI ou OpenCode.

## Fichiers du kit à mettre en place

Le dossier `Kit bootstrap/` contient les gabarits génériques à copier dans un nouveau vault. C'est la source de vérité du kit de départ : l'utilisateur n'a pas à réécrire les règles, les cartes AIOS ou les skills à la main.

Le kit contient notamment :

- `AGENTS.md` et `CLAUDE.md` pour les règles de base des agents IA ;
- `AIOS/Me.md` comme gabarit à personnaliser ;
- `AIOS/Vault Map.md`, `AIOS/Skills Map.md`, `AIOS/Note Types.md`, `AIOS/Edge Types.md` et `AIOS/Codex Config.md` ;
- `skills/README.md`, `skills/prime.md`, `skills/ingest.md`, `skills/save.md`, `skills/query.md`, `skills/lint.md` ;
- des skills complémentaires inclus dans le kit de base : `skills/analyse/` et `skills/json-canvas/`.

Ces fichiers sont volontairement génériques. Ils utilisent des placeholders comme `<NOM>`, `<RÔLE>`, `<DOMAINES>`, `<PROJETS_ACTIFS>` et `<PRÉFÉRENCES_DE_TRAVAIL>`, que l'outil IA remplacera seulement après validation avec l'utilisateur.

## Installation des outils IA

### Claude Code CLI

```bash
npm install -g @anthropic-ai/claude-code
```

Source : [Anthropic — Claude Code getting started](https://docs.anthropic.com/en/docs/claude-code/getting-started)

### Gemini CLI

```bash
npm install -g @google/gemini-cli
```

Source : [Gemini CLI — Get started](https://google-gemini.github.io/gemini-cli/docs/get-started/)

### Codex CLI

```bash
npm install -g @openai/codex
```

Source : [OpenAI — Codex CLI getting started](https://help.openai.com/en/articles/11096431-openai-codex-cli-getting-started)

### OpenCode

```bash
curl -fsSL https://opencode.ai/install | bash
```

ou :

```bash
npm install -g opencode-ai
```

Source : [OpenCode docs](https://opencode.ai/docs/)

## Obsidian

Installer Obsidian depuis le site officiel et ouvrir le dossier du vault comme vault Obsidian. Il n'est pas nécessaire d'avoir un outil CLI Obsidian pour commencer.

Source : [Obsidian — Create a vault](https://help.obsidian.md/vault)

## Synchronisation

Un service de synchronisation est optionnel, mais fortement utile. Il permet de retrouver la mémoire sur plusieurs appareils et de capturer depuis un autre poste. OneDrive est un exemple, mais ce rôle peut aussi être joué par iCloud Drive, Dropbox, Syncthing, Git ou un autre service adapté.

Source : [Microsoft — Sync files with OneDrive](https://support.microsoft.com/en-us/office/sync-your-computer-s-files-and-folders-with-onedrive-615391c4-2bd3-4aae-a42a-858262e42a49)

## Sécurité

- Installer les outils depuis les sources officielles.
- Éviter les scripts inconnus, forks suspects ou faux paquets npm.
- Ne jamais écrire de clés API ou secrets dans les notes.
- Documenter les dépendances, pas les valeurs secrètes.

## Liens typés

- fait-partie-de → [[Fonctionnement-complet-du-vault-Obsidian-AIOS]]
- soutient → [[00-Description-de-la-memoire-numerique]]
- soutient → [[12-Choix-des-modeles-IA]]
- rédigé-par → humain+claude
