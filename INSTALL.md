# FUEL — PWA Deployment Guide

## What's in this folder

```
fuel-pwa/
├── index.html       ← The app
├── manifest.json    ← Makes it installable
├── sw.js            ← Service worker (offline support)
├── icons/           ← App icons for all devices
│   ├── icon-72.png
│   ├── icon-96.png
│   ├── icon-128.png
│   ├── icon-144.png
│   ├── icon-152.png
│   ├── icon-192.png
│   ├── icon-384.png
│   └── icon-512.png
└── INSTALL.md       ← This file
```

---

## Option 1 — Deploy to Netlify (Recommended, free)

This gives you a public URL you can open on any device and install from.

### Steps:

1. Go to **https://netlify.com** and sign up for a free account (use GitHub, Google, or email).

2. Once logged in, find the box that says **"Deploy manually"** or drag-and-drop area.

3. **Drag the entire `fuel-pwa` folder** onto that area in your browser.

4. Netlify will give you a URL like `https://amazing-name-123.netlify.app` in about 10 seconds.

5. Open that URL on your phone — done! See "Installing on your phone" below.

> To use a custom name: in your Netlify dashboard go to Site Settings → Change site name.

---

## Option 2 — Deploy using Netlify CLI (terminal)

If you prefer the command line:

```bash
# Install Netlify CLI (one time)
npm install -g netlify-cli

# Deploy the folder
cd path/to/fuel-pwa
netlify deploy --prod --dir .
```

Follow the prompts — it will open a browser to log in, then deploy.

---

## Option 3 — Run locally with a simple server

PWAs require a server (not just opening index.html directly). The easiest way:

### Using Python (already installed on Mac/Linux):
```bash
cd path/to/fuel-pwa
python3 -m http.server 8080
```
Then open **http://localhost:8080** in your browser.

### Using Node.js:
```bash
npx serve fuel-pwa
```

> Note: Running locally only works on the same device. To install on your phone, use Netlify (Option 1).

---

## Installing on your phone

### iPhone (Safari only):
1. Open your Netlify URL in **Safari** (must be Safari, not Chrome)
2. Tap the **Share button** (box with arrow pointing up) at the bottom
3. Scroll down and tap **"Add to Home Screen"**
4. Tap **"Add"** — FUEL appears on your home screen like a native app

### Android (Chrome):
1. Open your Netlify URL in **Chrome**
2. Tap the **three-dot menu** (top right)
3. Tap **"Add to Home screen"** or **"Install app"**
4. Tap **"Install"** — FUEL appears in your app drawer

### Desktop (Chrome/Edge):
1. Open your Netlify URL
2. Look for the **install icon** (➕) in the address bar on the right
3. Click it and confirm — FUEL opens as a standalone window

---

## Updating the app

If you make changes to `index.html`:

1. Go back to your Netlify dashboard
2. Drag the updated `fuel-pwa` folder onto the deploy area again
3. Netlify redeploys in seconds — the app updates automatically on all devices

---

## Notes

- **Your data stays on your device** — all food logs are stored in the browser's localStorage, not on any server
- **Works offline** — once installed, the app shell loads without internet. The food search and barcode lookup require a connection
- **No account needed** — nothing to sign up for, no subscription

