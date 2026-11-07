# Changelog

*[Version française](CHANGELOG.md)*

What each published version brought, newest first. Before 0.3.0, versions were not published.

## 0.3.31 (2026-11-07)

### New
- **Roles that really change the behaviour** (Claude Code): each role gives a starting instruction, and **Review** and **Security** work read-only, with no tool that changes a file. The order planner reads the role's description.
- **Mission templates**: six templates ready to complete (fix a bug, new feature, audit, documentation, web research, restructuring), and your own templates. A template never carries the connectors, your agreement to external sources or the approval of the checks.
- **“Redo” a mission** also takes back its mode, limits, isolation and web.
- **Order history**: every order, even cleared from the thread, with search, details and a Markdown export without secrets.
- **Same file edited**: two Claude consoles editing the same file within half an hour are flagged.
- **Log kept on disk** (7 days, without secrets), and an abrupt stop is flagged at the next launch, with a diagnostic that attaches macOS's crash report.
- **Notifications signed Constellation**: a finished turn is reported by Constellation. In the consoles and missions it launches, the ECC plugin's "Claude Code" notification is turned off; it stays on in your Terminal.
- **Lighter top bar**: the quota and the usage are now a single button.
- **Settings redone**: a sidebar with search, like macOS's System Settings, and new sections. **Board**: size of new consoles, animated, still or no background network. **Notifications**: each kind of event set apart, with or without sound, and the Dock badge. **Confirmations**: you can stop being asked before stopping a console or quitting. **Data**: export, import or reset the settings, create a diagnostic, open the log. **About**: the credits (Vel, with the GitHub link) and the open-source software used.

### Fixes
- **Console counter**: it could count consoles from test projects left in the data by the automatic captures. Captures now keep everything in their throwaway folder.
- **Settings › Updates**: "From the code on this Mac" no longer shows in a published app, which could not use it.

### Good to know
- **Checked**: the test suite on this Mac (870 tests, 16 skipped, no failures); the role options with the real Claude Code; the "same file" warning with the real script, which keeps only the file's path. GitHub did not run its checks (the month's minutes are used up).
- **Checked by captures**: every section of the new Settings, in French and English.
- **Not checked on screen**: mission templates, the order history, the "same file" warning and the new notifications. If something gets stuck, open an issue.
- **Changing a console's role** applies at its next start. For Codex and Gemini, the role stays a label.

## 0.3.30 (2026-11-06)

### Fixes
- **An order's plan**: the "Final report" box and the "After …" menu are the same size as the rest of the editor. They were larger.
- **Console list**: the time reads "3 min ago", instead of "since 3 min ago".

### Good to know
- **Presentation**: screenshots of an order's plan and of the console list, guides, frequently asked questions and the changelog on the project page.
- **Checked**: the test suite (851 tests, 16 skipped, no failures), on this Mac and on GitHub.

## 0.3.29 (2026-11-06)

### Orders to several consoles
- **The plan can be edited before sending**: console, instruction, adding or removing a step, final step.
- **A step can wait for others** (“After …”) and receives their reports: for instance, write then have it reviewed.
- **A finished or failed step can be relaunched**, on the same console or another one.
- **Reports say how the step ended**: time limit, console stopped, interrupted or API error, in orange, instead of “done”. The final step waits for your go-ahead if a step did not finish.
- **Cancelling stops the agents** working on the order. Two orders to the same console run one after the other.
- **Orders stay after a restart**; “Clear” hides them without deleting them.

### Consoles and board
- **TURN FAILED** instead of READY after an API error; a console that stopped on an error code is red.
- **“Stuck?”** on a console working without any sign for 10 minutes, with Interrupt and Restart.
- **Restart on the same conversation**, instead of always starting over.
- **macOS notifications** in the background and the number of consoles waiting for you on the Dock icon (Settings › Appearance).
- **⌘P “Go to a card”**, **a list of all consoles** when you click their counter, and **“Undo”** after a deletion.

### Security
- Mission agents no longer receive your tokens (GitHub, cloud). Checks no longer read your personal folders. The no-permissions mode ends with the app. A Web card only opens web pages.
- An order's plan flags a console without permissions, and the reports passed on are presented as data, secrets masked.
- A mission's header names the permissions of your Claude Code settings, which add to the mission's.

### Updates
- The update shows the notes of **every version skipped**.
- **Go back to an earlier version** from Settings › Updates.
- A withdrawn version is no longer offered.

### Good to know
- **Checked**: the test suite (851 tests, 16 skipped, no failures), on this Mac and on GitHub, green again; the real trials with Claude Code on `.git`, `.Claude` and reading outside the project.
- **Not checked on screen**: the plan editor, notifications, ⌘P, the console list and going back to an earlier version. If something gets stuck, open an issue.
- **A project kept in Documents** whose tests read a neighbouring folder: those tests now fail in the sandbox.
- New guides: giving orders, roles and teams, and ten examples.

## 0.3.28 (2026-11-06)

### Fix
- **Updates that no longer came**: in 0.3.23, the "GitHub repository" box of the update page could still be typed into. A name typed there stayed saved and came before the official repository. The app then looked for updates in a repository that does not exist, with no way to fix it, since the box has been read-only since 0.3.24. A published app now always looks in its own repository.

### Good to know
- **If your app has not offered an update since 0.3.24**, this version cannot reach you by itself, as the old version is the one looking. Install it once by hand from this page: the next ones will come by themselves.
- **Checked**: the test suite (816 tests, 16 skipped, no failures).
- **Reminder from 0.3.27**: an order to several consoles can end with a common report, which waits for the others and gets their full reports. Also tried with the real planner on four squads of four consoles.

