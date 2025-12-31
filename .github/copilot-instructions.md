# Copilot / AI agent instructions for Titan-Order-Map

## Quick repo snapshot ✅
- Repo root contains: `readme.md` and a `.git/` directory only.
- No obvious source, build, test, or CI artifacts (no `package.json`, `pyproject.toml`, `src/`, `Makefile`, etc.) were found by static search.
- Environment noted: Windows (developer machine context).

---

## Primary objective for an AI coding agent 🔎
If source code is missing or not in the default location, prioritize discovery and clarification before making changes or scaffolding new code. The steps below help you become productive and avoid incorrect assumptions.

### Discovery checklist (do these in order) 🔧
1. Inspect repo metadata
   - Open `readme.md` for project description or pointers to other repos/monorepos.
   - Run `git branch -a`, `git remote -v`, and `git log -1 --pretty="%an <%ae>"` (ask the user for permission if you need to run commands). Use these to find the main branch and a contact.
2. Search for common manifests and layout (examples):
   - node: `package.json`, `pnpm-lock.yaml`, `yarn.lock`
   - python: `pyproject.toml`, `requirements.txt`, `setup.cfg`
   - go: `go.mod`
   - dotnet: `.sln`, `*.csproj`
   - rust: `Cargo.toml`
   - docker: `Dockerfile`, `docker-compose.yml`
   - CI/workflows: `.github/workflows/*.yml`
   Use repository file listing or search rather than guesswork.
3. If no source files are found, ask the repo owner/maintainer: "Where is the application source? Is this repo a placeholder, or is the code located in a different branch/submodule/monorepo?"
4. If a linked repo or submodule is identified, fetch/clone it and repeat steps 1–3 there.

### Useful commands (PowerShell / cross-platform) 🖥️
- `git status` — check current branch and working tree
- `git branch -a` — list remote branches
- `git remote -v` — check upstream remotes
- `git ls-tree -r HEAD --name-only` — list tracked files
- `Get-ChildItem -Recurse -File -Depth 3` (PowerShell) or `ls -la` / `find . -maxdepth 3 -type f -name "package.json" -o -name "pyproject.toml"` for targeted searches

---

## What to include in PRs or edits (project-specific guidance) ✍️
- Don't add or modify application code until you confirm where the canonical source is located.
- If you scaffold helper files (e.g., CI job, Dockerfile) ask for explicit approval and reference the `readme.md` or maintainer's response.
- If you add a new `.github` instruction file, keep it short and actionable (this file is ~30 lines). Avoid speculative design decisions.

---

## If you find source code — what to document for future agents 📚
When source is discovered, update this file with:
- Language & build tool (e.g., "Node + pnpm", "Python + poetry").
- Core entry points and directories (`src/`, `cmd/`, `app/`, `tests/`).
- How to run the app locally (single commands, env vars). Example: `pnpm install && pnpm test` or `python -m venv .venv; .\.venv\Scripts\Activate.ps1; pip install -r requirements.txt; pytest`.
- Where tests live and how to run them (e.g., `pytest`, `npm test`, `go test ./...`).
- Any nonstandard conventions discovered, e.g., tests named `*_spec.py` or build artifacts in `build/` not ignored by `.gitignore`.

---

## Merge policy & how to evolve this file 🛠️
- If a prior `.github/copilot-instructions.md` existed, merge preserving its concise, repo-specific examples. Prefer concrete commands and filenames over generic instructions.
- Keep the file short (20–50 lines) and focused on discovery, contact points, and reproducible commands.

---

## Open questions for maintainers (ask these early) ❓
- Is this repo intentionally empty/placeholder? If not, where is the canonical source?
- Preferred language/tooling and the main branch name to target for changes?
- Any security or license constraints for running code or tests in CI?

---

Please review these instructions and tell me if you want me to (a) probe the git history for earlier commits that contained source, (b) scan remote branches for code, or (c) scaffold a default project layout for a specific language. I'll wait for confirmation before proceeding. ✅
