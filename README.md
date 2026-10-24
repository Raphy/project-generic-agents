# Modèle de documentation agents

Modèle de dépôt autonome pour une API Symfony / API Platform et un front Angular / PrimeNG. Documentation partagée entre développeurs et agents, indépendante de l'outil utilisé.

## Installer pour un projet

1. Créer un dépôt à partir de ce modèle, nommé `<project-slug>-agents`.
2. Le cloner à côté des dépôts applicatifs. Un monorepo peut conserver la même séparation avec ce dépôt documentaire voisin.
3. Remplacer les marqueurs `{{...}}` par les informations vérifiées du projet. Supprimer les sections optionnelles inutiles ; conserver « Non renseigné » pour les inconnues. Ne jamais inventer une configuration.
4. Renseigner en priorité `AGENTS.md`, `context/project.md`, `context/architecture.md`, `context/local-development-and-tests.md` et `team.md`.
5. Décider explicitement du workflow Git et des autorisations dans `context/project.md`. Le modèle ne donne aucune autorisation de push, merge ou déploiement.
6. Créer le dossier personnel `local/` et copier `templates/state.md` vers `local/state.md`.
7. Dans la configuration de workspace propre au poste, ajouter l'instruction ci-dessous. Ne pas ajouter de documentation d'outillage IA dans les dépôts applicatifs.

```text
Avant toute intervention, lire <project-slug>-agents/AGENTS.md,
puis les fichiers de contexte qu'il indique.
Toute documentation de travail persistante propre au projet doit être
placée dans <project-slug>-agents/. Les notes et fichiers produits vont dans local/.
```

Arborescence recommandée :

```text
workspace/
├── <project-slug>-agents/
├── <project-slug>-api/
├── <project-slug>-web/
├── <project-slug>-sdk/       # optionnel
└── <project-slug>-iac/       # optionnel
```

## Personnaliser

Les conventions de stack sont des règles proposées par le modèle, pas la description d'un code déjà inspecté. Les confirmer lors de l'adoption. Versions, moteur SQL, hébergeur, CI, conteneurs, SDK, authentification, stratégie Angular (zone.js ou zoneless, SSR, formulaires) et outils de tests restent à vérifier dans chaque projet.

Les workflows spécifiques à une organisation, les données métier, les comptes, les domaines, les secrets et les permissions d'un projet source ne sont pas repris. Les procédures de chiffrement, Kubernetes et Graphify sont facultatives ; aucun script lié à une infrastructure particulière n'est embarqué.

## Entretenir

Les fichiers partagés décrivent l'état durable vérifié. Le backlog reste dans le gestionnaire de tickets, l'historique dans Git et l'état de session dans `local/state.md`. Les noms de fichiers sont en anglais, le contenu en français. Ce modèle ne fournit pas de licence : choisir une licence avant sa diffusion publique.
