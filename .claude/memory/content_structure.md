---
name: Profile README Content Structure
description: Section layout, terminal aesthetic conventions, project table format, wiki documentation scope
type: project
---

## README Section Layout (160 lines)

| Line Range | Section | Header Style |
|-----------|---------|--------------|
| 1-13 | Profile | C# code block defining `Developer` struct |
| ~15-30 | Who Am I | `$ whoami` — bio, languages, philosophy |
| ~32-70 | Projects | `$ ls ~/projects --sort=stars` — 10-project table |
| ~72-95 | Tech Stack | `$ cat /proc/tech_stack` — ASCII table |
| ~97-130 | System Info | `$ neofetch` — contact, system emulation |
| ~147-169 | Contribution | Animated snake SVG (light/dark responsive) |

## Terminal Aesthetic Rules

- Section headers are shell commands: `$ whoami`, `$ ls`, `$ cat /proc/tech_stack`, `$ neofetch`
- Tech displayed as ASCII art tables
- Profile rendered as a C# struct
- Code blocks use language syntax highlighting
- Tables use GitHub Markdown format

## When to Update

- **Adding a new repo**: Update the projects table (`$ ls ~/projects/active`)
- **Changing tech stack**: Update the `$ cat /proc/tech_stack` section

## Wiki (jonathanperis.wiki/)

Wiki markdown in `wiki/` documents the public projects, architecture patterns, and how those projects measure behavior.

## Automated Content

- Snake animation SVGs generated daily by `Platane/snk` GitHub Action
- Pushed to `output` branch, referenced via `<picture>` element for dark/light mode
