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
| **Versus CPU** | Pick your fighter and opponent, then a difficulty: Novice, Fighter, Master or Shadow. Best of three rounds, 99-second timer. |
| **Versus Player** | Two players on one keyboard, or with gamepads. |
| **Training** | A dummy that stands, crouches, blocks, jumps or fights back. Health regenerates, meter can be infinite, and the last combo is shown. |

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
- **Audio:** WebAudio only. Filtered noise gives the swings and impacts,
  detuned partials the steel, and sub drops the weight. A convolution reverb
  and a quiet taiko pattern sit under the fight.
