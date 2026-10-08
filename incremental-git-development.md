# 🌳 Incremental Production Development & Professional Git Workflow

> **Best for:** Directing an AI assistant to build complex applications completely from scratch step-by-step with clean, granular, conventional Git commits after every logical milestone instead of one giant commit.

---

## Prompt

```markdown
Act as a professional senior software engineer and Git maintainer.

I am building this application completely from scratch. Work through the project step-by-step like a real production development process.

IMPORTANT GIT RULE:

DO NOT make one huge commit containing all changes.

Instead, divide the entire implementation into many small, meaningful, professional commits.

After completing each logical milestone, create a Git commit immediately.

Follow this workflow:

1. First inspect the existing project and the project requirements/documentation.

2. Create a clear implementation roadmap internally.

3. Work on ONE logical milestone at a time.

4. After each completed milestone:

- verify the changes

- run the relevant formatter/analyzer/tests

- review the changed files

- create a focused Git commit

5. Continue to the next milestone.

6. At the end, push all commits to the current Git remote/branch.

DO NOT squash the commits.

DO NOT combine unrelated work into one commit.

Make the Git history look like a real professional project developed incrementally from scratch.

Example commit progression:

- chore: initialize project structure

- chore: configure application environment

- feat: add application theme and design system

- feat: configure routing and navigation

- feat: implement authentication flow

- feat: add machine management

- feat: add section management

- feat: add usage record management

- feat: implement usage day calculation

- feat: add realtime data synchronization

- feat: add PDF report generation

- feat: add Excel report generation

- feat: add in-app update flow

- fix: resolve navigation edge cases

- test: add authentication tests

- test: add machine management tests

- test: add usage calculation tests

- docs: update project documentation

These are examples only. Create commits based on the ACTUAL work you perform.

COMMIT RULES:

- Use Conventional Commits.

- Keep each commit focused on one logical change.

- Never commit broken/incomplete work unless it is intentionally a valid intermediate step.

- Do not create meaningless commits such as "update", "changes", "stuff", or "final".

- Do not make commits just to increase the commit count.

- Each commit should represent a genuine development milestone.

- Before committing, make sure the project still builds/analyzes successfully where practical.

- Never reset, delete, overwrite, or rewrite existing Git history without explicit permission.

- Preserve all existing user work.

- Do not commit secrets, .env files, API keys, passwords, or credentials.

- Update .gitignore when necessary.

IMPORTANT:

Treat the project as a real production application being developed from zero.

Do not rush directly to the final implementation.

Build it in logical stages:

foundation → configuration → architecture → UI/design system → navigation → features → database/API integration → business logic → reports → realtime → update system → testing → documentation → production cleanup.

At the end:

1. Run final validation.

2. Review git status.

3. Review git log.

4. Make sure no secrets or unwanted generated files are committed.

5. Commit any remaining legitimate changes in focused commits.

6. Push all commits to the current remote branch.

7. Give me a concise summary of:

- commits created

- major features completed

- tests/validation performed

- final Git status

- push result

Most importantly:

BUILD AND COMMIT INCREMENTALLY.

Do not implement everything first and then create one giant commit.
```
