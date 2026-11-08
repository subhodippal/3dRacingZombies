# Dead Mile Racer

A 3D zombie street racer that runs in the browser. You drive a car with a plow on the front along an endless, curving 3-lane city road at night. Weave through traffic, launch off speed breakers, avoid potholes and run over zombies for points.

Built with [Three.js](https://threejs.org/) (r128, loaded from a CDN). The whole game is one `index.html` file, with no build step and no dependencies to install.

## Play

- **Online:** `https://<your-username>.github.io/<repo-name>/` once GitHub Pages is turned on (see below).
- **Locally:** open `index.html` in a browser. It needs an internet connection to load Three.js and the fonts.

## Controls

| Key | Action |
| --- | --- |
| `W` / `S` | Throttle / brake |
| `A` / `D` | Steer |
| `Space` | Jump |
| `Ctrl` or `N` | Nitrous boost |
| `Caps Lock` or `E` | Shift up |
| `Shift` or `Q` | Shift down |
| `G` | Switch between manual and automatic gearbox |
| `C` | Inside-car (cockpit) view |
| `V` | Cycle camera views (chase, low, high, side, cockpit) |
| Mouse drag / scroll | Look around / zoom |
| `P` or `Esc` | Pause |
| `M` | Mute |

On phones and tablets, on-screen buttons appear. The car accelerates and shifts gears by itself.

> If you hold `Ctrl` and then press `W`, the browser closes the tab, and a web page can't block that. Press `W` before `Ctrl`, or use `N` for nitrous.

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
