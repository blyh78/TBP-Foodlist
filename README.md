# Food Plaza — Tiong Bahru Plaza Food Directory

A single-page, self-contained food directory for Tiong Bahru Plaza. Search by name or cuisine, filter to halal-only stalls, and reserve or view menus directly from each stall card.

This is a **static site** — just one `index.html` file with no build step, no dependencies, and no server-side code. It's ready to deploy as-is.

## Deploy to Vercel via GitHub

### 1. Push this folder to a new GitHub repo

```bash
# unzip this file first, then inside the folder:
git init
git add .
git commit -m "Initial commit: Food Plaza directory"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/food-plaza.git
git push -u origin main
```

(Create the empty repo on GitHub first at github.com/new — don't initialize it with a README, so the push above doesn't conflict.)

### 2. Import into Vercel

1. Go to [vercel.com/new](https://vercel.com/new)
2. Click **"Import Git Repository"** and select the `food-plaza` repo you just pushed
3. Vercel will auto-detect it as a static site — no framework preset, no build command, no output directory needed
4. Click **Deploy**

That's it — Vercel will give you a live URL (e.g. `food-plaza.vercel.app`) within about 30 seconds.

### 3. Future updates

Any time you edit `index.html` and push to the `main` branch on GitHub, Vercel automatically redeploys.

```bash
git add .
git commit -m "Update stall list"
git push
```

## Files

- `index.html` — the full app (HTML/CSS/JS, no external dependencies)
- `vercel.json` — minimal Vercel config (clean URLs, no trailing slash)
- `README.md` — this file

## Editing the stall data

Stall data lives in the `stalls` array near the top of the `<script>` block in `index.html`. Each entry looks like:

```js
{ name: "Stall Name", unit: "#02-137", cuisine: "Indonesian", halal: true, phone: "+6512345678", reservation: false, website: "https://example.com" }
```

- `phone`: use `null` if unknown — the reserve button won't show a clickable number
- `website`: use `null` if the stall has no site/socials — the Menu button won't render
- `reservation`: `true` shows a "Reserve" button with the stall's unit number
