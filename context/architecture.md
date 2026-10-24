# Architecture et conventions

Décrire l'existant vérifié, en citant les chemins de code et les alias de dépôts. Les règles de stack proposées dans `AGENTS.md` restent à confirmer lors de l'adoption.

## Vue d'ensemble

Flux à confirmer : Angular / PrimeNG → contrat HTTP API Platform → Symfony / Doctrine → base de données. Ajouter SDK, workers, stockage et services tiers uniquement s'ils existent.

## Versions vérifiées

| Composant | Version | Source |
|---|---|---|
| PHP / Symfony / API Platform / Doctrine | {{BACKEND_VERSIONS}} | `composer.json`, `composer.lock` (api) |
| Angular / PrimeNG / TypeScript | {{FRONTEND_VERSIONS}} | `package.json` et lockfile (web) |
| Base de données | {{DATABASE_VERSION}} | Configuration d'exécution |

## API

Documenter ressources et domaines, providers/processors, identifiants et IRIs, formats et pagination, filtres et tris, validation, erreurs, authentification, autorisations par opération et filtrage des collections. Ajouter transactions, Messenger, tâches planifiées et stockage si utilisés.

Indiquer les conventions de migrations et les garanties d'idempotence des traitements ou webhooks concernés. Ne pas inventer de mécanisme de sécurité propre au projet.

## Front

Documenter routes et layouts, composants partagés, accès API (SDK ou services), types et erreurs, réactivité (signals/RxJS), détection des changements, formulaires, rendu SPA/SSR, thème PrimeNG et icônes. Préciser la gestion des dates, des fuseaux et de l'authentification.

## Contrat entre dépôts

Préciser comment les types sont maintenus, les changements compatibles ou cassants, l'ordre de livraison et les éventuels sous-modules ou paquets. Ne pas introduire un SDK uniquement parce que ce modèle comporte une ligne optionnelle pour lui.
