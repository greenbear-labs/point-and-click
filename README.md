# Froggy Farm (working title)

An original tap-and-drag play world for toddlers. It is a hub of little games, and each game has its own mascot. There's no text to read, no menus, and no way to fail: everything you tap does something silly.

It's a plain HTML/SVG/JavaScript web app with no build step and no dependencies. All the art is drawn in SVG, every sound and the music are synthesized live with the Web Audio API, and the characters' voice lines use the tablet's own text-to-speech. So there are no asset files to license.

## Games

| Mascot | Game | Status |
| --- | --- | --- |
| Frog | **Bug snack.** Tap his belly: he giggles, says something silly and spits out a bug sticker. Tap a bug and it does its own trick (the ladybug spins, the bee buzzes around, the caterpillar wiggles, the butterfly flutters, the beetle flips over). Drag a bug onto the frog and he slurps it up with his tongue. Sometimes a **magic wand** pops out instead: drop it on the frog, a bug, a flower or the cow and it turns blue, pink, orange, purple, then a crazy rainbow, then back to normal. | Playable |
| Penguin chef | **Ice cream kitchen.** Pick a cone, a chocolate-dipped cone or a cup. Tap the tubs to stack up to 7 scoops, then tap the jars for toppings. There are 12 flavors (including swirl, chocolate chip, bubblegum and cookies and cream) and 10 toppings (including gummy bears, chocolate chips, marshmallows, banana and broccoli); each visit shows a random 6 flavors and 5 toppings, and ringing the bell brings out a new set. Drag the ice cream onto the penguin or a guest and they eat it scoop by scoop. After eating, a guest waves and hops away and a new animal of about the same size takes the spot (puffin, bunny or chick on the counter; polar bear cub, fox or panda; walrus, hippo or sheep). Reactions depend on what's in it: everyone has a favorite flavor (hearts), 5+ scoops is a brain freeze, rainbow makes them dance, sauce + cream + cherry is a super sundae, mint is minty fresh, broccoli gets a silly face, an empty cone is silly. | Playable |
| Ghost | **Pumpkin house.** Tap a pumpkin in the patch (orange, white, green, purple or pink) and it hops onto the stump. Tap the board to carve eyes, a nose and a mouth. There are 8 of each (hearts, stars, moons, diamonds, a piggy nose, vampire fangs, a wiggly or grumpy mouth and more); the board shows a random 4 per row each visit and after each pumpkin goes on the porch. When the face is done it lights up, glows and talks. Drag it onto the spooky house's porch; four glowing pumpkins start a party. The skeletons dance when tapped, the moon sends out bats, a cat lives behind the door and the ghost plays peekaboo. | Playable |
| Elephant | **Car wash.** It goes step by step, and the tool for the next step always glows with a pointing hand (finished steps get a green check). First, three muddy vehicles (truck, bus, tractor, race car, fire truck, police car or ambulance; the emergency ones flash their lights and sirens) wait in the bay: tap one. Then only the wash tools show up: the elephant sprays it with his trunk (or grab the elephant and pull: his trunk stretches like a hose and sprays wherever you point it, any time), the soap covers it in bubbles (tap them to pop), scrub it with a finger or the sponge (tap the soap or sponge, or drag it onto the car and rub), spray again to rinse (soap + water washes off all the mud, and a rainbow appears), then dry it with the fan. Once it's clean and dry, the paint and stickers appear. Paint it from the buckets: red + yellow makes orange, blue + yellow makes green, red + blue makes purple, the same color twice makes it sparkly, and there's a rainbow bucket. Tap or drag stickers on (two googly eyes bring it to life); drag a sticker to move it, or drag it off the car to peel it away. Tap the traffic light and it drives around the block, with a trail from its stickers; sometimes it comes back muddy and needs another wash. The "new car" button (top right) sends it away and brings three new muddy ones. The duck quacks and the sun makes a rainbow. | Playable |
| Robot | **Repair shop.** Three broken gadgets wait on the workbench (a radio, alarm clock, TV, robot dog, toaster or music box; they look sleepy, puff smoke and spark): tap one. It goes step by step, with the next tool glowing and a check on each finished step. There is no pointing hand, and every step is a drag: tapping a tool only makes it do a little trick (the screwdriver spins, the vacuum shakes, the grabber snaps, the parts box hops), and then the robot shows the way with a see-through tool sliding where it should go. Drag the screwdriver onto the four screws and the cover pops off. Drag the vacuum around (or rub with a finger) to clean out the dust bunnies; tickling the dusty insides makes it sneeze. Something silly is always hiding inside: a mouse that runs away, a stinky sock that lands on the robot's head, a cookie the robot eats, a rubber duck or a marble. Grab the grey broken parts with a finger or the grabber and carry them to the junk bin (drop one anywhere else and it waits on the bench), then drag shiny new parts out of the parts box onto the gadget (batteries, gears, light bulbs and springs, with dashed outlines showing where they go). Drag the cover back on (it glows when it's time) and screw it shut, then slide the red power switch all the way across: lightning, a power-up sound, and the gadget wakes up happy and does its job (the radio plays music, the clock rings, the TV shows rainbow colors, the dog barks and wags, the toaster pops toast, the music box spins its star). Then drag silly add-ons onto it: propeller hat (it flies), rocket (it zooms in a loop), googly eyes, a mustache (deep fancy voice), waving arms and party lights. Tapping an add-on shows off its own little animation; drag one off the gadget to take it away. Tap the gadget and it does everything at once. The "next" button sends it home (flying away if it has a propeller) and brings three new broken ones. Tapping screws, dust bunnies, parts and the cover makes them spin, hop, shiver or clank. The robot reacts to taps (waves, spins, head on a spring, heart eyes, dance, antenna zap), the lamp turns the lights off, the pegboard tools clank, the junk bin rattles and the oil can oils the gadget. If a step takes a while, the robot shows how again. | Playable |

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
- `js/games/robot.js`: the robot repair shop.
- `js/games/icecream.js`: the ice cream kitchen.
- `js/games/pumpkin.js`: the pumpkin house.
- `js/games/carwash.js`: the elephant car wash.
- `sw.js`, `manifest.webmanifest`, `icons/`: what makes it an installable, offline app.

To add a game, draw its screen, then call `App.register({ id, screen, enter, leave, clear })` and point a hub tile's `data-game` at that id. Remember to add its files to `ASSETS` in `sw.js` and bump `CACHE`.