## 0.3.27 (2026-11-06)

### Fix
- **A common report from several teams**: when you gave an order to several consoles, every step was sent at the same time and the consoles could not see each other. The final report was therefore sent without the other teams' work. Now the orchestrator adds a final step when your request calls for a common report, synthesis or review. It is marked "after the others" in the plan and is sent only once every other console is done.
- **Full reports**: the final console gets each console's whole report, in a `.constellation/comptes-rendus-….md` file of the project, kept out of Git. For a Claude Code console it is its whole last answer. For the other tools it is the end of the screen. Each team knows who its report goes to.

### Good to know
- **Checked**: the test suite (815 tests, 16 skipped, no failures), including a 500-line report found whole, and a trial with the real planner: two teams of three consoles, then a common report.
- **Not checked**: the complete run with real consoles on the board. If something gets stuck, open an issue.

## 0.3.26 (2026-11-06)

### Fixes
A full analysis of the app, run by a 13-agent Constellation mission, found 10 serious defects. They are all fixed.

**Security**
- **Settings of a downloaded project**: missions no longer apply the Claude Code settings kept in the project (`.claude/settings.json`). A trapped project could run commands on your Mac as soon as a mission started. The project's `CLAUDE.md` is still handed to the agents.
- **Project tests**: when the sandbox is on, agents no longer run the project's tests themselves. Only Constellation runs them, in the sandbox. Before, an agent could write a test and then run it outside the sandbox, with access to your keys.

**Losing nothing**
- **An update that crashes**: if the new version does not stay open, the previous one is put back and reopened by itself. The new one is kept in the backup.
- **Damaged mission history**: its backup copy is put back, with a message. The project is no longer blocked.
- **A Git repository kept inside the project**: the work done in it is now delivered. Before, the task was reported successful with nothing delivered.

**Comfort and accessibility**
- **Plan checks**: what you type stays as typed. Spaces and new lines vanished while typing.
- **Less work at rest**: consoles no longer make every card redraw twice a second, and a Folder card reads 2,000 items at most, reading nothing again while the app is in the background.
- **VoiceOver** announces a console that needs you or failed, a mission waiting for a decision and a finished mission.
- **Agents' language**: until you choose one, it is the interface's. On an English Mac, agents answered in French.

### Good to know
- **Checked**: the test suite (809 tests, 16 skipped, no failures), two short real missions that succeeded, and the blocking of project settings tried with the real Claude Code.
- **Not checked**: on screen, the checks editor, the VoiceOver announcements and the Folder card. Going back to the previous version was only tried with a fake app. If something gets stuck, open an issue.
- **Agents no longer run the tests themselves** when the sandbox is on: if a test fails, Constellation sends them a fix to make.
- 148 medium or minor defects remain, to handle in the next versions.

## 0.3.25 (2026-11-05)

### Fix
- **Lighter missions**: to start from your current state, each mission task gets a copy of the files Git does not track. That copy also took the working copies of the same project kept inside it, such as those Claude Code keeps in `.claude/worktrees`, whole, builds included. It even took their `.git` file, which points to your real repository. On one project, each task weighed 2.6 GB. These copies of the project are now left out. Other untracked files, and another repository kept inside the project, are still copied.

### Good to know
- **Checked**: the test suite (796 tests, 14 skipped, no failures), including a trial with a real worktree of the same repository and another nested repository.
- **Not checked**: a real mission with this fix. If something gets stuck, open an issue.
- **Worktrees already created** do not change: "Clean up the worktrees", in a finished mission, removes them.

## 0.3.24 (2026-11-05)

### Fix
- **An update that seemed not to reopen the app**: before installing, the app copied its whole data folder, including the missions' working copies (worktrees), which can weigh gigabytes. The app stayed closed for long minutes without showing anything. The backup now leaves the worktrees in place, as the installation does not touch them, and clones the rest: it takes under a second and almost no disk space.
- **Update page**: the GitHub repository shows as plain text instead of a field you could type into.

### Good to know
- **The backup is made by the version already installed**: going from 0.3.23 to 0.3.24 may therefore still be slow, one last time. Wait for the app to come back. Later updates will be fast.
- **Checked**: the test suite (795 tests, 14 skipped, no failures). On a real 16 GB folder, the backup went from about 1 min 30 to 0.2 s, and from 16 GB to 10 MB.
- **Not checked**: the complete path from the app's button to the relaunch with the new backup. If something gets stuck, open an issue.
- **Old backups** (`~/Library/Application Support/Constellation-sauvegardes`) can weigh a lot: those of earlier versions hold a full copy of the worktrees. You can delete the oldest ones.

## 0.3.23 (2026-11-05)

### Important fixes
This version fixes 18 bugs reported by a second code analysis of Constellation. Several concern security: updating is recommended.

**Security**
- Cloning a repository: a pasted address starting with `-` is refused. It could run a command on your Mac.
- Checks run in the sandbox no longer read your shell profiles (`~/.zshrc` and the others), the `.env` files of other projects, or the Vercel, Stripe, Hugging Face and a few other accounts. Your `PATH` is read once outside the sandbox: `git`, `swift`, `node` or `python3` still work.
- The SSH agent set by a shell profile (1Password, Secretive) is now closed to checks.
- Double-clicking a file or a link that opens an app asks for confirmation.

