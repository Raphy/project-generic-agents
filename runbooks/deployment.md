# Livrer une version

Procédure à adapter aux commandes validées de `context/infra-deployment.md`.

1. Identifier l'environnement, le périmètre, les autorisations et les autres sessions utilisant les mêmes ressources.
2. Vérifier Git, le diff, les commits exacts, les dépendances entre dépôts et les versions actuellement déployées.
3. Exécuter les contrôles requis sur les commits à livrer et vérifier la CI et les artefacts correspondants.
4. Relire les migrations, leur compatibilité et leur mode d'exécution ; vérifier les prérequis de sauvegarde sans lire les dumps.
5. Préparer le changement de configuration, son aperçu et le retour arrière. Une migration de données n'est pas annulée par un rollback d'image.
6. Appliquer la livraison uniquement dans le périmètre autorisé, avec une cible explicite.
7. Vérifier démarrage, santé, erreurs, workers et parcours touchés. En cas d'échec, appliquer le retour arrière prévu ou demander la décision nécessaire.
8. Mettre à jour `local/state.md` avec les versions et preuves. Mettre à jour les tickets et communiquer seulement selon les instructions reçues.

## Commandes propres au projet

{{DEPLOYMENT_COMMANDS}}

## Retour arrière

{{ROLLBACK_COMMANDS_AND_LIMITATIONS}}
