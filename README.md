# Fut · Senpai Football

Pick a legendary club squad and play the match yourself: real-time 3D football with an FC Mobile–style broadcast camera and touch controls, against Senpai (the computer) or a friend online. Play 11 v 11, 5 v 5 or 3 v 3; small-sided games use a smaller pitch and goals and pick the best players from each squad.

## Play

Open `index.html` in a browser, or deploy the repo to Vercel (no build step, it is a static site).

### Lobby

The home screen is a lobby over the 3D stadium: your club lined up on the pitch with its star player doing keepy-ups, your club card and star player card, a quick match against Senpai (match type, level, half length, opponent), Online 1v1, Squad and Controls. Tap your name at the top to change it; your record against Senpai is kept on this device.

### Controls (FC Mobile scheme)

Every action button reads a swipe made while you hold it: tap for the basic action, or swipe before you let go. Hold a button for a moment in a match to see its swipes (you can turn the hints off from the pause menu).

| Button | Tap | Swipe ↑ | Swipe ↓ | Swipe ← | Swipe → |
| --- | --- | --- | --- | --- | --- |
| **Pass** | Ground pass to the teammate the stick points at | Lob (cross near the box) | Pass and go | Driven lob | Driven pass |
| **Through** | Through ball into the runner's path (clearance in your own third) | Lofted through | Trigger a run (no pass) | Dinked through | Driven through |
| **Shoot** (hold for power) | Shot | Chip | Finesse | Fake shot | Driven low shot |
| **Sprint & Skill** (hold to sprint) | Step over | Rainbow flick | Roulette | Drag back | Heel to heel |
| **2nd Def** (defending) | Hold: a teammate presses the carrier | | Keeper rush | | |

Defending: **Switch**, **Slide**, and **Sprint & Tackle** (hold to jockey and close down, tap to stand tackle).

Keyboard: WASD/arrows move · Pass J, U lob, Y pass and go, H driven lob, N driven · Through L, O lofted, R run / keeper rush, I dinked, M driven · Shoot K or Space, C chip, F finesse, G fake, B driven · Shift sprint, E step over / tackle, Q rainbow, Z roulette, X drag back, V heel to heel · Enter skip · P pause.

Players are built with human proportions (shaped torso, muscled limbs, jaw, hands and boots), drawn slightly under life size so pitches and goals read right, and smaller again on the 5 v 5 and 3 v 3 pitches.

Receivers hold their spot and come short to meet the ball instead of drifting away from it; runners making a run are played into their path. Passes, first touches, shots, skills, tackles, throw-ins, jockeying, shielding, keeper catches and goal celebrations all have their own animations, and each player has their own skin tone, hairstyle and facial hair.

The default layout matches FC Mobile: Sprint & Skill (green) in the bottom-right corner, Pass (blue) to its left, Through (yellow) above Pass and Shoot (red) above Sprint & Skill, with the joystick on the left. Buttons can be dragged to new positions and resized from the pause menu (Edit button layout).

### Tackling, skills and movement

- **Tackling is about angle and timing.** Step into the ball in front of or beside the carrier and you can nick it; your controlled player wins it most reliably. Tackles from behind rarely work and are often fouls (free kick, or a penalty in the box). Slide tackles through the back of a player are fouls.
- **Skill moves follow a set path:** the ball stays at the player's feet through step overs, roulettes and drag backs, and rainbow flicks and heel-to-heels knock it past the defender for you to run onto. Point the stick sideways to choose which way you go. Defenders close by can be wrong-footed; low-DRI players can take a heavy touch.
- **Players carry momentum.** They lean and bank into turns, plant before changing direction, side-step and backpedal while watching the ball, walk when the shape is set, and sprint only when it matters. Attackers make their own runs (in behind, coming short, full-backs overlapping), and through balls lead them.

### Shooting and goalkeeping

- **Placement:** point the stick to one side of the goal to place the shot there. Running straight at goal (or no stick) uses shot assist, which picks the near or far post, whichever line stays furthest from the keeper. Shots never default to the middle.
- **Accuracy and height** depend on SHO, distance, the angle, too much power, pressure and shooting on the run. Finesse shots are solved so the curl brings them back inside the far post; driven shots stay low; harder shots rise.
- **Keepers save what they can physically reach:** they react after a moment (REF), dive sideways at a speed set by DIV, and have an arm's reach. Low and high corners at full stretch are the hardest to reach, a curling shot is read late, and slow lobs give them time to get back. Keepers stand on the line that splits the angle between the ball and the posts, and come off their line to narrow the angle in one-on-ones.

### Match presentation and Skip

Matches open with the teams lined up side by side and the line-ups on screen, then a fly-in to kick-off. At half-time the players walk off with the score and stats on screen, then the second half opens with its own fly-in. Full-time shows the winners celebrating around the man of the match (losers with hands on heads, a draw applauded) before the result screen. Against Senpai, every goal is followed by the celebration and a slow-motion replay. **Skip** (or Enter) skips each of these; online, each player can skip their own sequences.

### Player ratings

Outfield players have PAC, SHO, PAS, DRI, DEF and PHY; keepers have DIV, HAN, KIC, REF, SPD and POS. They drive the gameplay: pace sets top speed and acceleration, shooting sets power and accuracy, passing sets accuracy, dribbling sets close control, turning, first touch and skill-move success, defending sets tackle and interception success, and physical sets strength in duels, headers and stamina.

### Online 1v1

1. Both players open the site and pick a club.
2. One player taps **Online → Create room**, then **Copy invite link** (or sends the 5-character code).
3. The friend opens the link (it joins the room automatically) or taps **Join with a code**. The host taps **Kick off**.

Two connections run side by side, and either one is enough:

- a **direct link** between the two devices through [PeerJS](https://peerjs.com/) (WebRTC), which has the least delay and keeps retrying until it connects;
- a **relay** through free public MQTT brokers (`broker.emqx.io`, `broker.hivemq.com`) for networks that block direct links. It also keeps the room alive if a phone briefly goes to the background, for example while sharing the code.

The room screen shows which one is in use. The host runs the match, so the host should keep the game open on screen. Game state and nicknames pass through the public relay when it's in use, so don't put anything private in your nickname.

## Deploy to Vercel

1. On vercel.com, choose **Add New → Project** and import this repo.
2. Leave the framework preset as **Other** and the build settings empty.
3. Deploy. Every push to `main` redeploys automatically.

## Files

- `index.html` – the whole game: menus, match engine, 3D renderer, controls and online rooms.
- `vendor/three.min.js` – three.js r149 (MIT license) for the 3D graphics.
