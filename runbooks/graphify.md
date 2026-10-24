# Navigation par graphe (optionnelle)

Ce modèle ne fournit pas de script de génération. Activer cette procédure uniquement si le projet utilise un outil de graphe et après vérification de son fonctionnement.

- Périmètre : uniquement le code autorisé, jamais les dumps, secrets, clés ou exports.
- Sorties générées : `local/graphify/<repository>/<branch>/`.
- Référencer le commit source et vérifier la fraîcheur avant analyse.
- Le graphe aide à naviguer ; le code de la branche analysée reste la référence.
- Ne pas envoyer le code à un service externe sans autorisation appropriée.

Commande de génération et vérification validée : {{GRAPH_COMMANDS}}

Supprimer ce runbook si inutile et retirer ses références éventuelles.
