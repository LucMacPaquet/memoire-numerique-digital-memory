# Mémoire numérique — Règles Claude

> **Lire `AIOS/Me.md` en premier** : ce fichier contient le contexte personnalisé de l'utilisateur.

> **Vault optimisé Infinite Brain** : les types de notes et les types de liens sont documentés dans `AIOS/Note Types.md` et `AIOS/Edge Types.md`.

Toute nouvelle note durable doit avoir :

- un résumé en une phrase en tête : `> **Résumé en une phrase** : ...` ;
- un champ `type:` en français ;
- un champ `author:` ;
- une section `## Liens typés` en fin de note.

> [!warning] Règles absolues
>
> 1. Ne jamais modifier le contenu d'un fichier dans `raw/`.
> 2. Exception : après un `/ingest` réussi, déplacer la source traitée vers `archives/`.
> 3. Ne jamais supprimer une note wiki : archiver avec `status: archive`.
> 4. Ne jamais inventer une information absente du vault.
> 5. Capturer les idées échangées en conversation dans `Inbox.md` ou une note dédiée.
> 6. Ne pas supposer de contexte externe à ce vault.

> [!info] Standards de qualité des notes wiki
>
> 1. Une note wiki doit contenir assez d'information pour comprendre le sujet sans retourner à la source.
> 2. Une note trop courte doit être enrichie depuis l'archive ou signalée dans le rapport.
> 3. Toute note dérivée d'une source archivée doit inclure `dérivé-de → [[archives/chemin/fichier.md]]` dans `## Liens typés`.
> 4. Si une source parle d'une idée, créer une note dans `wiki/idées/` avec le format `(YYYY-MM-DD_HHhMM)-(nom-de-l-idee).md`.

## Structure wiki

| Dossier | Contenu |
| --- | --- |
| `wiki/index.md` | Panneau de direction à lire en premier |
| `wiki/log.md` | Journal append-only |
| `wiki/Context/` | Profil, contexte, objectifs et projets |
| `wiki/Daily/` | Notes quotidiennes |
| `wiki/Intelligence/` | Recherches, décisions, analyses |
| `wiki/Projets/` | Notes détaillées par projet |
| `wiki/Resources/` | Guides, méthodes, ressources réutilisables |
| `wiki/Contacts/` | Contacts et organisations |
| `wiki/idées/` | Idées créées pendant `/ingest` |

## Opérations

| Commande | Quand |
| --- | --- |
| `/prime` | Début de session |
| `/ingest` | Après ajout dans `raw/` |
| `/save` | Fin de session |
| `/query` | Recherche dans le wiki |
| `/lint` | Entretien périodique |

Chaque projet peut avoir son propre fichier technique, mais ce vault reste la mémoire centrale.
