# Froggy Farm (working title)

An original tap-and-drag play world for toddlers. It is a hub of little games, and each game has its own mascot. There's no text to read, no menus, and no way to fail: everything you tap does something silly.

It's a plain HTML/SVG/JavaScript web app with no build step and no dependencies. All the art is drawn in SVG, every sound and the music are synthesized live with the Web Audio API, and the characters' voice lines use the tablet's own text-to-speech. So there are no asset files to license.

## Games

| Mascot | Game | Status |
| --- | --- | --- |
| Frog | **Bug snack.** Tap his belly: he giggles, says something silly and spits out a bug sticker. Tap a bug and it does its own trick (the ladybug spins, the bee buzzes around, the caterpillar wiggles, the butterfly flutters, the beetle flips over). Drag a bug onto the frog and he slurps it up with his tongue. Sometimes a **magic wand** pops out instead: drop it on the frog, a bug, a flower or the cow and it turns blue, pink, orange, purple, then a crazy rainbow, then back to normal. | Playable |
| Penguin | **Ice cream kitchen.** Make any ice cream through a few prep steps, add toppings, then hand it to the penguin or the other characters to eat. | Next up (tile in the hub says "coming soon") |

The frog's pond also has other things to poke at: the cow moos, the flowers chime (and every third tap a butterfly sticker pops out), the pond splashes, the clouds rain, and the sun switches day to night (tap the moon to switch back; the music turns into a lullaby).

## Run it

Any static file server works:

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Put it on the tablet

1. Host the folder on any HTTPS static host (GitHub Pages works: Settings → Pages → Source: **GitHub Actions**; the included workflow deploys `main`).
2. Open the site on the tablet and add it to the home screen (iPad: Share → Add to Home Screen; Android Chrome: menu → Install app).
3. Open it from the home screen once while online. After that it works offline, full screen, in landscape.
4. To keep little fingers in the game, turn on **Guided Access** (iPad: Settings → Accessibility → Guided Access) or **App pinning** (Android: Settings → Security).

## Grown-up corner

Press and hold the **top-left corner** for 3 seconds. A panel opens where you can turn the music and voice on or off, clear the stickers, go back to the game picker, or go full screen.

## Code map

- `index.html`: the hub and the frog's scene, drawn as SVG.
- `js/app.js`: the hub, shared voice and settings, the grown-up panel, full screen and offline setup.
- `js/audio.js`: all sound effects and the music loop.
- `js/games/frog.js`: the frog game.
- `sw.js`, `manifest.webmanifest`, `icons/`: what makes it an installable, offline app.

To add a game, draw its screen, then call `App.register({ id, screen, enter, leave, clear })` and point a hub tile's `data-game` at that id. Remember to add its files to `ASSETS` in `sw.js` and bump `CACHE`.
