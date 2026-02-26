# Prague Explorer — iPhone PWA

A GPS-based urban exploration app for Prague. Walk around the city and "color in" every building you visit.

## Quick Deploy to iPhone (via GitHub Pages)

### Step 1: Create a GitHub Repository
1. Go to [github.com](https://github.com) and sign in (or create a free account)
2. Click **"New repository"** (the green button or the `+` icon)
3. Name it `prague-explorer`
4. Set it to **Public**
5. Click **"Create repository"**

### Step 2: Upload Files
1. On the new repo page, click **"uploading an existing file"**
2. Drag ALL files from this folder into the upload area:
   - `index.html`
   - `sw.js`
   - `manifest.json`
   - `apple-touch-icon.png`
   - `icon-192.png`
   - `icon-512.png`
3. Click **"Commit changes"**

### Step 3: Enable GitHub Pages
1. Go to repo **Settings** → **Pages** (in the left sidebar)
2. Under **Source**, select **"Deploy from a branch"**
3. Branch: `main`, Folder: `/ (root)`
4. Click **Save**
5. Wait 1-2 minutes. Your URL will be:
   `https://YOUR_USERNAME.github.io/prague-explorer/`

### Step 4: Install on iPhone
1. Open **Safari** on your iPhone
2. Go to your GitHub Pages URL
3. Tap the **Share** button (square with arrow)
4. Scroll down and tap **"Add to Home Screen"**
5. Tap **"Add"**
6. The app icon appears on your home screen!

### Step 5: Load Building Data
1. Open the app from your home screen
2. Upload your Prague building shapefile (.zip) or GeoJSON
3. Buildings load and are cached — you only do this once
4. Walk around Prague and explore!

## Features
- **GPS tracking** — automatically discovers buildings as you walk within 30m
- **Offline support** — map tiles and data cached for offline use
- **112 Prague districts** — real cadastral boundaries with per-district completion tracking
- **Wake Lock** — screen stays on while exploring
- **Haptic feedback** — vibrates when you discover a building

## Troubleshooting

**GPS not working?**
- Make sure Location Services is ON (Settings → Privacy → Location Services)
- Allow location for Safari/the PWA
- GPS requires HTTPS — GitHub Pages provides this automatically

**Map tiles not loading?**
- First load requires internet to cache tiles
- Walk around with internet first to pre-cache your area
- Tiles cache automatically for offline use

**App feels slow on first load?**
- Large shapefiles (100k+ buildings) take a moment to parse
- Once cached in IndexedDB, subsequent loads are instant

**"Add to Home Screen" missing?**
- Must use Safari (not Chrome/Firefox on iOS)
- The option is in the Share menu, scroll down if you don't see it

## File Structure
```
prague-explorer/
├── index.html          ← Main app (all-in-one HTML)
├── sw.js               ← Service worker (offline caching)
├── manifest.json       ← PWA manifest
├── apple-touch-icon.png ← iOS home screen icon (180×180)
├── icon-192.png        ← Android icon (192×192)
└── icon-512.png        ← Splash/large icon (512×512)
```