**Missions**
- "Interrupt" no longer touches a task that is already finished.
- A task that reaches the spending cap really waits for your decision.
- "Relaunch" makes corrections possible again.
- When the agent says it has not finished, a favourable review no longer validates the task.
- A task out of attempts becomes "Failed".
- Cleaning a worktree keeps the files ignored by Git that nobody declared.

**The rest**
- A resumed draft can no longer overwrite a file changed in the meantime.
- Loops count their pauses, no longer lose a run and show their real duration.
- Dictation no longer loses a sentence.
- Git panel: double-clicking Commit no longer shows a false failure, and a failed fetch is no longer recorded as done.
- A repository like `me.github.io` keeps its name when cloned.

### Good to know
- **Checked**: the test suite (794 tests, 14 skipped, no failures); 15 of the 18 bugs were first reproduced by a failing test. A real mission ended "Successful and verified" with its checks in the new sandbox. The sandbox rules were tried on real paths.
- **Not seen on screen**: dictation, the confirmation when opening a card, and drafts. If something gets stuck, open an issue.
- **Known and not fixed**: the sandbox refuses a list of sensitive files, it does not allow a closed list; an ordinary file from another project stays readable. A check that uses a profile function (`nvm use`, `conda activate`) no longer finds it. A kept worktree has no "Delete anyway" button.

## 0.3.22 (2026-11-05)

### Important fixes
This version fixes the 15 bugs reported by a code analysis of Constellation. Several concern security: updating is recommended.

**Security**
- Checks run in the sandbox can no longer touch the files of an update being prepared: those files moved to another folder.
- They can no longer reach the SSH agent macOS provides or the one the app knows.
- They can no longer read Codex and Gemini accounts, or the app's data. The project folder stays readable.
- A `CLAUDE.md`, `AGENTS.md` or `GEMINI.md` written by an agent goes through your approval before entering the project. With the web or a connector, the agent cannot change them with its editing tools.

**Missions**
- Tasks that exceed their time limit together each keep their 3 attempts, instead of 3, 2 and 1.
- A task key containing `/` no longer blocks the integration.
- A relaunch or an acceptance during the final check is no longer lost.

**Git panel**
- A refused commit keeps your message and selection.
- A file gone from the list no longer fails the commit.
- "Discard changes" also keeps the staged version.

**The rest**
- Reply drafts stay attached to their task.
- A failed export says so.
- A waiting plan is no longer cleared with finished orders.
- An ambiguous `skills:` field is no longer rewritten.

### Good to know
- **Checked**: the test suite (759 tests, 14 skipped, no failures). This version's code also downloaded the real 0.3.21 from GitHub, verified its signature in the new folder, then installed it in a trial folder with a backup, and the work folder was emptied. The sandbox's refused accesses were tried on real paths.
- **Not checked**: this path started from the app's button, with the certificate check and the relaunch; an actual script swap during an installation (only the write was proven, then refused); per-task drafts and the Git panel selection on screen. Four of the 15 bugs were confirmed by reading the code only, without reproducing them. If something gets stuck, open an issue.
- **Known and not fixed**: an SSH agent set by a shell profile (1Password, Secretive) stays reachable from the sandbox. Five leads set aside by the analysis remain to check: they are in the roadmap.

## 0.3.21 (2026-11-05)

### What's new
- **Faster coordinator plan**: it finds the project's structure and reads only the files that matter for splitting the work, instead of doing the agents' analysis for them. On one project, the plan went from 4 min 51 and $1.02 to 33 s and $0.11, with one measure each.
- **Sonnet proposed by default for the coordinator**: if you never changed this setting, new missions use it. If you chose a model, your choice stays. You can change it in **New mission › Advanced** and in Settings.

### Fix
- **Installation**: two installations started at once could leave an empty app in Applications. Only one can run at a time now, and each has its own temporary folder.

### Good to know
- **Review and synthesis**: they move to Sonnet too, as they follow the coordinator unless you choose another model for the review. It costs less, but a lighter review may let more errors through.
- **Checked**: the test suite (733 tests, 14 skipped); a single timing test failed, by very little (0.62 s against 0.6 s), while the Mac was under load, and it passed 3 times out of 3 run alone. The plan with both settings was measured on a real project. The double installation was tested with the script, not from the app.
- **Not checked**: a Sonnet plan carried through a large mission, and the complete path from the board's "Update" button to the relaunch. If something gets stuck, open an issue.
- **Known and not fixed**: a code analysis reported 15 possible bugs, in missions, the sandbox and the Git panel. None has been reproduced or fixed yet.

## 0.3.20 (2026-11-04)

### What's new
- **Automatic update checks**: at launch, then every 6 hours, and when you come back to the app if that time has passed. You can turn this off in Settings › About. Installing stays your choice, as it closes the app.
- **Red dot on Settings**: it shows that an update is waiting, on the home screen and on the board. A click opens Settings on "About".

### Fix
- **The board's "Update" button**: it showed "Constellation will close and reopen" and never installed anything. The app now closes its window before quitting. If you refuse to quit, for example because of a live console, the installation is cancelled and a message tells you.
- A check can no longer start during an installation.

### Good to know
- **From a version older than 0.3.20**: install from **Settings › About**. The board's "Update" button in those versions stays stuck.
- **Checked**: an old-version app found the real latest version on GitHub and showed the dot on the board; closing, cancelling and "Quit" were tried on a copy of the app.
- **Not checked**: the dot on the home screen, opening on "About", the 6-hour check in real conditions, and the complete path from the board's button to the relaunch. If something gets stuck, open an issue.

## 0.3.19 (2026-11-04)

