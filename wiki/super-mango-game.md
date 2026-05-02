# super-mango-game

> Classic 2D side-scrolling platformer built with C and SDL2

**Repository**: [github.com/jonathanperis/super-mango-game](https://github.com/jonathanperis/super-mango-game) | **Language**: C

## Overview

A fully-featured 2D platformer written in pure C using SDL2, with a WebAssembly build that makes it playable directly in the browser via Emscripten. This is not a game jam prototype -- it's a substantial codebase (~454KB of C) with a proper rendering pipeline, physics system, and extensive content.

## Game Features

### Rendering Engine
- **32 render layers** -- proper depth sorting for backgrounds, midgrounds, entities, and foreground elements
- **Parallax scrolling** -- multiple background layers moving at different speeds for depth illusion
- **Animated water** with visual effects
- **Fog overlay** system
- **HUD** with lives, hearts, coins, and stars display

### Physics & Gameplay
- **Delta-time physics** -- frame-rate independent movement
- **Gamepad support** alongside keyboard input
- **Multiple enemy types**: spiders, jumping spiders, birds, fish, blue flames
- **Environmental hazards**: spikes, swinging axes, circular saws
- **Collectibles**: coins and stars
- **Traversal mechanics**: bouncepads, climbable vines/ladders/ropes, crumble bridges, rails

### Game Systems
- **Lives and hearts** health system
- **Start menu** with navigation
- **Debug overlay** for development
- **Audio system** with music and sound effects

### WebAssembly Build

The game compiles to WebAssembly via Emscripten, allowing browser-based play with no plugins. The build pipeline handles the SDL2 -> Emscripten translation, including asset loading and input mapping.

## Platform Support

| Platform | Build System |
|----------|-------------|
| macOS | Native SDL2 |
| Linux | Native SDL2 |
| Windows | MSYS2 + SDL2 |
| Browser | Emscripten + WebAssembly |

## Architecture

The codebase is structured as a classic game loop:

```
Init -> Load Assets -> Game Loop [ Input -> Update -> Render ] -> Cleanup
```

Key design aspects:
- **Layer-based rendering**: 32 distinct render layers allow fine-grained control over draw order
- **Entity system**: enemies, hazards, and collectibles share a common update/render interface
- **Asset management**: textures, audio, and level data loaded from files
- **Platform abstraction**: SDL2 provides the cross-platform layer, Emscripten provides the web target

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | C |
| Graphics | SDL2 |
| Web Build | Emscripten (WebAssembly) |
| Build | Makefile |
| Scripting | Python (tooling) |

## Topics

`2d-game` `c` `emscripten` `game-development` `gamedev` `open-source` `pixel-art` `platformer` `sdl2` `webassembly`
