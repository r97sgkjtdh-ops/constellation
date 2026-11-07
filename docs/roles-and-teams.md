# Roles, groups and layouts

*[Version française](roles-et-equipes.md)*

## Groups

A group gathers consoles under a name and a colour. An order reaches it with `@group name`; `@Team A tous : …` sends the same text to each of its consoles. A group linked to an orchestrator card receives that card's orders.

## Roles

Each console or group can carry a role: General, Frontend, Backend, Tests, Review, Design, Documentation or Security.

**Since 0.3.31, a role changes what a Claude Code console does**, when the console starts:

| Role | Effect |
|---|---|
| General | None. |
| Frontend, Backend, Tests, Design, Documentation | A starting instruction for the role (for instance: write and run tests without changing the code's behaviour). |
| Review, Security | A starting instruction, and **read-only**: the console has no tool that changes a file. It reviews and writes a report. |

A console's own role comes before its group's. A new role applies at the console's next start. The order planner also reads the role, with its description, to split the work.

For Codex, Gemini CLI and the other CLIs, the role stays a label: they have no matching setting. A Codex “Review” console can therefore write; say so in the instruction.

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