### Important fixes
This version fixes about forty bugs, several of which could lose work. Updating is recommended.

**Missions that ended "not verified"**
- In delegated mode, with no web or connector and the sandbox on, the approval box for checks is now ticked by default. You can untick it.
- Plain reads of the folder (`test`, `grep`, `wc`…) run alone in the sandbox, even with the web.
- If a task needs the web and the mission does not have it, the plan says so and the app tells you that relaunching will change nothing.

**Lost work**
- Code studio: `⌘Z` after switching files no longer touches the other file, and drafts go to the right file.
- Markdown studio: closing right after typing no longer loses text, and saving no longer overwrites a file changed by an agent.
- Git panel: "Discard" no longer loses work with names containing a quote or a `*`.
- "Close space" asks for confirmation, and a closed space can be restored. A removed project gets its board and history back when you reopen its folder.
- A file that is unreadable or written by a newer version is no longer overwritten.
- Skill and sub-agent editors: "Cancel" keeps your changes, and saving no longer removes settings.
- Saving follows symbolic links, and keeps mixed line endings and the BOM.
- `⌘Z` restores groups and loops, and asks before stopping a live console.

**What did not work**
- A console idle for 60 s is no longer marked "needs you".
- An accented file name no longer fails the commit. The first commit of a repository, a project in a subfolder of a repository and already staged deletions work.
- "Stop" really stops a console.
- A loop no longer stops if the agent answers in under 2 minutes.
- A handoff stays in its project and no longer answers a trust question for you.
- The Usage page no longer counts about three times too many output tokens. Your totals will therefore drop.
- Pasting a console into another project no longer keeps the old folder or the no-permissions mode.
- The fish and tcsh shells no longer break the app's commands.
- The microphone no longer stays on after dictation, and closing a studio during a generation no longer loses the result.

### Good to know
- **Security decision**: with the box ticked by default, the code of a project you cloned can run alone in the sandbox, with the network open. Your usual secrets stay unreadable. Untick the box if you do not trust the project.
- **Checked in real conditions**: a mission with the web and the box off, ended "Successful and verified"; the keyboard and clicks inside cards, on a copy of the app. The plain-read filter went through 111 trap commands in zsh, bash and sh, but no full attack test.
- **Not seen on screen**: the new confirmation dialogs, the "Restore a closed space…" menu, the "Relink to a folder…" button and the Git panel with the mouse. Their logic is tested. The new "needs you" setting has not run in a real console, nor fish with the real shell. If something gets stuck, open an issue.
- **Known and not fixed**: after "Relink to a folder…", a finished mission keeps its old path. A folder made elsewhere can still arrive in the project with its own `.git`.

## 0.3.18 (2026-11-04)

### What's new
- **Review model**: in **New mission › Advanced** and in Settings, you can choose the model of the independent review: "Same as the coordinator" (default), Sonnet, Haiku or Opus. A lighter model costs less but may let more errors through. If you change nothing, nothing changes.

### Good to know
- If you untick the independent review, the reviews that still run, such as the end-of-mission one, use the coordinator's model.
- Tried with the tests' fake CLI, not yet in a real mission. If something gets stuck, open an issue.

## 0.3.17 (2026-11-04)

### Important fixes
- **Ticket and event editor with the keyboard**: Return opened it, but the keyboard stayed on the board. Nothing could be typed in it and Escape did not close it. The keyboard now enters it, what you type is added at the end of the title, Escape closes it and the keyboard returns to the ticket or day.
- **Calendar**: Return again on a day opens the next event. Deleting an event closes its editor.

### Security
- **Protected subfolders**: during a check, a subfolder holding a `.git`, a `.claude` or a `CLAUDE.md` can no longer be moved or removed, so it can no longer leave the project and come back changed. What is inside it stays editable as usual.
- **Process in its own session**: in a task's worktree, what a check or an agent session started with `setsid` is stopped when it ends, and when the app closes.
- **Shell profile secrets under fish**: variables are removed one at a time, a safer form across fish versions.

### Other fixes
- A mission note followed by another stays translated in the English app.

### Good to know
- **Subfolder limits**: a folder made elsewhere can still arrive in the project with its own `.git`. Folders that tools rebuild (`node_modules`, `.venv`, `venv`, `.build`…) are not pinned. Past a very large number of protected subfolders, some are not either, and the check says so.
- **Processes deliberately not stopped**: in a folder with no worktree, a process in its own session may belong to another check or agent. A daemon that changes directory or forks again also escapes.
- **Keyboard**: tested with real keys and real clicks sent by macOS, not with VoiceOver.
- **Update**: tried for real from 0.3.15 to 0.3.17 from the app.
- **Not tried**: the fish form has not run in real fish. If something gets stuck, open an issue.

## 0.3.16 (2026-11-04)

### Important fixes
These defects were in 0.3.15. Updating is recommended.
- **Lost deliverable**: a task whose only result was a file ignored by Git, inside a folder, counted as successful and the file never reached the project. This case is now reported, and the worktree holding the file is kept.
- **Acceptance that stayed**: after a manual acceptance and then a conflict, a new attempt could pass as accepted without a check.
- **Write error during integration**: the message pushed you to accept without proof. It now offers "Retry the integration".
- **Caches**: a mere `__pycache__` or `node_modules` no longer prevents removing a worktree.
- **Final check**: a task with no check no longer cancels the final review when the plan repeats a check.

