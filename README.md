# Froggy Farm (working title)

An original tap-and-drag play world for toddlers. It is a hub of little games, and each game has its own mascot. There's no text to read, no menus, and no way to fail: everything you tap does something silly.

It's a plain HTML/SVG/JavaScript web app with no build step and no dependencies. All the art is drawn in SVG, every sound and the music are synthesized live with the Web Audio API, and the characters' voice lines use the tablet's own text-to-speech. So there are no asset files to license.

## Games

| Mascot | Game | Status |
| --- | --- | --- |
| Frog | **Bug snack.** Tap his belly: he giggles, says something silly and spits out a bug sticker. Tap a bug and it does its own trick (the ladybug spins, the bee buzzes around, the caterpillar wiggles, the butterfly flutters, the beetle flips over). Drag a bug onto the frog and he slurps it up with his tongue. Sometimes a **magic wand** pops out instead: drop it on the frog, a bug, a flower or the cow and it turns blue, pink, orange, purple, then a crazy rainbow, then back to normal. | Playable |
| Penguin chef | **Ice cream kitchen.** Pick a cone, a chocolate-dipped cone or a cup. Tap the tubs to stack up to 7 scoops (strawberry, chocolate, vanilla, mint, blueberry, rainbow), then tap the jars for sprinkles, a cherry, chocolate sauce, whipped cream or candy stars. Drag the ice cream onto the penguin, the walrus, the polar bear cub or the puffin and they eat it scoop by scoop. Reactions depend on what's in it: everyone has a favorite flavor (hearts), 5+ scoops is a brain freeze, rainbow makes them dance, sauce + cream + cherry is a super sundae, mint is minty fresh, an empty cone is silly. Tap the bell and everyone hops. | Playable |
| Ghost | **Pumpkin house.** Tap a pumpkin in the patch (orange, white, green, purple or pink) and it hops onto the stump. Tap the board to carve eyes, a nose and a mouth (circles, triangles, hearts, stars, smiles, a toothy grin, an "ooh" or a silly tongue). When the face is done it lights up, glows and talks. Drag it onto the spooky house's porch; four glowing pumpkins start a party. The skeletons dance when tapped, the moon sends out bats, a cat lives behind the door and the ghost plays peekaboo. | Playable |
| Elephant | **Car wash.** A muddy truck, bus, tractor or race car waits in the bay: tap one. The elephant sprays it with his trunk, the soap covers it in bubbles (tap them to pop), rub it with a finger or tap the sponge to scrub, spray again to rinse (soap + water washes off all the mud, and a rainbow appears), then dry it with the fan. Paint it from the buckets: red + yellow makes orange, blue + yellow makes green, red + blue makes purple, the same color twice makes it sparkly, and there's a rainbow bucket. Tap or drag stickers on (two googly eyes bring it to life). Tap the traffic light and it drives around the block, with a trail from its stickers; sometimes it comes back muddy. The duck quacks and the sun makes a rainbow. | Playable |

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
- `js/kit.js`: shared helpers for a game screen (sparkles, speech bubbles, tweens).
- `js/games/frog.js`: the frog game.
- `js/games/icecream.js`: the ice cream kitchen.
- `js/games/pumpkin.js`: the pumpkin house.
- `js/games/carwash.js`: the elephant car wash.
- `sw.js`, `manifest.webmanifest`, `icons/`: what makes it an installable, offline app.

To add a game, draw its screen, then call `App.register({ id, screen, enter, leave, clear })` and point a hub tile's `data-game` at that id. Remember to add its files to `ASSETS` in `sw.js` and bump `CACHE`.
