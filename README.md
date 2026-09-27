# multiversefighters

Single-file browser fighter — open `index.html`, no build step.

## Visual overhaul (cutscenes · characters · animation · movement · VFX)

### Ultimates are real cutscenes now
- **U at 100%** → super flash: the world freezes and a comic-style cut-in band slides across with the fighter's portrait and the move name.
- Then a real **startup move** plays in gameplay (rush, projectile or ground eruption depending on the fighter). The cutscene **only plays if that startup connects** — a whiff or a block just burns the meter, so cinematics stay special.
- Every fighter has a bespoke multi-shot cinematic (camera moves, dutch angles, eye cut-ins, comic panels, impact frames, onomatopoeia, running hit/damage counter):
  - **KAGE** palm strike → shadow clones juggle through the sky → spiral sphere → dome explosion
  - **REIKA** pass-through slash → frost → the moon rises → giant crescent fang → the ice shatters
  - **VANTA** grapple reel → lights-out brawl lit only by the hits → perched against the moon, cape spread → dive → shadow blast
  - **AEGIS** shield bash → the shield ricochets across comic panels → leap and slam with a hex barrier dome
  - **PYRA** fire pillar → rune circle → a sun forms over her staff → hurled → eruption
  - **NULL-9** visor lock-on HUD → capacitors spin up → the beam → explosion on the horizon
  - **SYLVA** roots bind → spectral arrow draw → world tree → arrow rain → flowers bloom
  - **ZAP** iris-in TA-DA → hammerspace mallet → tornado full of pianos and anvils → anvil drop → iris-out
  - **MORGRIM** scythe hook → void realm gate rises, chains bind → the soul is pulled out → REAP → the gate slams
  - **TITANA** hammer recall → the storm strikes the hammer → rise above the clouds → GOD BOLT
  - **RONIN** back-to-back sheathe in frozen time → sliced panels → a thousand hanging cuts → *click* → the frame shatters
  - **NOVA** gravity well → among the stars a star is born → black hole → supernova
- The AI (Veteran/Master) can land its ultimate on you too — same cutscene, roles swapped.
- **Match intro** (vs CPU, once per match, skippable with J/K/SPACE/ENTER): entrance shots with name cards, then a VS split. **K.O. finish**: freeze-frame impact, slow-mo launch, comic K.O., the winner's victory pose, then ROUND n / FIGHT!

### Characters
- New skeleton renderer: FK arms, IK foot planting, tapered limbs with hands and boots, torso/pelvis shapes, cel shading (the part minus itself nudged toward the light), coloured ink outlines drawn as one silhouette per limb so joints never show seams.
- Anime faces with expressions (neutral, fierce, shout, hurt, grin, eyes-closed); eyes switch to a detailed treatment once a head is big on screen, so cutscene close-ups hold up.
- Every fighter re-dressed as an homage to their source (spiky blond ninja with headband and whiskers; bat-eared cowl and scalloped cape; blue suit with chevron and heater shield; Bleach-style greatsword; winged circlet and storm hammer; rubber-hose toon; samurai with mempo and scabbard…) — archetypes and silhouettes, no copied logos.
- Verlet cloth for capes, scarves, coat tails, braids and long hair — they trail dashes and lift on falls.

### Animation
- Per-fighter fighting stances instead of one shared idle; procedural IK gait locked to ground speed (no foot sliding) with run styles per fighter (ninja run, heavy mech stomp, toon scramble, hover glide).
- Every state blends into the next instead of snapping; attacks keep anticipate → snap → overshoot → settle, now with smear "multiples" on strike frames and filled weapon swooshes.
- Hit reactions by hit height, launches tumble, hard landings knock down, get-up roll, air recovery flip.

### Movement
- **I = Super Dash** — homing flight straight at the opponent (once per airtime), shoulder-checks on arrival, attack out of it.
- Dash, then hold forward to **sprint**; **wall cling + wall jump** at the arena edges; pre-jump squat; **tap SPACE for a short hop**, hold for full height.

### VFX
- Cheap bloom pass (auto-disables on slow machines; **B** toggles it), cached glow sprites for particles, anime hit sparks, impact frames on big hits, speed lines, ground cracks, victim hit-flash.
- Specials now run on game time (they pause during hitstop, slow-mo and cutscenes).

### Also
- New HUD (slanted health bars with trailing damage, portraits, segmented meters, combo counters for both sides), comic-style select screen with bust portraits, stages with sun/moon, god rays, and per-stage weather.
- Fixed: NULL-9's Plasma Railgun never dealt damage (it referenced an undefined variable).

## Previous update
Animation
Knee direction fix — every knee value was positive, so legs bent forward and the run read as backwards. Now negative across all poses.
Proper gait — thigh swings fore/aft, knee tucks on the rear swing, arms counter-swing, two bobs per cycle.
Attacks went 3 phases → 4: anticipate → snap → follow-through → settle. The overshoot is extrapolated from the windup→strike vector, so every attack got it without new poses.
Motion smear trails — FK solves the weapon tip each frame into a tapered ribbon.
Squash & stretch on takeoff, landing, and strike frames.
Secondary motion — hair/cape spring that lags the body, head counter-rotates against torso lean.
Root motion — attacks step into the hit.
New poses: skid, fast-fall, air-dash. Idle got two breathing frequencies plus a weight shift.
Movement
Momentum-based instead of lerp-to-target; +23% top speed, heavier gravity
Double jump (with flip), air dash (aimable W/S), fast fall, skid on hard reversals, dash attack that keeps momentum
Jump moved to SPACE so W/S could become aim directions
Dummy tumbles when launched and wall-bounces
Ultimate charges
12 unique charge stances — all 12 previously used the same arms-back pose
12 unique charge routines — all 12 previously used identical converging orbs
Per-ultimate camera — Vanta charges near-black, Ronin desaturated and near-frozen
Opponents
Dummy became five levels: Dummy, Rookie, Fighter, Veteran, Master
updPlayer generalized to updFighter(f, dt, input) — the AI runs your exact code, so it can't do anything you can't
Brain: approach, retreat, guard, anti-air, dash-in, zoning, low pokes, jump-ins, specials; reacts to your swings, turtles when low
You now have HP — hitstun, blocking (84% reduction), K.O. with slow-mo, round reset, win tally
Opponent + difficulty pickers on the select screen
Camera
Was locked wide; now tracks the midpoint and zooms on separation (2.13× close → 1.05× full stage), plus zoom kick on heavies, pullback for ultimates, snap to the loser on K.O.
Real parallax — skyline layers lag the camera at 55/37/19%
Bugs fixed
hl() would have mutated shared POSE constants
Tornado and Supernova left the player hovering after the ult
Key collision in the ultimate step scheduler
Dummy's st field collided with the new state string
Viewport reporting 0 during layout, and window resize mid-fight, never recovered
Art
Redrew Aegis's shield — the concentric-disc-with-a-star read as a real trademarked design; now an original heater shield with a chevron band.