### What's new
- **Keyboard inside cards**: in a kanban, ↑ enters the tickets, the arrows walk them, Return edits one and ⌥ ← → changes its column. In a calendar, the arrows walk the days, Return opens the day's first event and ⇧ Return adds one. An outline shows where you are.
- **Readability**: state and group colours reach a 4.5:1 contrast in light and dark. The smallest text goes up to 11 pt. On the Usage page, "Cache written" turns violet to stand apart from "Cache read".
- **Reduce animations** now also covers the card border. Some English translations were missing from the board menus.

### Security
- **Nothing left after a check**: what a check leaves running in the background, for example with `(cmd &)`, is stopped when it ends.
- **Shell profile secrets**: variables recognised as keys or passwords, exported by your profile, are removed from sandboxed checks. If the profile cannot be read, the check says so in its note.

### Fewer wasted turns
- Agents now know which Bash commands they may run. Across 6 real missions, all successful, no Bash command was refused, against 2 or 3 per mission before.

### Good to know
- **Not tried in real conditions**: the real keyboard (tested with simulated keys), VoiceOver, and Escape to close a ticket or event editor, which did not respond to simulated keys. If something gets stuck, open an issue.
- **Known and not fixed**: a process started with `setsid` still survives its check. The secrets filter relies on variable names and values: it can miss some, and it has not been tried with the fish shell.
- **Cautious choice**: a `dist`, `build` or `target` folder ignored by Git, inside a task's scope, keeps its worktree so as not to lose a deliverable. You may sometimes have to clean it by hand.

## 0.3.15 (2026-11-04)

### What's new
- **Mission history**: the **Missions** button on the home screen finds every mission, with a search. You can reopen one, run it again, copy its result or save it, with keys masked.
- **Change the request**: after a refused plan, you pick up your request without rewriting it.
- **Keyboard and VoiceOver**: Tab, ⇧Tab and ⌥ Arrows move from card to card, Return opens it. Each card announces itself to VoiceOver. A file that is not a document asks before opening.

### Security
- **Checks in a sandbox**: checks can no longer change Git data or Claude's configuration, at any depth of the folder, launch apps, change preferences or read the clipboard.

### Reliability
- **Hard stop during integration**: on return, the mission reports the doubt instead of applying the patch again. You choose between "Already in my files" and "Apply".
- **Project in a subfolder of a repository**: worktrees and integration take it into account.
- **One instance of the app at a time**: two instances can no longer overwrite each other's data.
- **Safer deletions**: deleting a mission keeps the worktrees that still hold work, and names them.
- **Agent instructions**: a check the agent could not run no longer makes its work count as partial, which sometimes blocked a mission.
- **Usage limits**: they are recognised better, and so is their end time.

### Fewer tokens, more speed
- The diff sent for review is capped. Calls outside missions go through Sonnet, without connectors or skills.
- Saving leaves the main thread, and the Usage page reopens much faster.

### Good to know
- **Sandbox**: it is one more barrier, not a guarantee. What a check writes in the folder or a cache can run later. In a folder with no worktree, `git add` and `git commit` fail during a check.
- **Not tried in real conditions**: the real keyboard and VoiceOver, the "Already in my files" and "Apply" buttons, a forced stop during integration, the second-instance alert. These are only covered by automated tests. If something gets stuck, open an issue.
- **Known and not fixed**: a process started in the background with `(cmd &)` survives closing the app.

## 0.3.14 (2026-11-03)

### Fixes
- **Files not in UTF-8**: a task isolated in a worktree could corrupt them when integrated. The patch now keeps the exact bytes.
- **Generated documents**: the end of the text could be lost. They are read to the end, without cutting accented letters.
- **Safer storage**: one unreadable mission no longer takes the others, and the file is set aside, with a message. A failed write is tried again. Small unreadable files (profiles, memory, presets) are set aside instead of overwritten.
- **Less risky deletions**: nothing is deleted if the archive fails. Cards holding work and documents ask for confirmation. A dropped file no longer overwrites another.
- **Notes and code**: an unreadable note is no longer opened as an empty one. A failed write is reported and the text stays on screen. A Latin-1 file stays Latin-1.
- **Updates**: if the installation fails, the old app is put back.
- **Maximum spending held better**: each session gets its share and stops at it, keeping its conversation. Unticking "Suspend" at the limit grants half as much again, not an open account. A mission stopped by spending tells you.
- **Model**: a task with no planned model runs on Sonnet, no longer on the account's default.
- **Usage limit**: the plan and reviews also wait for the limit to end. An account error is no longer retried in a loop.
- **Without Claude Code or an account**: the mission window says so and starts nothing.
- **Secrets**: the most common tokens are masked in the log and the diagnostic.

### Good to know
- **Maximum spending**: it can still be exceeded. The plan, reviews and summary have no reserved share, and a session can go slightly over within a turn. Stopping at the limit has not yet been seen in a real mission.
- **Checks**: they still run without a sandbox, with your rights. The script protection is partial.
- **Not checked on screen**: several of these fixes are covered by tests without having been tried in the interface. If something gets stuck, open an issue.

## 0.3.13 (2026-11-03)

### What's new
- **Missions use less**: the model chosen by the plan now really applies to each task, Sonnet by default. Before, an old setting could run everything on the CLI's default model, even when the plan chose otherwise. **Your task model setting goes back once to "Depending on the task"**: set it again if you chose it on purpose. Agent sessions also load fewer tools and read more selectively.
- **The usage limit no longer fails agent tasks**: they wait for the announced time, then resume the same conversation, without pointless attempts.
- **Maximum spending** per mission, in the advanced settings. It is optional and can be exceeded, since running sessions finish.
- **More text in English**: the engine's messages with values now follow the interface language.

