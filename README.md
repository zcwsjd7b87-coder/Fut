# Fut · RCL Football

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

Receivers hold their spot and come short to meet the ball instead of drifting away from it; runners making a run are played into their path. Passes, first touches, shots, skills, tackles, throw-ins, jockeying, shielding, keeper catches and goal celebrations all have their own animations, and each player has their own skin tone, hairstyle and facial hair.

The default layout matches FC Mobile: Sprint & Skill (green) in the bottom-right corner, Pass (blue) to its left, Through (yellow) above Pass and Shoot (red) above Sprint & Skill, with the joystick on the left. Buttons can be dragged to new positions and resized from the pause menu (Edit button layout).

### Intro, replays and Skip

Matches open with a stadium fly-in and line-up banner. Against Senpai, every goal is followed by the celebration and a slow-motion replay. **Skip** (or Enter) skips the intro, celebrations, replays and half-time; online, the host can skip celebrations and half-time.

### Player ratings

Outfield players have PAC, SHO, PAS, DRI, DEF and PHY; keepers have DIV, HAN, KIC, REF, SPD and POS. They drive the gameplay: pace sets top speed and acceleration, shooting sets power and accuracy, passing sets accuracy, dribbling sets close control, turning, first touch and skill-move success, defending sets tackle and interception success, and physical sets strength in duels, headers and stamina.

### Online 1v1

1. Both players open the site and pick a club.
2. One player taps **Create room** and sends the 5-character code.
3. The other taps **Join with a code** and enters it. The host taps **Kick off**.

Online play connects the two devices directly through [PeerJS](https://peerjs.com/) (free public signalling server, no account needed). The host runs the match, so the host should keep the game open on screen. Some strict networks (certain mobile carriers or school/office Wi-Fi) block direct connections; if joining hangs, try another network.

## Deploy to Vercel

1. On vercel.com, choose **Add New → Project** and import this repo.
2. Leave the framework preset as **Other** and the build settings empty.
3. Deploy. Every push to `main` redeploys automatically.

## Files

- `index.html` – the whole game: menus, match engine, 3D renderer, controls and online rooms.
- `vendor/three.min.js` – three.js r149 (MIT license) for the 3D graphics.
