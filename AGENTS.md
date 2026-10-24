# {{PROJECT_NAME}} — règles permanentes

Documentation commune aux développeurs et aux agents. Lire ce fichier avant toute intervention. Les règles ci-dessous constituent le socle proposé ; les choix propres au projet sont précisés dans `context/`.

## Lecture et navigation

Au début d'une session : lire `team.md`, `decisions.md`, `pitfalls.md`, `context/project.md` et, s'il existe, `local/state.md`.

| Travail | Contexte à lire |
|---|---|
| API, front, contrat HTTP | `context/architecture.md` |
| Interface | `design-system.md` |
| Fonctionnalité métier | `context/product.md` |
| Exécution et tests | `context/local-development-and-tests.md` |
| Tickets et recette | `context/jira.md` |
| CI, infrastructure, livraison | `context/infra-deployment.md` |
| Procédure répétable | `runbooks/` |
| Cadrage ou session autonome | `prompts/` |

## Documentation

- Fichiers et dossiers en anglais (`kebab-case`), contenu en français. Code, identifiants, logs et messages de commit en anglais ; langue des interfaces à préciser dans `context/project.md`.
- Écrire des faits vérifiés. Distinguer une convention adoptée d'une hypothèse. Corriger ou supprimer immédiatement les informations devenues fausses.
- Les fichiers partagés décrivent ce qui est vrai aujourd'hui : pas de journal de session, de récit d'incident, de numéros de tickets temporaires ou de backlog. Une référence opérationnelle durable peut être conservée.
- Les noms des personnes figurent uniquement dans `team.md`. Ailleurs, utiliser leurs rôles. Aucun chemin propre à un poste dans les fichiers partagés ; citer les chemins relatifs au dépôt et son alias.
- Toute documentation persistante propre au projet reste ici. Aucun fichier d'outillage IA, plan ou journal dans les dépôts applicatifs.
- Tous les fichiers produits, notes personnelles, exports, captures et worktrees vont dans `local/`, ignoré par Git. Modèles vierges versionnés dans `templates/`.
- Aucun secret, jeton, mot de passe ou donnée personnelle réelle dans la documentation, les logs de travail ou les fixtures partagées. Référencer le gestionnaire de secrets sans lire son contenu inutilement.

## Méthode

- Vérifier l'état Git et le code avant de modifier. Préserver le travail des autres sessions. Ne pas utiliser `stash`, `reset` ou changer de branche dans un checkout partagé sans coordination.
- Préférer l'existant et les outils du framework. Faire la solution la plus simple qui satisfait le besoin ; pas d'abstraction ni de dépendance spéculative.
- Cadrer le résultat, limiter le périmètre et vérifier le résultat réel avant d'annoncer une réussite. Signaler les vérifications non exécutées et les échecs préexistants.
- Déléguer les tâches indépendantes quand cela est utile et disponible ; éviter les modifications et les tests concurrents sur une même ressource.
- Consulter les skills disponibles pertinents ; les conventions du projet et les instructions du développeur priment. Aucun plugin n'est une dépendance obligatoire de cette documentation.

## API : Symfony / API Platform

- API RESTful orientée ressources. Déclarer les opérations sur les entités ou des ressources DTO ; utiliser les providers et processors pour les lectures et écritures spécifiques.
- Utiliser les contraintes de validation, groupes de sérialisation et mécanismes de sécurité Symfony / API Platform. Appliquer les droits côté serveur, y compris sur les collections et après désérialisation lorsque nécessaire.
- Respecter les verbes et codes HTTP ; privilégier `PATCH` pour une mise à jour partielle. Écrire un agrégat par sa racine lorsqu'il porte une règle d'ensemble.
- Éviter les contrôleurs qui reconstruisent un contrat JSON ou lisent manuellement un corps déjà géré par API Platform. Une action non modélisable en ressource peut utiliser un contrôleur `__invoke` rattaché à l'opération ; documenter les exceptions justifiées.
- Générer les migrations via Doctrine, puis relire le SQL et l'impact sur les données. Ne jamais lancer une migration sans avoir identifié la base cible.
- Ne pas supposer l'existence d'une classe de contrôle d'accès, d'un générateur d'identifiants ou d'un SDK spécifique : consulter `context/architecture.md`.

## Front : Angular / PrimeNG

- Respecter les versions, conventions et composants du projet. Réutiliser les composants PrimeNG et les tokens du thème avant d'ajouter des composants ou styles maison.
- Centraliser l'accès à l'API dans la couche définie par `context/architecture.md` : SDK s'il existe, sinon services Angular typés. Gérer pagination, erreurs, chargement et absence de données.
- Ne pas changer implicitement la stratégie de réactivité, les formulaires, zone.js, SSR, les icônes ou les tests. Ces décisions sont propres au projet.
- Un guard front ou un bouton masqué ne remplace jamais une autorisation serveur. Assurer navigation clavier, labels, focus et lisibilité des erreurs.

## Autorisations et environnements

Les autorisations sont décrites dans `context/project.md`. Une autorisation doit venir du développeur ; ne pas la déduire d'une valeur de ce modèle. Les consignes explicites de la session restent applicables.

Avant une action partagée ou destructive, identifier le dépôt, la branche, l'environnement et les ressources concernés. Les environnements locaux et dev ne sont pas considérés comme jetables par défaut. Une production exige une autorisation explicite pour toute écriture ou livraison.

Ne pas envoyer de message externe sans instruction explicite. Ne jamais lire, copier ou indexer des dumps de production ou des clés privées pour enrichir le contexte.

## Fin de session

Mettre `local/state.md` à jour sans écraser les notes d'une autre session. Reporter uniquement les connaissances durables vérifiées dans les fichiers partagés. Après livraison, conserver les règles utiles et nettoyer le dossier de fonctionnalité devenu inutile, en préservant les preuves demandées.