### Fixes
- **The cost shown was too high**: relaunches of one conversation were added up. Older missions show the right amount too.
- **Fewer false successes**: an agent reporting a failure or partial work goes to "to check", even if its checks pass. A mission with no required task is never "verified", and a deliverable ignored by Git blocks success.
- **Less risk of loss**: an unreadable missions file is no longer taken for an empty history. "Discard changes" removes nothing without a safety copy. A console whose folder disappeared no longer starts in your home folder.
- **Security**: agents only get exact read commands. With the web or a connector, only Constellation runs the checks, and an approved command waits for your agreement if an agent changed `package.json`, a `Makefile` or a script.
- **Accessibility**: the main clickable areas are visible to VoiceOver.

### Good to know
- The script protection is partial: the list of watched files is not complete, and the box that authorizes all commands overrides it.
- A mission that used to finish alone can now stop to ask you to judge a task.
- The usage limit pause and VoiceOver were not tried in real conditions. If something gets stuck, open an issue.

## 0.3.12 (2026-11-03)

### What's new
- **Connectors in missions**: Notion, Gmail, Vercel… You tick, mission by mission, the ones agents may use. Nothing is ticked by default and only ticked connectors are loaded. The coordinator and the reviewer have no access to them.
- **The interface is now available in English almost everywhere**: tutorial, Settings, skill library, missions, mission map, tool windows and messages.

### Good to know
- **A connector can act outside your Mac.** Constellation can't tell which tools write, and agents don't ask you to confirm each action. Web + connector and delegated mode + connector therefore require a consent box for the mission.
- **External actions are not verified.** Constellation can't see the real state of the service: each call appears in the activity, with the "Unverified external actions" mention.
- **A relaunch or a fix can repeat an action.** The agent is told about earlier calls, but nothing guarantees it: check the result in the service itself.
- Connectors are installed and signed in through Claude Code, not the app. Each agent session uses a bit more when a connector is ticked.
- Still in French: the instructions sent to agents, the content of skill templates, the words recognised by voice commands and the command bar, and a few technical messages from the engine.

## 0.3.11 (2026-11-02)

### Nouveautés
- **Se déplacer et zoomer devient simple** : deux doigts ou la molette déplacent le tableau partout, même au-dessus d'une carte. Le pincement et ⌘ + molette zooment autour du pointeur. Tu peux dépasser les bords pour sortir une carte de sous les barres d'outils. À la souris, maintiens le clic droit et glisse pour te déplacer ; un simple clic droit ouvre toujours le menu. Les boutons + et − avancent par paliers réguliers.
- **Un fond vivant** : un réseau de points lumineux à l'accueil, et une version plus discrète derrière les cartes du tableau. Il s'anime quand un agent travaille. Il suit ta couleur d'accent.
- **Des missions plus lisibles** : la carte du coordinateur montre l'avancement, la durée, le coût (« au moins X $ »), le plafond d'appels et les dernières actions. Les tâches ont une pastille d'état et un badge de modèle.
- **Des animations** : halo sur les tâches en cours et signaux sur les liens actifs. « Réduire les animations » coupe tout mouvement.

### Ce qui change à l'usage
Une console ou une page web ne défile que si tu as **cliqué dedans**. Clique sur le tableau vide pour lui rendre le défilement.

### Corrections
- **Moins de consommation au repos** : la pastille d'une console inactive pulsait 30 fois par seconde, même fenêtre cachée. Sur une version de test, la consommation au repos passe d'environ 22 % à 3 % de processeur.
- Une carte ne peut plus rester coincée sous la barre d'outils.

### À savoir
Pendant qu'une mission travaille, le fond et les animations consomment davantage de processeur : environ 30 % sur une version de test. Si l'app te semble lourde, active « Réduire les animations ». Les gestes réels au trackpad et à la souris, ainsi que le clic droit sur une page web, n'ont pas été couverts par les tests automatiques : si quelque chose ne va pas, ouvre une issue.

## 0.3.10 (2026-11-02)

