# LittleGuys

> A Worms-inspired 2D artillery game built in Haskell with the Gloss graphics library.

![Haskell](https://img.shields.io/badge/Haskell-5D4F85?style=flat&logo=haskell&logoColor=white)
![Status](https://img.shields.io/badge/status-complete-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

## Overview

LittleGuys is a turn-based 2D artillery game inspired by Worms, developed as a university project at Universidade do Minho. Two or three teams of worms battle on destructible terrain using weapons and explosives.

Built entirely in Haskell using a purely functional approach — game state is immutable, and all updates are pure functions.

## Gameplay

- Turn-based multiplayer (2–3 teams, up to 5 worms per team)
- Destructible terrain with water, earth, stone and rock tiles
- Weapons : dynamite, missiles, mines and barrels
- Real-time animations with frame-by-frame sprite rendering
- Scrollable camera that follows the active worm
- Win screen when all enemy worms are eliminated

## Technical Highlights

| Feature | Implementation |
|---|---|
| Game loop | Gloss `play` with pure state transitions |
| Rendering | Custom sprite sheet parser + frame animation system |
| Physics | Turn timer, gravity, projectile trajectories |
| Camera | Smooth follow camera with bounds clamping |
| State machine | `Menu → TeamSetup → Jogo → WinScreen` |
| Randomness | Seeded `System.Random` for map generation |
| Input | Custom key set tracking via `Data.Set` |

## Project Structure

```
app/
  Main.hs        → Entry point, Gloss setup
  Types.hs       → All game types and data structures
  Worms.hs       → Core game state and team configuration
  Eventos.hs     → Input handling and event processing
  Tempo.hs       → Game loop update logic
  Desenhar.hs    → Rendering pipeline
  Mapa.hs        → Map generation and terrain
  Camera.hs      → Camera system
  Sprites.hs     → Sprite loading and animation
assets/
  sprites/       → Frame-by-frame character animations
  objects/       → Weapon sprites
  *.bmp          → Background and UI textures
```

## Installation

### Prerequisites
- [GHC](https://www.haskell.org/ghc/) (Haskell compiler)
- [Cabal](https://www.haskell.org/cabal/) or [Stack](https://docs.haskellstack.org/)
- Gloss library

### Run

```bash
git clone https://github.com/Oshyma/LittleGuys
cd LittleGuys
cabal run worms-game
```

## Authors

Developed in collaboration with @Totsugeeki for the Laboratórios de Informática course at **Universidade do Minho**, 2025–2026.
