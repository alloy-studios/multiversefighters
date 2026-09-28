# UMBRA — a duel of shadows

A 2D fighting game in the spirit of Street Fighter, Dragon Ball FighterZ and
Shadow Fight, played entirely in silhouette. Every fighter is pure black with
exactly one colour: a pair of glowing eyes that leave trails when they move,
a lit blade edge, a burning hammer head. The stages are bright, layered
landscapes behind them, so every pose reads through its outline.

Everything is a single `index.html`. There are no images, sprites or sound
files: the fighters are drawn procedurally from a skeleton, the stages are
generated shape by shape, and all audio is synthesized in the browser.

**Play:** open `index.html` in a modern browser (Chrome, Edge, Firefox or Safari).

---

## Modes

| Mode | |
|---|---|
| **Story** | Pick a shadow and play their four chapters: a prologue, a rival, and the Keeper of the Last Gate (or, for Grim, the one man who walked back out of it). Scenes between the fights are told in drawn shots with subtitles, and each fighter has their own ending. Lose a chapter and you can continue from it. |
| **Versus CPU** | Pick your fighter and opponent, then a difficulty: Novice, Fighter, Master or Shadow. Best of three rounds, 99-second timer. |
| **Versus Player** | Two players on one keyboard, or with gamepads. |
| **Training** | A dummy that stands, crouches, blocks, jumps or fights back. Health regenerates, meter can be infinite, and the last combo is shown. |
| **Lore** | The world, the eight fighters and their rivalries. Rival finishers you have already seen can be watched again from here. |

## Controls

| | Player 1 | Player 2 |
|---|---|---|
| Move / crouch | `A` `D` / `S` | `←` `→` / `↓` |
| Jump | `W` or `Space` | `↑` |
| Light (press three times for a chain) | `J` | `Numpad 1` or `,` |
| Heavy | `K` | `Numpad 2` or `.` |
| Special | `L` | `Numpad 3` or `/` |
| Throw | `I` | `Numpad 4` or `;` |
| Ultimate (full meter) | `U` | `Numpad 5` or `'` |
| Dash | `Shift`, or double-tap a direction | `Numpad 0` / right `Shift` |

- **Block:** hold away from your opponent. Crouch-block (`↙`) for lows. Overheads must be blocked standing.
- **Directional attacks:** `→ + Heavy` is an overhead. `↓ + Light` is a low. `↓ + Heavy` is a sweep that knocks down.
- **Specials:** `Special`, `→ + Special` (rush) and `← + Special` (rising anti-air, invincible on startup).
- **Throws:** press `Throw` up close. Hold back to throw behind you. Press `Throw` as you're grabbed to break it.
- **Cancels:** lights chain into each other, into heavies and into specials. Normals and specials cancel into your ultimate.
- **Other keys:** `Esc` / `P` pauses and shows the full move list. `M` toggles sound.
- **Story scenes:** `J` / `Enter` shows the next line and `Esc` skips the scene. During a rival finisher, press any button twice to skip it.
- **Gamepad:** stick or d-pad to move, `A` jump, `X` light, `Y` heavy, `B` special, `RB` throw, `LB` dash, `RT` ultimate, `Start` pause.

## Ultimates

Ultimates cost a full meter. The opening strike has to connect. When it does,
the fight cuts away to a short animated sequence: close-ups, whip pans, slow
motion, and single two-tone impact frames. There are no speech bubbles and no
exclamation text. Each fighter has one:

| Fighter | | Weapon | Ultimate |
|---|---|---|---|
| **ASHEN** | The Crimson Revenant | odachi | *Crimson Requiem*: time stops and the world drains to grey while eight red cuts hang in the air around you, then colour floods back as they all bloom at once |
| **VEX** | Blade of the Silent Moon | twin daggers | *Moonless Night*: the light dies until only her eyes remain, and each cut is lit for a single frame |
| **GOLIATH** | Forgeborn Juggernaut | forge hammer | *Forgefall*: he slams you skull-first into the floor, the cracks run molten, and fire bursts from every one of them |
| **SOL** | The Last Monk | open hand | *Hundred Suns*: a storm of palms as light breaks out behind him, then a sun drawn between his hands carries you across the ground |
| **MORROW** | Witch of the Hollow Mire | hex staff | *Hollow Grasp*: hands of shadow climb out of the swamp mist and drag you into her sigil |
| **GRIM** | Keeper of the Last Gate | scythe | *The Last Gate*: a gate grows out of the earth and opens, and he reaps your shadow into it |
| **BOLT** | Stormfist | storm gauntlets | *Stormbreaker*: a rush cut like a boxing highlight reel, then lightning strikes his raised fist and he drives it straight through you |
| **RIN** | Petal Lancer | spear | *Thousand Petals*: the spear becomes a wheel of cuts, a whirlwind of petals pins you, and she dashes straight through it |