### Nouveautés
- **Des missions sur tous les sujets** : recherche, rédaction, analyse, organisation ou code. Depuis l'accueil, **Nouvelle mission** crée toute seule un dossier de travail dans `~/Documents/Constellation`. Git reste discret quand il n'y a pas de dépôt.
- **Une relecture indépendante, activée par défaut** : une session séparée juge chaque tâche selon ses critères et peut demander une correction. L'app dit toujours ce qui a été fait : « Vérifiée par commandes », « Vérifiée par commandes et relue » ou « Validée par relecture ». Une relecture réduit les erreurs, sans rien garantir.
- **Des sous-agents visibles sur plusieurs niveaux** : un agent peut créer un sous-agent, qui peut en créer un autre (4 niveaux par défaut, jusqu'à 6). Chacun apparaît sur le tableau.
- **Un modèle selon la tâche** : Haiku, Sonnet ou Opus sont choisis tâche par tâche. Tu peux aussi imposer un modèle à toute la mission.
- **Fable au choix** : si tu le sélectionnes, Constellation vérifie ton accès. Sans accès ni crédits, la tâche passe sur Opus et l'app te le signale.
- **La recherche sur le web** : activée par défaut dans un nouveau dossier, désactivée par défaut dans un projet existant.
- **Les livrables** : les fichiers produits s'ouvrent d'un clic. Les fichiers exécutables s'affichent seulement dans le Finder.
- **Moins d'interruptions en mode assisté** : tu valides le plan, puis les sous-agents et les corrections avancent seuls. Les commandes inconnues, les questions et les conflits t'attendent toujours.

### Consommation
La relecture par défaut consomme nettement plus de quota : lors d'un essai, une recherche sur le web en deux tâches a coûté environ 2,50 $ selon la CLI, sans aller jusqu'au bout. Tu peux la décocher pour une petite mission de code bien testée. Une mission se suspend au bout de 80 appels à Claude, et tu peux lui en accorder 40 de plus. Le coût s'affiche sous la forme « au moins X $ ».

### Sécurité
- Avec le web activé, seules les commandes de ton plan s'exécutent sans te demander. Les commandes des sous-agents attendent ton accord.
- **Une limite demeure** : une page web piégée pourrait tromper un agent. Il pourrait alors modifier des fichiers, envoyer leur contenu vers un site, ou glisser du code dans une commande que tu as approuvée, qui tournerait avec tes droits. Laisse le web désactivé sur les projets sensibles.

### Corrections
- Une mission ne reste plus bloquée quand deux agents créent des sous-agents sur les mêmes fichiers, ni quand l'app est fermée pendant la rédaction d'une correction.
- Une correction en attente reprend après une fermeture de l'app.

### À savoir
Le parcours complet dans l'interface n'a pas encore été essayé en conditions réelles : les essais réels ont été faits sur la CLI. Si quelque chose ne va pas, ouvre une issue.

## 0.3.9 (2026-11-01)

### Nouveautés
- **Nouvelle icône** : une constellation en forme de C, avec une étoile corail qui brille sur un ciel de nuit. Elle reste reconnaissable dans le Dock comme dans les listes du Finder.

Le Dock peut garder l'ancienne icône un moment après la mise à jour : elle se met à jour au prochain redémarrage du Dock ou du Mac.

## 0.3.8 (2026-11-01)

### Corrections
- **Tes projets ne peuvent plus disparaître** : si la liste des projets est abîmée, Constellation la reconstruit à partir de ses fichiers et garde une copie de l'ancienne. Un projet illisible reste dans la liste au lieu d'être oublié, et un bandeau te prévient.
- **Enregistrement surveillé** : si le disque refuse un enregistrement (disque plein, droits), un bandeau le dit et Constellation réessaie toutes les 10 secondes, au lieu de faire comme si tout était enregistré.
- **Plus d'appels bloqués** : les boucles d'automatisation et le planificateur d'ordres ne peuvent plus rester figés sur un appel à Claude Code. Le délai s'applique toujours et arrête aussi les programmes lancés par l'appel.
- **Missions plus fiables** : la dernière ligne d'une session est toujours lue avant sa fin, ce qui évitait parfois une relance inutile.
- **Messages aux consoles** : deux messages envoyés coup sur coup à la même console ne se mélangent plus.
- **Mises à jour** : les fichiers temporaires sont supprimés après chaque essai.

### Sécurité
- **Contrôles automatiques plus stricts** : une commande de contrôle n'est lancée sans ton accord que si elle ne contient que des options sûres. Les options qui lancent un autre programme (`go test -exec`, `pytest -p`, `make -f`…) demandent ta validation.
- **État des consoles protégé** : chaque console a ses propres hooks, signés par un jeton secret. Un programme lancé dans la console ne peut plus faire croire que l'agent attend ou a fini.
- **Mises à jour liées à ton certificat** : une mise à jour n'est acceptée que si elle est signée avec le même certificat que l'app installée.

### Confort
- **Tableau plus fluide** avec plusieurs missions et consoles actives : seules les zones qui changent sont redessinées, et l'animation s'arrête quand la fenêtre est cachée.
- **Moins d'énergie au repos** : l'état des consoles n'est relu que lorsqu'il change, et moins souvent quand l'app est en arrière-plan.

### Accessibilité
- **VoiceOver lit le tableau** : tâches de mission, sous-agents et groupes sont annoncés en mots, et une tâche s'ouvre en l'activant.
- **Textes plus lisibles** : aucun texte de l'interface ne descend sous 11 points, et les barres d'outils ne coupent plus leurs libellés.
- **Boutons nommés** : les boutons faits d'une seule icône ont un nom pour VoiceOver et une bulle d'aide.
- **Interface anglaise complétée** : les derniers textes en français seulement sont traduits.

## 0.3.7 (2026-10-29)

### Nouveautés
- **Missions expliquées en clair** : chaque tâche a un encadré « En clair » qui dit ce qui s'est passé, pourquoi et quoi faire, avec le nom des boutons. Le détail technique reste disponible dessous. Les contrôles sont écrits en phrases (« le fichier rapport.md contient « Gravité » »), et la carte du coordinateur résume la mission en une phrase.
- **Essais automatiques** : un agent qui plante, renvoie une erreur ou dépasse son temps est relancé tout seul, deux fois, dans sa conversation. Pendant ce temps, les autres agents terminent leur travail.
- **Missions plus rapides** : une tâche terminée laisse la main tout de suite à la suivante (0,07 s au lieu d'environ 1 s entre deux tâches qui se suivent).

### Corrections
- **« Reprendre » relance vraiment les sous-agents** après une fermeture de Constellation en pleine mission. Ils repartent là où ils s'étaient arrêtés quand leur conversation est connue. Avant, le bouton rouvrait la mission sans rien relancer, puis disparaissait.
- **Tâches bloquées** : une tâche bloquée par une autre repart dès que celle-ci a réussi ou que tu l'as acceptée.
- **Un agent arrêté ne peut plus faire quitter Constellation**, ce qui arrêtait tous les autres agents.
- **Dossier partagé** : une tâche réussie ne finit plus « Non vérifiée » parce que d'autres agents écrivaient en même temps. Sa vérification attend qu'ils aient fini.

## 0.3.6 (2026-10-29)

### Nouveautés
- **Tâches de mission déplaçables** : sur le tableau, glisse les tâches d'une mission lancée, et donc leurs sous-agents, pour les ranger comme tu veux. Leurs liens suivent. Elles restent à leur place par rapport au coordinateur : si tu déplaces sa carte, toute la mission suit. Un clic ouvre toujours la tâche, et ⌘Z annule un déplacement.
- **Clic droit sur une tâche** : « Remettre à sa place » ou « Ranger la mission automatiquement ».

### Corrections
- **Contrôles de mission avec des accents** : un contrôle comme `grep -q 'Gravité' rapport.md` échouait toujours, même quand le fichier contenait le mot. macOS transmettait les accents sous une autre forme (« é » devenait « e » + accent). Les tâches échouaient alors après plusieurs tentatives, ou posaient des questions sans issue. Le texte arrive maintenant intact : contrôles et sessions des missions, automatisations, générateurs, commandes du panneau Git et messages de commit.

## 0.3.5 (2026-10-29)

### Nouveautés
- **Barres de progression** pour l'agent de chaque console Claude Code (sous son titre) et pour chacun de ses sous-agents (dans leur bulle). Quand l'agent tient une liste de tâches, la barre affiche les tâches faites et la tâche en cours. Sinon, elle avance avec ses étapes (chaque outil utilisé) et le temps passé. C'est alors une estimation, qui n'arrive au bout qu'une fois le travail fini.
- **Skill find-skills** dans la bibliothèque : les agents et sous-agents cherchent un skill utile, d'abord parmi ceux installés, puis sur skills.sh. Ils proposent ce qu'ils trouvent et n'installent rien sans ton accord.
- **Réglages › À propos** : liens vers la page GitHub de Constellation et vers la page pour signaler un problème.

### Corrections
- **Déconnexion** : la fenêtre Réglages se ferme et ne peut pas être rouverte tant que tu n'es pas reconnecté. Avant, elle restait ouverte et modifiable.

## 0.3.4 (2026-10-29)

### Nouveautés
- **Plein écran au lancement** : la fenêtre s'ouvre en plein écran, puis comme tu l'as laissée la dernière fois.

### Corrections
- **Accès aux Documents demandé à chaque lancement** : l'app est maintenant signée avec un certificat qui ne change pas d'une version à l'autre, et macOS se souvient de tes autorisations (Documents, micro). Il peut les redemander une dernière fois après cette mise à jour.
- **Déconnexion** : les fenêtres ouvertes (Réglages, À propos, Mises à jour…) se ferment et ne recouvrent plus la page de connexion.
- **Barres de défilement** : elles n'apparaissent plus que pendant le défilement et n'encadrent plus le tableau, même en plein écran.

## 0.3.3 (2026-10-29)

### Nouveautés
- **Quota de ton abonnement Claude dans la barre du haut** : la part utilisée de la session de 5 h et de la semaine, avec l'heure de réinitialisation. Au survol ou dans la page Consommation, tu vois aussi la part restante. Les chiffres viennent de Claude Code et s'actualisent quand une console Claude Code du tableau reçoit une réponse.
- **Bouton de compte** en haut à droite, à côté des réglages : il affiche le compte connecté et son offre, et permet de se déconnecter, ou de se connecter si tu utilises Constellation sans compte.

### Corrections
- **Claude Code introuvable** : si Claude Code était installé avec sa commande officielle, Constellation pouvait rester bloquée sur la page « Installer Claude Code ». Elle le trouve maintenant dans ses dossiers d'installation habituels. La même correction s'applique aux missions, aux automatisations et aux générateurs.

## 0.3.2 (2026-10-29)

### Nouveautés
- **Mac Intel pris en charge** : l'app est désormais universelle (Apple Silicon et Intel), toujours à partir de macOS 14.
- **Exporter un diagnostic** (menu Aide) : une archive à joindre à un signalement, avec la version, le système, les réglages de l'app sans clés ni jetons, et le journal de la session. Ton dossier personnel et ton nom d'utilisateur sont masqués, et rien n'est envoyé automatiquement.
- **VoiceOver** : les boutons qui n'affichent qu'une icône ont maintenant un nom.

### Corrections
- **Récupération des projets** : si le fichier d'un projet manque ou a été coupé (par exemple après un plantage pendant une sauvegarde), sa copie précédente est maintenant bien rechargée. Avant, le projet disparaissait du tableau.
- **Détection des CLI** : elle ne peut plus rester bloquée si ton fichier de démarrage du shell attend une saisie.

## 0.3.1 (2026-10-29)

### Nouveautés
- **Vérification du système au lancement** : Constellation s'assure d'abord qu'elle tourne sur macOS 14 ou plus récent. Sinon, elle explique pourquoi et se ferme, sans toucher à aucune donnée.
- **Nom unifié** : l'app, ses réglages et ses données s'appellent désormais tous Constellation. Les réglages et données des versions précédentes sont repris automatiquement au premier lancement.

## 0.3.0 (2026-10-29)

### Nouveautés
- **Compte Claude** : page de connexion au premier lancement (abonnement Claude ou compte Anthropic Console), état du compte dans Réglages, déconnexion depuis le menu.
- **Mises à jour** depuis ce dépôt, vérifiées par signature Ed25519.
