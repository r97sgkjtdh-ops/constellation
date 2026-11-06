# Roles, groups and layouts

*[Version française](roles-et-equipes.md)*

## Groups

A group gathers consoles under a name and a colour. An order reaches it with `@group name`; `@Team A tous : …` sends the same text to each of its consoles. A group linked to an orchestrator card receives that card's orders.

## Roles

Each console or group can carry a role: General, Frontend, Backend, Tests, Review, Design, Documentation or Security.

**Today a role is a label.** It shows on the card and on the mission map, and the order planner reads it to split the work. It changes neither the console's tools, nor its permissions, nor its model: a “Review” console can write in the project like the others. For a review without writing, say so in the instruction, or use a mission.

## Layouts

A layout creates groups of consoles at once, sometimes with cards around them. They are in the board's layouts menu; “Save” keeps your own.

| Layout | What it creates |
|---|---|
| Développement | 1 general agent and a kanban |
| Binôme | 2 agents |
| Trio | 3 agents |
| Sprint | 4 agents, a kanban and an orchestrator |
| Web | 1 frontend, 1 backend and a localhost preview |
| Dev HQ | 2 frontend, 2 backend, 1 reviewer, a kanban, a preview and an orchestrator |
| Livraison | 2 agents, 1 tester and a release checklist |
| Bug Hunt | 2 testers, 2 reviewers and a kanban |
| Review Panel | 3 reviewers and an orchestrator |
| Sécurité | 2 security agents and 1 reviewer |
| Docs Sprint | 3 writers and a kanban |
| Design | 1 designer, 2 frontend and a preview |
| Tests | 3 testers and a checklist |
| Backend | 3 backend agents |
| Frontend | 3 frontend agents and a preview |
| Deux équipes | 2 groups of 3 agents and an orchestrator |
| Recherche | 3 researchers and 1 writer for the synthesis |
| Four Squads | 16 consoles in 4 squads, a kanban and an orchestrator |
