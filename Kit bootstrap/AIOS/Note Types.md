# Types de notes - Reference

> **Resume en une phrase** : Les 16 types de notes donnent a chaque note durable un role clair afin que l'agent IA puisse classer, filtrer et relier la memoire sans tout relire.

## Convention

Le champ `type:` du frontmatter accepte uniquement les valeurs ci-dessous.

## Les 16 types

| Type | Quand l'utiliser | Exemple generique |
| --- | --- | --- |
| `pilier` | Principe fondateur, domaine majeur, projet structurant | Strategie personnelle, portefeuille de projets |
| `décision` | Choix pris avec contexte et consequences | Choix d'un outil, abandon d'une option |
| `concept` | Idee, modele mental, theorie ou notion abstraite | Methode de priorisation, modele de veille |
| `question` | Interrogation ouverte ou point a clarifier | Faut-il automatiser cette etape ? |
| `processus` | Procedure repetable ou mode operatoire | Processus `/ingest`, rituel hebdomadaire |
| `tâche` | Action ponctuelle a faire ou a suivre | Appeler un fournisseur, valider une hypothese |
| `événement` | Evenement date ou journal quotidien | Daily note, rencontre, jalon |
| `schéma` | Pattern observe, synthese transversale | Themes recurrents dans plusieurs sources |
| `hypothèse` | Idee a tester, non encore validee | Un segment d'utilisateurs serait prioritaire |
| `fait` | Donnee verifiee avec source claire | Chiffre, date, resultat, contrainte confirmee |
| `source` | Article, livre, video, document ou conversation source | Capture web traitee, document analyse |
| `signet` | Reference a consulter plus tard | Page a lire, outil a evaluer |
| `note` | Capture libre ou note courte structuree | Observation, pensee, brouillon |
| `contact` | Personne, equipe, organisation ou agent | Contact client, partenaire, expert |
| `référence` | Documentation stable ou manuel | Guide, syntaxe, aide-memoire |
| `personnalisé` | Cas rare qui ne correspond a aucun autre type | Exception documentee |

## Regle pour `/ingest`

L'agent IA choisit le type le plus probable si l'utilisateur ne le precise pas. En cas d'incertitude, il choisit un type utile, signale l'incertitude dans son rapport et ajoute une question de validation si necessaire.

## Regles de qualite

- Une note ne doit avoir qu'un seul `type:`.
- Le type doit aider a comprendre le role de la note, pas seulement son dossier.
- Le type `personnalisé` doit rester rare.
- Les daily notes utilisent `événement`.
- Les guides et manuels utilisent souvent `processus` ou `référence`.
- Les notes issues d'une capture web peuvent etre `source`, sauf si l'agent en fait une synthese conceptuelle.

## Liens types

- fait-partie-de -> [[AIOS/Vault Map]]
- soutient -> [[AIOS/Edge Types]]
- soutient -> [[skills/ingest]]
- redige-par -> humain+ia
