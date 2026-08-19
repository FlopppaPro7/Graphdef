# Graphwar Tower Defense

A single-file HTML5 Canvas tower-defense game where **every turret fires along a
math equation you type** (`y = f(x)`). Clean ES6-class engine, safe math parser
(no `eval`), fixed-timestep loop, seven tower archetypes with unique upgrades,
and math-countered enemies.

Play by opening `index.html` in any modern browser — no build step, no
dependencies.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The game. Served at `/` by Vercel. |
| `graphwar-tower-defense.html` | Identical standalone source (kept for reference). |
| `graphwar-td-artifact.html` | Wrapper-stripped build used for the Claude Artifact preview. |
| `vercel.json` | Static-site config (clean URLs). |

`index.html` and `graphwar-tower-defense.html` have the same contents; edit the
game in one and copy to the other (`cp graphwar-tower-defense.html index.html`).

## Deploy to Vercel

This is a **static site** — no framework, no build command. Vercel serves
`index.html` at the root automatically.

### Option A — Connect the GitHub repo (recommended)

1. Push this repo to GitHub (already done on branch
   `claude/graphwar-tower-defense-96rrgb`; merge to your default branch to
   auto-deploy production).
2. Go to <https://vercel.com/new> and **Import** this GitHub repository.
3. When prompted for settings, leave everything at defaults:
   - **Framework Preset:** `Other`
   - **Build Command:** _(empty)_
   - **Output Directory:** _(empty / leave as root)_
   - **Install Command:** _(empty)_
4. Click **Deploy**. Vercel gives you a URL like
   `https://<project>.vercel.app` serving the game.

Every future push to the connected branch redeploys automatically.

### Option B — Vercel CLI

```bash
npm i -g vercel      # once
vercel               # from the repo root -> preview deploy
vercel --prod        # production deploy
```

Accept the defaults (framework: Other, no build command).

## Gameplay quick start

1. Pick a **Tower Type**.
2. Type an equation in `y =` (e.g. `0*x + 2`, `sin(x)`, `-0.5*(x-2)^2 + 4`).
3. Click **Place Turret**, then click the grid to drop it. Bullets ride the
   curve **rightward**, so place turrets to the *left* of the incoming lane.
4. Click **Start Wave**. Survive all 20 waves to win.

Click a placed turret to **Upgrade** (a unique mechanic change) or **Sell** it.
