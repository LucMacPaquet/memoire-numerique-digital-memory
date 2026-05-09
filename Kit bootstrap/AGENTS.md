# Mémoire numérique — Règles agents

> [!warning] Règles absolues
>
> 1. Ne jamais modifier le contenu d'un fichier dans `raw/`.
> 2. Exception : après un `/ingest` réussi, déplacer la source traitée vers `archives/`.
> 3. Ne jamais supprimer une note wiki : archiver avec `status: archive`.
> 4. Ne jamais inventer une information absente du vault.
> 5. Capturer les idées échangées en conversation dans `Inbox.md` ou une note dédiée.
> 6. Pendant `/ingest`, si une source parle d'une idée, créer une note dans `wiki/idées/` avec le format `(YYYY-MM-DD_HHhMM)-(nom-de-l-idee).md`.

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
