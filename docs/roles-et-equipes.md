# Rôles, groupes et dispositions

*[English version](roles-and-teams.md)*

## Groupes

Un groupe rassemble des consoles sous un nom et une couleur. On l'adresse dans un ordre avec `@nom du groupe` ; `@Équipe A tous : …` envoie le même texte à chacune de ses consoles. Un groupe relié à une carte orchestrateur reçoit les ordres de cette carte.

## Rôles

Chaque console ou groupe peut porter un rôle : Général, Frontend, Backend, Tests, Revue, Design, Documentation ou Sécurité.

**Depuis la 0.3.31, un rôle change ce que fait une console Claude Code**, au démarrage de la console :

| Rôle | Effet |
|---|---|
| Général | Aucun. |
| Frontend, Backend, Tests, Design, Documentation | Une consigne de départ propre au rôle (par exemple : écrire et lancer des tests sans changer le comportement du code). |
| Revue, Sécurité | Une consigne de départ, et **lecture seule** : la console n'a aucun outil qui modifie un fichier. Elle relit et rend un compte rendu. |

Le rôle d'une console passe avant celui de son groupe. Changer de rôle s'applique au prochain démarrage de la console. Le planificateur des ordres lit aussi le rôle, avec sa description, pour répartir le travail.

Pour Codex, Gemini CLI et les autres CLI, le rôle reste une étiquette : ils n'ont pas de réglage équivalent. Une console « Revue » Codex peut donc écrire ; dis-le dans la consigne.

## Dispositions

Une disposition crée d'un coup des groupes de consoles, et parfois des cartes autour. Elles sont dans le menu des dispositions du tableau ; « Sauvegarder » enregistre la tienne.

| Disposition | Ce qu'elle crée |
|---|---|
| Développement | 1 agent général et un kanban |
| Binôme | 2 agents |
| Trio | 3 agents |
| Sprint | 4 agents, un kanban et un orchestrateur |
| Web | 1 frontend, 1 backend et un aperçu localhost |
| Dev HQ | 2 frontend, 2 backend, 1 relecteur, un kanban, un aperçu et un orchestrateur |
| Livraison | 2 agents, 1 testeur et une checklist de sortie |
| Bug Hunt | 2 testeurs, 2 relecteurs et un kanban |
| Review Panel | 3 relecteurs et un orchestrateur |
| Sécurité | 2 agents sécurité et 1 relecteur |
| Docs Sprint | 3 rédacteurs et un kanban |
| Design | 1 design, 2 frontend et un aperçu |
| Tests | 3 testeurs et une checklist |
| Backend | 3 agents backend |
| Frontend | 3 agents frontend et un aperçu |
| Deux équipes | 2 groupes de 3 agents et un orchestrateur |
| Recherche | 3 chercheurs et 1 rédacteur pour la synthèse |
| Four Squads | 16 consoles en 4 escouades, un kanban et un orchestrateur |
