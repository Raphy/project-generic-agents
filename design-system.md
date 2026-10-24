# Interface et design system

À compléter après inspection du front. Réutiliser l'existant ; les indications ci-dessous sont des conventions proposées à confirmer.

| Élément | Référence du projet |
|---|---|
| Thème PrimeNG et configuration | {{THEME_PATH}} |
| Tokens couleurs, espacements, typographie | {{TOKENS_PATH}} |
| Icônes | {{ICON_SYSTEM}} |
| Layouts et composants partagés | {{SHARED_COMPONENTS_PATH}} |
| Écrans de référence | {{REFERENCE_SCREENS}} |
| Langue, formats de date et fuseau | {{UI_LOCALE}} |

## Règles proposées

- Utiliser les tokens du thème plutôt que des couleurs en dur.
- Prévoir les états chargement, vide, erreur, succès et accès refusé.
- Associer labels et champs, rendre les actions accessibles au clavier, gérer le focus des dialogs et la lisibilité des erreurs.
- Réutiliser les conventions des tableaux, filtres, pagination, formulaires, menus et confirmations.
- Vérifier le rendu responsive sur les tailles ciblées par le projet.

## Choix à documenter

Composants de formulaires et de dates, actions destructives, notifications, overlays, thème sombre éventuel et contraintes d'accessibilité. Ne pas reprendre de palette ou d'exception d'un autre produit sans décision.
