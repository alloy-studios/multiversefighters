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
| **Paths** | Every special fighter has a path: four fights in a row, with a few lines before and after each one. The fights get harder as you go. Lose one and you can continue from it. |
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
- **Path scenes:** `J` / `Enter` shows the next line and `Esc` skips the scene.
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
| **GOJO** | The Strongest *(limited time)* | none | *Hollow Purple*: the blindfold comes down, Blue forms in one hand and Red in the other, and he brings them together. What he lets go gouges a burning trench through the stage and goes off somewhere far out of sight. Below 35% health it becomes *Domain Expansion: Infinite Void* |
| **GOKU** | Ultra Instinct *(limited time)* | open hand | *Kamehameha*: you swing at him again and again and never touch him. One palm into the gap, a flurry from every side, then he vanishes, reappears high above you, and drives you into the ground with a beam |

Each fighter also has a three-hit light chain, heavy, overhead, low and sweep,
air attacks, a throw, and three specials: projectiles, rushes, anti-airs, a
grab-range hook and a ground eruption.

## Special fighters

Some fighters are not on the roster all the time.

- **Limited time:** playable only while their event runs. The title screen and
  the select screen show how long is left. Clear their path before the event
  ends and they stay on your roster for good. After the event, they disappear
  for anyone who didn't.
- **Unlockable:** earned by playing, for example by winning matches, landing
  ultimates, beating a difficulty or clearing a path. Until then they show on
  the select screen as a locked card with the condition and your progress.
  When you earn one, a notice pops up and they stay unlocked. There are none
  yet; the first one is on the way.

Progress is saved in your browser. Played on
[alloy-studios.github.io/umbra](https://alloy-studios.github.io/umbra/) while
signed in to an Alloy account, it also follows you to any device (see
[Alloy accounts](#alloy-accounts)).

To try every special fighter without saving anything, add `?unlock` to the
address, e.g. `index.html?unlock`. It only works on your own machine (opened
as a file, or from `localhost` / `127.0.0.1`); anywhere else it does nothing.

### GOJO: The Strongest

*Limited time: 26 September to 26 October 2026.* He fights with his hands in
his pockets.

| Input | Move |
|---|---|
| Light chain, overhead, low, sweep, air attacks | Kicks. The hands stay in the pockets. |
| Heavy | A two-finger flick |
| Special | *Blue*: an orb that drags you in and hits five times |
| → + Special | *Red*: a blast that throws you across the stage |
| ← + Special | *Infinity*: anything that touches him stops. A melee attacker freezes for a moment and he counters. Projectiles vanish. It doesn't stop ultimates. |
| Ultimate | *Hollow Purple* |
| Ultimate below 35% health | *Domain Expansion: Infinite Void* |

**His path, *The Strongest, Visiting*:** a stranger in a blindfold walks out of
the rain and picks four fights: Bolt, Vex, Goliath and Grim.

### GOKU: Ultra Instinct

*Limited time: 28 September to 8 November 2026.* A silver aura, and he never
blocks.

| Input | Move |
|---|---|
| Hold back | *Ultra Instinct*: instead of blocking, his body moves on its own. He sways back or ducks under the hit and leaves an afterimage where it was going. No chip damage, and the attacker gets nothing to cancel from. Projectiles fly on past. While you hold back with an attack coming, he weaves. Throws still catch him. |
| Light chain, heavy, overhead, low, sweep, air attacks | Fast punches and kicks, with afterimages on the big ones |
| Special | *Ki Blast*: one quick shot from an open palm |
| → + Special | *Instant Transmission*: two fingers to his forehead, gone, and back behind you with a palm strike |
| ← + Special | *Dragon Fist*: a rising punch, invincible on startup |
| Ultimate | *Kamehameha* |

**His path, *A Good Fight*:** something falls out of the sky over the
monastery, and it wants a fight: Sol, Bolt, Goliath and Grim.

The event dates are in `index.html`: search for `SPECIAL.gojo` or
`SPECIAL.goku`. `from` is the first day and `to` is the day after the last
(local dates). Events can overlap; the title screen lists every one that is
on. Remove an entry to make that fighter permanent.

## Alloy accounts

UMBRA runs on [alloy-studios.github.io](https://alloy-studios.github.io/umbra/)
under the id `umbra`, and syncs its save to the player's Alloy account:

- **What syncs:** everything the game keeps under `umbra.*` in localStorage:
  your record (wins, ultimates, hardest difficulty beaten), cleared paths, kept
  limited guests and unlocked fighters.
- **On sign-in** the account's save and the browser's are merged, so nothing is
  lost: every list is the union of both and every count the higher of the two.
  Nothing is written to the account before that first load has answered.
- **Saving:** clearing a path, keeping a guest or unlocking a fighter is sent at
  once; wins and ultimates go out with the site's routine batching. The game
  adopts whatever the server replies with.
- **Status:** a small line on the title and results screens says whether
  progress is saved to the account, syncing, or that signing in would keep it.
- **Opened any other way** (as a file, from its own repo) there is no account,
  and the game runs on its browser save exactly as before.

The server checks every save with [`alloy/validator.js`](alloy/validator.js).
Every field is cleaned and clamped, never rejected. Wins and ultimates can only
rise as fast as the game's own round timers and unskippable cutscenes allow (the
working is in the file). A limited guest is only kept if the server's own clock
is inside that fighter's event window, whatever the player's clock says. When a
special fighter or a path is added to the game, add it to the tables at the top
of the validator too.

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
  path scenes, Gojo's ultimates and Goku's close-ups get angles other than side-on. The angles
  are drawn, not modelled: sets are laid out with a pinhole camera the way a
  background painter rules vanishing lines, and the characters are flat
  drawings for each view, placed and scaled by depth.
- **Audio:** WebAudio only. Filtered noise gives the swings and impacts,
  detuned partials the steel, and sub drops the weight. A convolution reverb
  and a quiet taiko pattern sit under the fight.
