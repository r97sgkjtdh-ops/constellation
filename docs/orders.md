# Giving orders to consoles

*[Version française](ordres.md)*

The command bar (⌘K) sends an order to one or more consoles of the board. An orchestrator card does the same, but only for the consoles and groups linked to it.

## Four ways to write an order

| You type | What happens |
|---|---|
| `Claude 2, add tests to the parser` | A console's name, then a comma: the text goes unchanged to that console. |
| `@Claude 2 add tests` | The same with `@`, anywhere in the sentence. |
| `@Team A tous : review your last commit` | `tous :` sends the same text to every console of the group or of the named consoles. |
| `Add a login page and its tests` | No name: the planner splits the work between the consoles and shows you a plan before anything is sent. |

When two consoles or groups share a name, the order is refused: give the exact name with `@`.

## Board commands

These sentences are handled by Constellation, without the planner:

- `crée 4 agents Codex` (or `lance`, `ouvre`, `ajoute`): creates consoles, 12 at most;
- `ouvre l'espace 2`: shows another workspace;
- `passe cette tâche à codex`: the selected console sums up its work, and a new console of the chosen CLI takes it over.

## The plan

Without a console's name, the planner (a call to Claude Code, without tools) proposes steps: one instruction per console. **Nothing is sent before you click “Send this plan”.** Until then you can:

- change a step's console or its instruction;
- remove a step, or add one;
- choose what a step waits for (“After …”): it starts once those steps are done, with their reports;
- tick “Final report, after the others” on a single step.

A plan whose waits loop is refused. A console running without permissions is flagged in orange: it will act on what it receives without asking you.

## The final step

The final step waits for all the others. It receives their full reports in a `.constellation/comptes-rendus-….md` file in its console's folder, kept out of Git and removed after 7 days. The other consoles are told their report will be passed on.

If a step did not finish (failure, time limit, console stopped), the final step waits for your go-ahead: “Launch the final step anyway”, or cancel.

The reports passed on are presented to the console as material to summarise, not instructions, and the secrets it recognises are masked.

## A step's states

| State | Meaning |
|---|---|
| queued, waiting for the start | Not sent yet. |
| waiting for the other consoles to finish | A final step, or a step waiting for others. |
| waiting for the console to finish another order | The console is already working on another order: this one comes after. |
| waiting for you | The console asks for a permission or a question. |
| sent, running | The agent is working. |
| done | The agent finished its turn; its report is attached. |
| time limit passed, console stopped, interrupted | Ended without a full report: what was read is kept, marked partial. |
| failed | API error (limit, overload, network): the console shows TURN FAILED. |
| not sent | The console was not ready (paused, shell, permission pending…). |

A step that ended, failed or was not sent can be **relaunched**, on the same console or another one. **Cancelling** an order also stops the agents working on it, as Esc does, and keeps their partial report.

Orders stay after the app restarts. What was running when it quit is marked interrupted and can be relaunched. “Clear” removes them from the thread without deleting them.

## Limits

- A step's time limit is 30 minutes, not counting the time spent waiting for your answer to a permission.
- For CLIs other than Claude Code, the end of a turn is guessed after 6 seconds without output, and the report is the end of the screen.
- The planner needs Claude Code and takes up to 3 minutes.
