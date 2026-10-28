# Fut · RCL Football

Pick a legendary club squad and play the match yourself: real-time 3D 11v11 football with an FC Mobile–style broadcast camera and touch controls, against the CPU or a friend online.

## Play

Open `index.html` in a browser, or deploy the repo to Vercel (no build step, it is a static site).

### Controls

| Action | Touch | Keyboard |
| --- | --- | --- |
| Move | Drag anywhere on the left half of the screen | W A S D or arrows |
| Pass / Switch player | Pass | J |
| Shoot / Tackle | Shoot (hold longer for more power) | K or Space |
| Through ball / Teammate press | Through | L |
| Sprint | Sprint (hold) | Shift |
| Skill move / Slide tackle | Skill | I |

The buttons change with possession: with the ball they pass, shoot, play through balls and do skill moves; without it they switch player, tackle, send a teammate to press and slide tackle.

- Shots without sprint curl in as finesse shots; hold the stick toward a post to aim.
- Press pass or shoot while a pass is coming to you to play it first time.
- Cross from near the byline to set up headers.

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
