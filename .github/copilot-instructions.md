<!--
Guidance for AI coding agents working on this repository.
This file is intentionally short and pragmatic: it documents what is
actually discoverable in the workspace and a safe checklist for next steps.
-->

# Copilot instructions — Assignment1_oop1

Repository snapshot (discoverable):
- `README.md` — "Online Library management system"
- `.git/` and git metadata

Quick intent for an AI agent:
- The repo currently has no source code or build files. Your job is to (1) inspect the workspace to confirm language/build, (2) surface missing pieces to the human, and (3) offer minimal, concrete scaffolding only if the user asks you to create it.

Immediate actions (run in PowerShell) — detect what exists:
```powershell
git status --porcelain; # quick repo status
Get-ChildItem -Recurse -File | Select-Object -First 200; # list files
Get-ChildItem -Recurse -Include package.json,pom.xml,build.gradle,pyproject.toml,requirements.txt,setup.py,*.csproj -File
```

How to behave when code is missing
- Do not assume a language or test framework. Report that only `README.md` exists and ask these clarifying questions:
  1. Which programming language should be used (Java/C#/Python/JS)?
 2. Are there starter requirements or a grading rubric (console app vs web vs library)?
 3. Do you want scaffolding (project layout, example classes, tests)?

When code exists — concise discovery checklist
- Locate these common roots: `src/`, `app/`, `lib/`, `tests/`, `examples/`.
- Identify build files: `pom.xml` (Maven), `build.gradle` (Gradle), `package.json` (npm), `pyproject.toml`/`requirements.txt` (Python), `*.csproj` (dotnet).
- Map domain objects by name: search for `Book`, `Library`, `User`, `Loan` — these are common for an "Online Library" and are useful anchors for API/CLI behavior.

Concrete examples you should return in analysis (if present):
- File that owns the entry point (e.g., `Main.java`, `Program.cs`, `app.py`, `index.js`).
- Where tests live (e.g., `tests/` or `src/test/`) and exact command to run them (for example `mvn test` or `python -m pytest`).
- Any external integrations (DB connection strings, external APIs) exposed as config files — return their paths.

Editing and suggestions policy
- Keep edits minimal and localized. If asked to generate starter code, create a small, runnable scaffold and include a short "how to run" in the PR description.
- Do not change formatting or project-wide settings unless the user requests it.

If you make an automated change (scaffold or fix):
- Add a concise README section describing how to build/run and one example of expected input/output.

If you are unsure, ask the three clarifying questions above before making non-trivial code changes.

---
References discovered in this checkout:
- `README.md` (project description only)

Next step for humans: tell the agent the preferred language and whether to scaffold a starter implementation (domain classes, simple CLI, and tests).
