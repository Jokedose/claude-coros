# CLAUDE.md

This file provides context and working conventions for AI assistants (primarily Claude Code)
operating in this repository.

---

## Project Overview

**Repository:** Jokedose/claude-coros
**Owner:** JokeTrirong (GitHub: Jokedose)
**Status:** Early / bootstrapping stage — no source code yet.

This project is currently empty. CLAUDE.md exists to establish conventions before code is
written, so that all future AI-assisted sessions are consistent from the start.

When the project's purpose is defined, update this section with: what the project does,
its primary language/runtime, and any key third-party dependencies.

---

## Repository Structure

```
claude-coros/
├── README.md       # Project description (currently a stub)
└── CLAUDE.md       # This file
```

As source code is added, update this tree. Suggested sections to document when ready:
source directories, test directories, configuration files, and build output locations.

---

## Git Workflow

### Primary Branch
`main` is the integration branch. It should always be in a working state.
Direct commits to `main` are discouraged; use feature branches and pull requests.

### Branch Naming Convention
```
claude/<action>-<description>-<id>
```

Examples:
- `claude/add-claude-documentation-MgtES`

Rules:
- Prefix AI-initiated branches with `claude/`.
- Use kebab-case for the description.
- Append a short random ID suffix (5–8 alphanumeric characters) to avoid collisions.
- Keep descriptions concise but meaningful (verb-noun form: `add-X`, `fix-X`, `update-X`).

Human-initiated branches may follow a different convention; document it here when established.

### Commit Messages
- Write in the imperative mood: "Add feature" not "Added feature".
- First line: 50 characters or fewer, no trailing period.
- If more context is needed, add a blank line then a body paragraph.
- Reference issue/PR numbers when applicable.

Example:
```
Add CLAUDE.md with project conventions

Establishes git workflow, branch naming, and AI assistant guidance
before any source code is written.
```

### Pull Requests
- Open a PR from a feature branch into `main`.
- Give the PR a title that mirrors the commit message style (imperative, concise).
- Include a short summary of what changed and why.

---

## Development Setup

_No build system, package manager, or runtime has been chosen yet._

Once a language and toolchain are selected, document here:
- How to install dependencies (e.g., `npm install`, `pip install -r requirements.txt`)
- How to run the project locally (e.g., `npm start`, `python main.py`)
- Required environment variables and where to put them (`.env`, etc.)
- Any required external services or accounts

---

## Testing

_No test framework has been chosen yet._

Once tests exist, document here:
- The command to run the full test suite
- How to run a single test file
- Where test files live relative to source files
- Coverage requirements or thresholds, if any

---

## Code Conventions

_No primary language has been chosen yet._

Once a language is established, document here:
- Formatter and linter (e.g., Prettier, ESLint, Black, Ruff)
- The command to format/lint the codebase
- Naming conventions (files, functions, variables, types)
- Import/module organization rules

---

## AI Assistant Instructions

### Scope of Work
- Read this file at the start of every session.
- Do not speculate about project purpose; work with what is documented here.
- When you learn something new and stable about the project (new toolchain, new convention),
  propose an update to CLAUDE.md as part of that session.

### File Operations
- Prefer targeted edits over wholesale file rewrites.
- Do not create files speculatively. Create files when there is a concrete reason.
- Do not create temporary scratch files in the repository.

### Git Operations
- Always work on a branch, never commit directly to `main`.
- Follow the branch naming convention above: `claude/<action>-<description>-<id>`.
- Stage specific files by name (`git add path/to/file`) rather than `git add .` or `git add -A`
  to avoid accidentally committing secrets or generated files.
- Do not use `--no-verify` to skip hooks.
- Do not amend existing commits. If a commit is wrong, create a new one to fix it.
- Do not force-push to `main` under any circumstances.
- Push the current branch with: `git push -u origin <branch-name>`
- Retry pushes on network failure up to 4 times with exponential backoff (2s, 4s, 8s, 16s).

### Pull Requests
- Use `gh pr create` (or GitHub MCP tools) to open pull requests.
- Set the base branch to `main`.
- Write a short summary body; do not leave the body blank.
- Do not merge your own PR without explicit human approval.

### What NOT to Do
- Do not install packages globally on the host system.
- Do not run destructive git commands (`reset --hard`, `checkout .`, `clean -f`) without
  explicit human instruction.
- Do not commit `.env` files or any file containing secrets or credentials.
- Do not push to the remote without explicit instruction from the human operator.

---

## Remote

The origin remote points to the GitHub repository through a local proxy:

```
http://local_proxy@127.0.0.1:42057/git/Jokedose/claude-coros
```

GitHub repository: https://github.com/Jokedose/claude-coros
