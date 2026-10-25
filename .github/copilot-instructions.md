# Repository conventions

- Put project documentation in `docs/`. Keep the root `README.md` as the entry point and GitHub agent definitions and instructions in `.github/` for discovery.
- Put reviewable mockups in `design/` and PNG screenshots in `design/screenshots/`. Link design artifacts from `docs/design.md`.
- Every UI change requires a mockup presented to the human and explicit approval before product UI implementation.
- Read product facts from `docs/PRODUCT.md`, the lifecycle from `docs/sdlc-workflow.md`, and accepted lessons from `docs/lessons-learned.md`. Keep live product status out of agent charters.
- When the user asks to commit and push, default to `main` without creating a pull request unless the user requests otherwise. Preserve remote changes and never force-push to bypass divergence.
