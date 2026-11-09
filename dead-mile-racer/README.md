# Dead Mile Racer

A 3D zombie street racer that runs in the browser. You drive a car with a plow on the front along an endless, curving city road at night. The road switches between 2 and 4 lanes (traffic merges where lanes end), runs through lit tunnels and under overbridges, and real street lights light it up. Weave through traffic, launch off speed breakers, avoid potholes and run over zombies for points.

Built with [Three.js](https://threejs.org/) (r128, loaded from a CDN). The whole game is one `index.html` file, with no build step and no dependencies to install.

## Play

- **Online:** `https://<your-username>.github.io/<repo-name>/` once GitHub Pages is turned on (see below).
- **Locally:** open `index.html` in a browser. It needs an internet connection to load Three.js and the fonts.

## Controls

The car always accelerates by itself. The **MENU** button (top left) or `Esc` opens the pause menu. The **camera** button (top right) changes the camera angle.

- **Manual:** each gear (R, N, 1–5) has a top speed. Shift up when the gear number flashes and shift down to slow down (engine braking). N rolls to a stop, and you can only select R once you've stopped.
- **Automatic:** gears change by themselves. Hold gear-down to brake, and keep holding at a stop to reverse. Let go to stop and pull away forward.

### Keyboard

These are the defaults. You can remap every action except pause in **Settings → Desktop**.

| Key | Action |
| --- | --- |
| `↑` | Gear up |
| `↓` | Gear down (automatic: hold to brake) |
| `←` / `→` | Steer left / right |
| `Space` | Jump |
| `Ctrl` | Special ability: Hellfire |
| `C` | Change camera angle |
| `Esc` | Pause menu and settings (fixed) |
| `G` / `M` | Switch transmission / mute (when not assigned to an action) |
| Right-drag / scroll | Look around / zoom |

With the mouse, holding the left or right half of the screen steers, and double-clicking jumps, the same as touch slide.

### Gamepad

These are the defaults. You can remap every action except pause in **Settings → Gamepad**, which shows a drawing of the pad with every button in use glowing and a line from each button to its action. Buttons light up as you press them. PlayStation pads show ✕ ○ □ △.

| Button | Action |
| --- | --- |
| `A` | Gear up (also starts the game) |
| `B` | Gear down (automatic: hold to brake) |
| D-pad ← / → | Steer left / right (the left stick always steers too) |
| `X` | Jump |
| `Y` | Special ability: Hellfire |
| `L1` | Change camera angle |
| `Start` | Pause menu (fixed) |

### Touch

Pick a control type in **Settings → Mobile**. The settings page shows a full phone-screen preview of each one.

| Type | Steer | Shift gear | Jump | Hellfire |
| --- | --- | --- | --- | --- |
| **Touch slide** | Hold the left / right side of the screen | Swipe up / down (automatic: swipe down and hold to brake) | Double tap, or JUMP | FIRE |
| **Steering** | Turn the on-screen wheel (bottom right); it springs back | Push / pull the GEAR lever (automatic: pull down and hold to brake) | JUMP (bottom left) | FIRE (bottom left) |
| **Gyro** | Tilt the phone like a wheel; touch steering is off | Swipe up / down | Double tap, or JUMP | FIRE |

Gyro steering is measured from how you hold the phone when the run starts. **Re-center tilt** in the settings resets it. On iPhone the browser asks for motion access the first time. If no motion sensor answers, the game falls back to holding the screen sides.

### Settings

Open them from the pause menu, or from **Settings** on the start screen. They're saved in the browser.

- **Top row:** sound on / off, transmission auto / manual, screen landscape / portrait. In *Landscape*, holding the phone upright shows a "turn your phone" screen. On Android, starting a run also goes fullscreen and locks the orientation you picked. iOS can't lock the orientation.
- **Desktop:** remap the keyboard. Choose **Change**, then press a key. If that key was already in use, the two actions swap.
- **Mobile:** control type (Gyro / Steering / Touch slide) with a preview, control size, steering sensitivity.
- **Gamepad:** remap the pad. Choose **Change**, then press a gamepad button (Start cancels). If that button was already in use, the two actions swap.

## Gameplay

- **Gearbox:** R, N, 1–5. Pull away in 1st and shift up when the gear number flashes. Stop before you select reverse.
- **Scoring:** distance, roadkill (chain kills for up to x10), overtakes, close calls and air time from speed breakers.
- **Hazards:** rear-ending traffic, scraping walls and potholes damage the car. Brutes (the big zombies) only go down if you hit them above about 85 km/h.
- **Road:** 2-lane and 4-lane stretches with tapers between them, tunnels and overbridges. Lanes are wider than before and potholes are rarer.
- **Hellfire (special ability):** every zombie you flatten charges it (6 kills, or 3 brutes). Set it off for a shockwave that blasts away nearby zombies and traffic, then the car burns for 7 seconds: it takes no damage and wrecks anything it touches.
- **Pickups:** amber wrench = hull repair.

Your best score is saved in the browser's local storage.

## Deploy to GitHub Pages

1. Create a new empty repository on GitHub, for example `dead-mile-racer`.
2. Push this folder:
   ```bash
   cd dead-mile-racer
   git init
   git add .
   git commit -m "Add Dead Mile Racer"
   git branch -M main
   git remote add origin https://github.com/<your-username>/dead-mile-racer.git
   git push -u origin main
   ```
3. On GitHub, open the repository's **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then click **Save**.
4. After a minute or two the game is live at `https://<your-username>.github.io/dead-mile-racer/`.

The empty `.nojekyll` file tells GitHub Pages to serve the files as they are, without running Jekyll.
