# Projet, dépôts et workflow

## Identité

- Produit : {{PROJECT_NAME}}
- Identifiant : {{PROJECT_SLUG}}
- Objectif et utilisateurs : {{PRODUCT_PURPOSE}}
- Langue utilisateur : {{UI_LANGUAGE}}
- Gestionnaire de tickets et projet : {{TRACKER_PROJECT}}

## Dépôts

Chemins relatifs au workspace, sans chemin de poste.

| Alias | Dépôt | Responsabilité | Branche de référence |
|---|---|---|---|
| api | {{API_REPOSITORY}} | Symfony / API Platform | {{API_BASE_BRANCH}} |
| web | {{WEB_REPOSITORY}} | Angular / PrimeNG | {{WEB_BASE_BRANCH}} |
| sdk (optionnel) | {{SDK_REPOSITORY}} | Client partagé | {{SDK_BASE_BRANCH}} |
| iac (optionnel) | {{IAC_REPOSITORY}} | Infrastructure | {{IAC_BASE_BRANCH}} |

## Git

Renseigner : branche source des fonctionnalités, nommage des branches et commits, stratégie de merge, branches protégées, revue requise et suppression des branches livrées. Ne pas supposer un flux `dev` / `prod`.

Dans les comptes rendus multi-dépôts, préfixer les branches et commits : `api:<branche>`, `web@<sha>`.

## Autorisations

Aucune permission opérationnelle n'est donnée par ce modèle. Compléter avec le développeur ; une entrée non renseignée ne vaut pas accord.

| Action | Périmètre autorisé et conditions |
|---|---|
| Commit local | {{COMMIT_POLICY}} |
| Push / force-push | {{PUSH_POLICY}} |
| Merge | {{MERGE_POLICY}} |
| Déploiement dev / recette | {{NONPROD_DEPLOY_POLICY}} |
| Lecture production | {{PROD_READ_POLICY}} |
| Écriture / déploiement production | Accord explicite du développeur pour l'action concernée |
| Réinitialisation de données locales / dev | {{DATA_RESET_POLICY}} |
| Notifications externes | Instruction explicite requise |

## Intégrations et données

Lister les tiers, leurs usages, les catégories de données transmises et les environnements sandbox. Préciser les contraintes de confidentialité et de conformité applicables sans présumer un contexte santé ou une certification.
