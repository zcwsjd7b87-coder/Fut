# Fut · RCL Football

Pick a legendary club squad and play the match yourself: real-time 3D football with an FC Mobile–style broadcast camera and touch controls, against Senpai (the computer) or a friend online. Play 11 v 11, 5 v 5 or 3 v 3; small-sided games use a smaller pitch and goals and pick the best players from each squad.

## Play

Open `index.html` in a browser, or deploy the repo to Vercel (no build step, it is a static site).

### Controls (FC Mobile scheme)

| Button | Tap / hold | Swipe while holding |
| --- | --- | --- |
| **Pass** | Ground pass to the teammate the stick points at | Up: lob or cross · Down: pass and go · Right: driven pass |
| **Through** | Through ball into the runner's path (clearance in your own third) | Up: lofted through ball |
| **Shoot** | Hold for power, release to shoot | Down: finesse · Up: chip · Left: fake shot |
| **Sprint & Skill** | Hold to sprint, tap for a skill move | Any direction: forward knock-on, drag back, or sidestep feint |
| **Switch** (defending) | Switch to the player nearest the ball | |
| **Slide** (defending) | Slide tackle | |
| **2nd Def** (defending) | Hold: a teammate presses the ball carrier | Down: keeper rush |
| **Sprint & Tackle** (defending) | Hold to close the carrier down, tap to stand tackle | |

Keyboard: WASD/arrows move · J pass, U lob, Y pass and go · L through, O lofted through · K shoot, F finesse, C chip, G fake · Shift sprint, E skill / tackle · R keeper rush · P pause.

The default layout matches FC Mobile: Sprint & Skill (green) in the bottom-right corner, Pass (blue) to its left, Through (yellow) above Pass and Shoot (red) above Sprint & Skill, with the joystick on the left. Buttons can be dragged to new positions and resized from the pause menu (Edit button layout).

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
