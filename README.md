# SuitUp

SuitUp is a proposed outfit-feedback app. A person chooses an occasion or event, takes or selects a photo of their outfit, and receives a score out of 10 with one decimal place and practical feedback about how well the outfit fits the occasion.

## Planned experience

- **Choose the occasion:** Tell the app the event or theme the outfit is for.
- **Add an outfit photo:** Take a photo or select one.
- **Get useful feedback:** See a one-decimal score, what worked, what fit the theme less well, and suggestions for next time.
- **Explore the outfit:** Spin a friendly, cartoon-style 3D avatar wearing a representation of the outfit through different angles.
- **Fidget interaction:** A small rotatable object or icon adds an optional tactile-feeling moment to the experience.

The first requested design pass covers the iOS home and results screens, followed by a responsive web experience that matches the iOS design as closely as the platform allows.

## Project status

This repository currently contains product and agent-swarm documentation plus an interactive first-pass design mockup. The user approved the cartoon-avatar mockup on October 25, 2026. The production app interface has not been implemented. Future UI changes still require mockup approval before implementation.

The app name `SuitUp` is inferred from the repository name and is not yet confirmed as the customer-facing brand. Monetization, rating methodology, how an outfit photo becomes a useful 3D avatar representation, avatar customization, image handling, accounts, and saved-result behavior also remain open decisions. No market or competitor research has been conducted.

## First-pass design

Open [`design/first-pass-mockup.html`](design/first-pass-mockup.html) for the iOS home and fit-note screens and the responsive web adaptation. The mockup uses an annotated fitting-sheet concept, includes light/dark previews, a rotatable, cartoon-style 3D avatar, and a separate fidget token. The sample avatar and rating are synthetic; the avatar is an original generic concept, not a copy of an existing character brand. This is a design artifact for review, not production app code.

PNG captures of the iOS screens and desktop/mobile web screens in both themes are in [`design/screenshots/`](design/screenshots/). See the [design record and screenshot gallery](docs/design.md).

## Product and design documentation

- [Documentation index](docs/README.md)
- [Product brief](docs/PRODUCT.md)
- [Agent swarm charters](.github/agents/README.md)
- [Shared SDLC workflow](docs/sdlc-workflow.md)

Keep project documentation in `docs/` and mockups and their PNG screenshots in `design/`. The root README remains the entry point; GitHub agent definitions and repository instructions remain in `.github/` for discovery.
