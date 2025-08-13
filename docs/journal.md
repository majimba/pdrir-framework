# Project Journal

This journal captures notable actions, decisions, and changes performed on the PDRIR Framework docs and repository.

## 2025-08-13

- Repository hygiene
  - Backed up accidental Git repository at `/Users/mac` by moving `.git` to a timestamped backup.
  - Initialized a proper Git repository in `PDRIR_Framework`, committed all files, and pushed to `origin/main` (`git@github.com:majimba/pdrir-framework.git`).

- Docs structure and configuration
  - Quoted nav labels containing colons in `mkdocs.yml` to satisfy YAML parsing.
  - Switched to `docs/` as the MkDocs `docs_dir`; moved documentation content under `docs/`.
  - Updated `edit_uri` to `edit/main/docs/`.
  - Fixed MkDocs reserved folder name by renaming `docs/templates` to `docs/doc-templates` and updated nav paths.

- CI/CD and deployment
  - Consolidated GitHub Pages workflow (kept a single deploy workflow) and pushed changes.
  - Verified local build with `mkdocs build --strict` and started local preview with `mkdocs serve -a localhost:8000`.
  - Guidance provided to enable GitHub Pages using “GitHub Actions” as the source in repo Settings → Pages.

- Next steps
  - Ensure Pages is set to “GitHub Actions” in Settings → Pages and re-run the deploy workflow.
  - Continue app updates; entries here will be appended as we progress.


