# jonathanperis — Claude Code Guide

GitHub profile README repository. Terminal-themed developer portfolio showcasing microservices, game dev, and polyglot performance engineering.

---

## Purpose

This is a **special GitHub repository** — its README.md is rendered as the profile page at `github.com/jonathanperis`.

---

## Structure

```
jonathanperis/
├── README.md                   # Profile README (169 lines, terminal aesthetic)
├── LICENSE                     # MIT License
├── .editorconfig               # UTF-8, LF, 4-space indent
├── .gitignore                  # .DS_Store only
├── .github/
│   ├── dependabot.yml          # Weekly GitHub Actions updates
│   └── workflows/
│       └── snake.yml           # Daily snake animation generation
└── jonathanperis.wiki/         # GitHub Wiki (separate git repo)
    ├── Home.md                 # Wiki index
    ├── About.md                # Extended bio
    ├── cpnucleo.md             # Project deep dive
    ├── rinha-de-backend.md     # Challenge documentation
    ├── super-mango-game.md     # Game dev docs
    ├── portfolio-site.md       # Portfolio site docs
    ├── blazor-mudblazor-starter.md
    ├── tech-stack.md           # Complete tech inventory
    ├── architecture-patterns.md
    └── performance-engineering.md
```

---

## README Sections

| Section | Command Header | Content |
|---------|---------------|---------|
| Profile | `$ whoami` | Developer bio + languages |
| Projects | `$ ls ~/projects --sort=stars` | 10 projects table with stars |
| Tech Stack | `$ cat /proc/tech_stack` | ASCII table of technologies |
| Benchmarks | `$ cat benchmarks.md` | Rinha implementations comparison |
| System Info | `$ neofetch` | Contact info, system emulation |
| Contribution Graph | — | Animated snake SVG (light/dark) |

---

## Automated Workflows

- **snake.yml**: Runs daily (`0 0 * * *`) via `Platane/snk` action to generate contribution graph snake animation SVGs. Pushes to `output` branch.

---

## Content Guidelines

- Terminal aesthetic: section headers use shell commands (`$ whoami`, `$ ls`, `$ cat`)
- Code-first design: tech stack as ASCII art, profile as C# struct
- Polyglot philosophy: always showcase multiple languages
- Keep project table updated when adding/removing repos
- Wiki documents each project's architecture and decisions
