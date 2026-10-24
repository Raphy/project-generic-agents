# Développement local et vérification

## Environnement

| Élément | Configuration vérifiée |
|---|---|
| Prérequis et installation | {{LOCAL_PREREQUISITES}} |
| Exécution hôte / conteneurs | {{EXECUTION_POLICY}} |
| Démarrage et arrêt | {{START_STOP_COMMANDS}} |
| URL et ports | {{LOCAL_URLS}} |
| Variables et secrets (emplacements seulement) | {{ENV_CONFIGURATION}} |
| Base de développement | {{LOCAL_DATABASE}} |
| Base de tests isolée | {{TEST_DATABASE}} |
| Comptes synthétiques (sans mot de passe) | {{TEST_ACCOUNTS_REFERENCE}} |

Ne pas supposer les noms de services Docker ou l'utilisateur PHP. Vérifier la cible avant une migration ou un chargement de fixtures. Ne pas arrêter une pile partagée à la fin d'une session sans demande.

## Commandes validées

Remplacer les marqueurs par les commandes réellement disponibles dans les scripts Composer, npm et la CI, en précisant le répertoire et le contexte d'exécution.

| Vérification | Commande et contexte |
|---|---|
| Qualité PHP / analyse statique | {{PHP_QUALITY_COMMAND}} |
| Tests unitaires PHP | {{PHP_UNIT_COMMAND}} |
| Tests intégration / API | {{API_TEST_COMMAND}} |
| Tests comportementaux, si utilisés | {{BEHAVIOR_TEST_COMMAND}} |
| Build Angular | {{FRONT_BUILD_COMMAND}} |
| Lint / format front | {{FRONT_QUALITY_COMMAND}} |
| Tests front, si utilisés | {{FRONT_TEST_COMMAND}} |
| Parcours navigateur | {{E2E_COMMAND}} |

## Stratégie

Choisir les contrôles selon le risque et les conventions adoptées : logique isolée, intégration Symfony, contrat HTTP et droits (autorisé/refusé), parcours utilisateur. Documenter les suites réellement utilisées et leur fréquence ; ni interdiction des tests Angular ni outil de test imposé par ce modèle.

Isoler les bases et les effets externes ; utiliser des sandboxes et des données synthétiques. Coordonner les tests lourds et les resets sur les environnements partagés. Rapporter les contrôles exécutés, leurs résultats et les limites.
