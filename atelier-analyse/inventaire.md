# Inventaire des points d'entrée

Le livrable de l'atelier d'analyse. Il dit ce que l'API devra **permettre** — pas comment on
l'écrira.

Une règle : tout ce qui figure ici doit se justifier par la lettre de mission ou par un écran
des maquettes. Si vous ne savez plus d'où vient une ligne, c'est peut-être qu'elle n'en vient
pas. (Seule exception : la section bonus, si vous en ajoutez une.)

---

## Ce que l'utilisateur peut faire

Une action par ligne, en français. Pas encore de chemins.

- L'utilisateur non connecté peut rechercher des trajets (sélectionner différentes villes, dates, nb voyageurs)
- L'utilisateur non connecté peut consulter la liste des résultats 
- L'utilisateur peut consulter le détail d'un trajet
- L'utilisateur peut créer un compte 
- L'utilisateur peut se connecter à son compte.
- L'utilisateur connecté peut ajouter des trajets à son panier.
- L'utilisateur connecté peut consulter son panier .
- L'utilisateur connecté peut supprimer des trajets de son panier .
- L'utilisateur connecté peut payer par carte bancaire / bon de transport.
- L'utilisateur connecté peut consulter ses réservations confirmées.
- L'utilisateur connecté peut consulter son compte


## Les points d'entrée

| Ce que ça fait                        | Chemin proposé                 | Qui peut l'appeler |
|---------------------------------------|--------------------------------|---|
| Rechercher des trajets et afficher les résultats | `GET /trajets`                 | Public |
| Consulter les détails d'un trajet     | `GET /trajets/{id}`            | Public |
| Créer un compte                       | `POST /utilisateurs`           | Public |
| Se connecter                          | `POST /connexion`              | Public |
| Consulter les informations de son compte | `GET /profil`                  | Utilisateur connecté |
| Consulter le contenu de son panier    | `GET /panier`                  | Utilisateur connecté |
| Ajouter un trajet au panier           | `POST /panier/articles`        | Utilisateur connecté |
| Supprimer un trajet du panier         | `DELETE /panier/articles/{id}` | Utilisateur connecté |
| Valider le panier et payer            | `POST /réservations`           | Utilisateur connecté |
| Consulter ses réservations confirmées | `GET /réservations`            | Utilisateur connecté |

## Les données qui circulent


| Nom du point d'entrée                            | Reçoit | Renvoit |
|--------------------------------------------------|-|--|
| Rechercher des trajets et afficher les résultats | nom villes, dates | deux villes, la dates du trajets, nb voyageurs |
| Consulter les détails d'un trajet                | franchise de masse, catapulte type | rien |
| Créer un compte                                  | | nom, prénom, adresse mail, mot de passe |
| Se connecter                                     | |  |
| Consulter les informations de son compte         | |  |
| Consulter le contenu de son panier               |  |  |
| Ajouter un trajet au panier                      |  |  |
| Supprimer un trajet du panier                    |  |  |
| Valider le panier et payer                       |  |  |
| Consulter ses réservations confirmées            |  |  |


## Ce dont on n'est pas sûrs

Les questions que la lettre et les maquettes ne tranchent pas. Une question notée vaut mieux
qu'une réponse inventée.