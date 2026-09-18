# multiversefighters

Animation
Knee direction fixed. Every knee value in the pose table was positive, so legs bent forward like a bird's — that's why the run read as backwards. Knees are now always negative across every pose (run, jump tuck, crouch, dash, hurt).
Real gait. Thigh swings fore/aft, knee tucks hardest on the rear swing so the heel kicks up behind, arms counter-swing against their own leg, two body bobs per cycle.
Attacks went from 3 phases to 4 — anticipate → snap → follow-through → settle, each with its own easing curve. The overshoot pose is extrapolated from the windup→strike vector, so all 120 normals got follow-through without authoring new poses.
Motion smear trails. Forward-kinematics solves the front hand/weapon tip each frame and feeds a 16-sample tapered ribbon.
Squash & stretch on takeoff, landing (harder = more), and every strike frame.
Secondary motion — hair and cape on a velocity-driven spring that lags the body; head counter-rotates against torso lean on every pose.
Root motion — attacks step into the hit.
Idle runs two breathing frequencies plus a slow weight shift so the loop isn't visible.
Movement
Momentum-based instead of lerp-to-target; ~23% higher top speed, heavier gravity
Double jump with a full-body flip
Air dash, one per airtime, aimable with W/S
Fast fall
Skid on hard direction reversals, with its own pose and dust
Dash attack — keeps your momentum
Jump moved to SPACE so W/S could become aim directions
Moveset
6 moves per character → 14. 168 total, all hand-authored.
Added down-tilt, down-heavy, up-tilt, up-heavy, neutral aerial, and a spike (positive downward knockback)
3 specials instead of 1 — neutral, down (S+L), up (W+L, doubles as recovery). 9 new special kinds: charged orb slam, ground quake, armed mine, counter stance, lingering field, self-buff, rising attack, teleport, rocket thrust.
Every light and heavy is now its own move with its own pose, damage, reach, hit height, timing and knockback — previously all 12 characters shared four generic definitions
TAB move list in-game, plus the full list on the select screen
VFX
Two independent layers: a shape per attack (9: jab, arc, wide, drop, rise, stab, pound, spin, blast) and an element per fighter (12: fire, frost, volt, shadow, holy, plasma, nature, toon, void, cosmic, wind, blade)
Elements behave differently, not just recolor — void implodes inward, shadow uses dark-blending ink, toon pops a comic starburst, plasma spits hex rings and chips
New particle renderers: shards fly point-first, chips tumble, leaves flutter, stars spin, ink blends darkly
Ultimates
9 distinct handlers → 12. rush was running three characters and nova two.
12 unique charge stances — previously every ultimate used the same arms-back pose
12 unique charge routines — previously all identical converging orbs
Per-ultimate camera — Vanta charges at 88% darkness, Ronin at 44% but zoomed and near-frozen
Opponents
The dummy became one of five levels: Dummy, Rookie, Fighter, Veteran, Master
updPlayer generalized into updFighter(f, dt, input) — the AI runs the identical code you do, so it literally can't do anything you can't
Brain picks an action per reaction window: approach, retreat, guard, anti-air, dash-in, dash attack, projectile zoning, low pokes, jump-ins, specials; reacts to your swings, turtles below 28% HP
You now have HP. Hitstun, knockback, tumbling, wall-bounces, blocking (84% reduction, guard bubble), K.O. with slow-mo, banner, auto round reset, win tally
Opponent picker (random or any of the 12) and difficulty descriptions on the select screen
Camera
Was locked to the full arena; now tracks the midpoint and zooms on separation (~2.1× close, 1.05× full stage)
Zoom kick on heavy impacts; pulls back for ultimates; snaps to the loser on K.O.
Real parallax — skyline layers lag the camera at 55/37/19%
Bugs found and fixed
Ultimate banner overflowed the screen on long names
Screen flash decayed on slow-motion time, so it stayed white for seconds
Reika's stage type had no renderer and silently fell through to the wrong art
hl() would have mutated the shared POSE constants (caught before it shipped)
Down/up specials defaulted to the element tint instead of the character's color — Kage's orb came out white instead of gold
Tornado and Supernova left the player hovering after the ult
Key collision in the ultimate step scheduler when one handler used it twice
The dummy's st field collided with the new state string
Viewport reporting 0 during layout, and window resize mid-fight, never recovered — the frame loop now self-heals
Art
Redrew Aegis's shield. The concentric-disc-with-a-star version was reading as a real trademarked design; it's now an original heater shield with a chevron band.
