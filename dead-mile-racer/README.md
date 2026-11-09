# Dead Mile Racer

A 3D zombie street racer that runs in the browser. You drive a car with a plow on the front along an endless, curving 3-lane city road at night. Weave through traffic, launch off speed breakers, avoid potholes and run over zombies for points.

Built with [Three.js](https://threejs.org/) (r128, loaded from a CDN). The whole game is one `index.html` file, with no build step and no dependencies to install.

## Play

- **Online:** `https://<your-username>.github.io/<repo-name>/` once GitHub Pages is turned on (see below).
- **Locally:** open `index.html` in a browser. It needs an internet connection to load Three.js and the fonts.

## Controls

The car always accelerates by itself. The **MENU** button (top left) or `Esc` opens the pause menu. The **camera** button (top right) changes the camera angle.

- **Manual:** each gear (R, N, 1–5) has a top speed. Shift up when the gear number flashes and shift down to slow down (engine braking). N rolls to a stop, and you can only select R once you've stopped.
- **Automatic:** gears change by themselves. Hold gear-down to brake, and keep holding at a stop to reverse. Let go to stop and pull away forward.

### Keyboard

| Key | Action |
| --- | --- |
| `W` / `↑` | Gear up |
| `S` / `↓` | Gear down (automatic: hold to brake) |
| `A` / `←`, `D` / `→` | Steer left / right |
| `Space` | Jump |
| `Ctrl` (or `N`) | Special ability: nitrous boost |
| `Esc` | Pause menu and settings |
| `G` / `M` | Switch transmission / mute |
| `C` / `V` | Inside-car view / cycle camera views |
| Mouse drag / scroll | Look around / zoom |

> If you hold `Ctrl` and then press `W`, the browser closes the tab, and a web page can't block that. Press `W` before `Ctrl`, or use `N` for nitrous.

### Gamepad

These are the defaults. You can remap every action except steering in **Settings → Gamepad**.

| Button | Action |
| --- | --- |
| Left stick / D-pad ← → | Steer (fixed) |
| `A` | Gear up (also starts the game) |
| `B` | Gear down (automatic: hold to brake) |
| `Y` | Jump |
| `X` | Special ability: nitrous boost |
| D-pad ↑ | Change camera angle |
| `Start` | Pause menu |

### Touch

| Control | Action |
| --- | --- |
| Slide pad ◀ ▶ | Put your thumb on a pad and slide and hold to steer. The further you slide, the sharper the turn |
| Slide pad ▲ ▼ | Gear up / gear down, one gear per slide (automatic: slide down and hold to brake) |
| JUMP (bottom corner) | Jump |
| SPECIAL (other bottom corner) | Nitrous boost |

Portrait shows one slide pad above the buttons. Landscape shows two pads, one for each thumb.

### Settings

Open them from the pause menu, or from **Settings** on the start screen. They're saved in the browser.

- **General:** transmission (automatic / manual), sound.
- **Touch screen:** orientation (landscape only / portrait + landscape), one or two pads in landscape, which side JUMP and SPECIAL go on, control size, steering sensitivity. In *Landscape only* mode, holding the phone upright shows a "turn your phone" screen. On Android, starting a run also goes fullscreen and locks landscape. iOS can't lock the orientation.
- **Gamepad:** remap gear up, gear down, jump, special ability, camera and pause. Choose **Change**, then press a button. If that button was already in use, the two actions swap.

## Gameplay

- **Gearbox:** R, N, 1–5. Pull away in 1st and shift up when the gear number flashes. Stop before you select reverse.
- **Scoring:** distance, roadkill (chain kills for up to x10), overtakes, close calls and air time from speed breakers.
- **Hazards:** rear-ending traffic, scraping walls and potholes damage the car. Brutes (the big zombies) only go down if you hit them above about 85 km/h.
- **Pickups:** amber wrench = hull repair, blue canister = nitrous.

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
