# multiversefighters

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