Each fighter also has a three-hit light chain, heavy, overhead, low and sweep,
air attacks, a throw, and three specials: projectiles, rushes, anti-airs, a
grab-range hook and a ground eruption.

## The story

Nine years ago the sun stopped at the edge of the world. It has not risen and it
has not set, and everything that lived in its light became a shadow of itself.
Every shadow keeps one ember, the last colour it had. Carry enough embers
through the Last Gate, the old stories say, and the sun will rise again. The
Gate opens for one shadow at a time, and its keeper decides which.

| Rivals | |
|---|---|
| **Sol** · **Morrow** | *The Dawn Flame.* Morrow walked into the High Temple and took the fire its thirty-one monks had kept alive through the Dusk. Sol is the one she left breathing. |
| **Ashen** · **Vex** | *The Gates of Ashfield.* Vex was paid to open Ashfield's gates. Ashen died holding them, went through the Last Gate, and walked back out. |
| **Bolt** · **Goliath** | *The Stolen Storm.* Bolt broke the storm out of the Crucible's forge. Goliath was made to guard it. |
| **Rin** · **Grim** | *Hana.* Rin's sister carried Petal Hill's embers through the Gate, and it kept her. |
| **Grim** · **Ashen** | *The One Who Returned.* Nobody comes back out of the Gate. Ashen did. |

### Rival finishers

Some rivalries end in a long cinematic instead of the normal ultimate. It runs
for about 40 seconds and has subtitles, a score, and shots from every angle:
bird's-eye, worm's-eye, over the shoulder and extreme close-up. Flashbacks are
graded to sepia, with only the light keeping its colour.

| Finisher | How to see it |
|---|---|
| **The Last Dawn** | As Sol, win the deciding round against Morrow with *Hundred Suns* on the High Temple stage. It works in Story, Versus CPU and Versus Player. |

The angles are drawn, not modelled. The sets are laid out with a pinhole
camera the way a background painter rules vanishing lines. The characters are
flat drawings for each view: front, back, from above, and eyes in close-up.
They are placed and scaled by depth. Anything standing in front of a light cuts
itself out of the glow layer, so it reads as a silhouette against it.

## Stages

Ashfield · Silent Grove · The Crucible · High Temple · Hollow Mire · The Last Gate · Zenith · Petal Hill

Each stage has parallax silhouette layers, atmospheric fog, a blurred
foreground and its own weather: embers, falling leaves, forge sparks, marsh
wisps, grave mist, rain with lightning, or blossom petals.

## How it's built

- **Fighters:** each fighter is a two-bone skeleton. The legs are solved by
  inverse kinematics, so feet stay planted. Every attack is a keyframed clip
  with anticipation, a snap, follow-through and settle. Hair, coats, scarves
  and tassels are verlet cloth that reacts to motion.
- **Hitboxes** come from the pose itself: a sword hits where the drawn blade
  is, and a kick where the leg is.
- **Rendering:** there are two layers. Ink goes on the main canvas. Light
  (eyes, edges, energy, trails) goes on a glow canvas, which is added back and
  bloomed. That keeps the blacks pure black.
- **Cinematics:** the engine plays shot lists in *story time*, with speed
  ramps for slow motion, camera moves with roll, backdrop swaps, letterboxing
  and two-tone impact frames.
  Shots can also be drawn by hand for their own camera angle. That is how the
  story scenes and the rival finishers get angles other than side-on.
- **Audio:** WebAudio only. Filtered noise gives the swings and impacts,
  detuned partials the steel, and sub drops the weight. A convolution reverb
  and a quiet taiko pattern sit under the fight.
