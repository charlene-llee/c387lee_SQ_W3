# Week 3 Example 2: Full Fighting Game

## What This Example Demonstrates

This example builds on Example 1 by adding health, attacking, hit detection, sound, and game states to create a complete two-player fighting game.

- **Game states** — the game is always in one of three states (`STATE_START`, `STATE_FIGHT`, `STATE_WIN`); each state controls what gets drawn and what responds to input; stored as constants to prevent typos
- **`preload()`** — loads all sounds before the sketch starts so they are ready to play immediately; sound files are loaded into an array for variety
- **Sound array** — `punchSounds` holds all 9 punch sounds; `floor(random(...))` picks a random index each time a punch lands so hits sound different
- **Health system** — each fighter has a `health` property that decreases when hit; `maxHealth` is stored separately so health bars can be drawn proportionally using `map()`
- **`startAttack()`** — called from `keyPressed()` so the punch fires once per press; sets the direction of the fist based on the opponent's position
- **`getPunchX()`** — a method that returns the fist's x position; used in `checkHits()` to test whether the punch connects with the opponent
- **`takeHit()`** — called on the fighter being hit; blocked punches deal no damage; health reaching zero triggers `endGame()`
- **Hit flash** — `hitFlash` counts down from 12 each time a fighter is hit; while it is above zero, the blob draws white instead of its normal colour
- **`hitLanded` flag** — prevents the same attack swing from registering more than one hit per punch
- **`keyPressed()` vs `keyIsDown()`** — `keyPressed()` fires once per press and is used for attacks and menu navigation; `keyIsDown()` fires every frame and is used for movement and blocking
- **Health bars with `map()`** — `map()` converts health (0 to maxHealth) to a bar width in pixels (0 to barW); the bar shrinks as health decreases
- **Start and win screens** — drawn using text and shapes in their respective game states; a semi-transparent overlay is used on the win screen

## Setup and Interaction Instructions

To run the sketch locally, open `index.html` in Google Chrome using Live Server.

Sound files must be present in `assets/sounds/` before running:

- `punch_1.wav` through `punch_9.wav`
- `win.wav`
- `background.mp3`

**Player 1 Controls:**

- Move: A / D
- Attack: F
- Block: G

**Player 2 Controls:**

- Move: Arrow Keys
- Attack: K
- Block: L

Press **ENTER** to start or rematch.

**Opening the Chrome Console**

- **Windows:** Press `F12` or `Ctrl + Shift + J`, then click the **Console** tab
- **Mac:** Press `Cmd + Option + J`

The console will show any errors in your sketch.

## Assets

| File | Source |
| `assets/images/startBG.png` | By mintor94 [1] |
| `assets/images/playBG.png` | By mintor94 [1] |
| `assets/images/winBG.png` | By mintor94 [1] |
| `assets/sounds/hitSOUND1.mp3` | By SoundReality [2] |
| `assets/sounds/hitSOUND2.mp3` | By Universfield [3] |
| `assets/sounds/startMUSIC.mp3` | By Mohamed_hassan [4] |
| `assets/sounds/playMUSIC.mp3` | By u_98a917e4i7 [5] |
| `assets/sounds/winMUSIC.mp3` | By DRAGON-STUDIO [6] |
| `assets/fonts/Robot Crush.otf` | By Darrell Flood [7] |

## References

[1] mintor94. n.d. High quality Portal 2 wall textures. GameBanana. https://gamebanana.com/mods/383184

[2] SoundReality. n.d. Hit Windy Thud. Pixabay. https://pixabay.com/sound-effects/film-special-effects-hit-windy-thud-399086/

[3] Universfield. n.d. Cinematic Impact Hit. Pixabay. https://pixabay.com/sound-effects/film-special-effects-cinematic-impact-hit-352702/

[4] Mohamed_hassan. n.d. Mysterious mission 1. Pixabay. https://pixabay.com/sound-effects/musical-mysterious-mission-1-481049/

[5] u_98a917e4i7. n.d. Boss Fight Ahh Music. Pixabay. https://pixabay.com/sound-effects/musical-boss-fight-ahh-music-490611/

[6] DRAGON-STUDIO. n.d. Correct. Pixabay. https://pixabay.com/sound-effects/technology-correct-472358/

[7] Darrell Flood (Hawtpixel). n.d. Robot Crush. DaFont. https://www.dafont.com/robot-crush.font
