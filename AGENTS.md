# Agent Instructions

This repository is a small Hugo blog that uses the Ananke theme as a git submodule. Keep instructions minimal, prefer the existing project files over assumptions, and avoid changing generated output.

## Key Files

- Site config: [hugo.toml](hugo.toml)
- Post template: [archetypes/default.md](archetypes/default.md)
- Published content: [content/posts/](content/posts/)
- Homepage styling: [assets/css/landing.css](assets/css/landing.css)
- CI build reference: [.github/workflows/hugo.yaml](.github/workflows/hugo.yaml)

## Working Rules

- Prefer editing `content/`, `layouts/`, `assets/`, and `hugo.toml` over changing `themes/ananke/` directly.
- Treat `themes/ananke/` as third-party code. Only modify it when the task explicitly requires a theme patch.
- Do not edit generated or ignored output: `public/`, `resources/_gen/`, and `.hugo_build.lock`.
- Preserve TOML frontmatter in posts. New posts should follow [archetypes/default.md](archetypes/default.md).
- Published posts must set `draft = false`.

## Validation

- Cheapest local validation: `hugo --gc --minify`
- For iterative content or styling changes: `hugo server`
- If local behavior needs to match CI, follow [.github/workflows/hugo.yaml](.github/workflows/hugo.yaml). The workflow uses Hugo extended and checks out submodules recursively.
- If `hugo` is unavailable locally, say so and fall back to static review instead of changing the build setup.

## Change Guidance

- Content updates usually belong in [content/posts/](content/posts/).
- Homepage style changes usually belong in [assets/css/landing.css](assets/css/landing.css).
- Blog styling currently falls back to the default Ananke theme unless the task explicitly reintroduces local theme overrides.
- Site metadata and theme selection belong in [hugo.toml](hugo.toml).
- Clone or update the repository with submodules enabled so [themes/ananke/](themes/ananke/) is present.