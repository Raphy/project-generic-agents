# Infrastructure, CI et déploiement

À renseigner selon l'hébergement réel. Docker, Kubernetes, Helm, Kustomize et un fournisseur cloud ne sont pas imposés.

## Cartographie

| Environnement | Applications / URL | Infrastructure | Source de configuration |
|---|---|---|---|
| {{ENVIRONMENT}} | {{APPLICATIONS}} | {{HOSTING}} | {{CONFIGURATION_PATH}} |

## CI et artefacts

Documenter les déclencheurs, contrôles, registres, tags immuables et liens permettant d'identifier le commit exact d'un artefact. Préciser où les tests tournent réellement.

## Livraison

Suivre `runbooks/deployment.md`. Renseigner les commandes validées, l'ordre API/front/workers, les migrations, les vérifications fonctionnelles et le rollback. Un marqueur n'est jamais une commande exécutable.

Si Kubernetes est utilisé : contexte et namespace explicites à chaque commande, jamais de changement global de contexte sur un poste partagé. Prévisualiser les changements avant application.

## Exploitation

{{HEALTH_CHECKS_AND_OBSERVABILITY}}

{{BACKUP_AND_RESTORE_REFERENCES}}

Référencer les procédures de sauvegarde sans ouvrir ni indexer leurs contenus. Identifier les traitements en cours et les impacts d'un redémarrage.
