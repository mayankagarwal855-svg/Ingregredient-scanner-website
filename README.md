# 🥗 CleanLabel — Ingredient Scanner

A fully offline ingredient scanner website. No API key, no accounts, no costs — ever.

## Features
- ⚡ Instant offline analysis against 600+ ingredient database
- 📷 Photo scan (reads label image)
- 🔢 Barcode lookup via Open Food Facts (free, no key)
- ✏️ Type/paste ingredients for fully offline analysis
- 💾 Save healthy products with filter by verdict
- 📲 Installable on iPhone via Safari → Add to Home Screen
- 🌐 Works on any device — desktop, tablet, mobile

## Setup — GitHub Pages (free hosting)

### 1. Create GitHub repository
- Go to [github.com](https://github.com) and create a new repo named `cleanlabel`
- Upload both files: `index.html` and `db.js`

### 2. Enable GitHub Pages
- Go to repo → **Settings → Pages**
- Source: **Deploy from a branch** → `main` → `/ (root)` → Save
- Your site will be live at: `https://yourusername.github.io/cleanlabel`

### 3. Add to iPhone home screen
- Open the URL in **Safari** on iPhone
- Tap the **Share** button (↑)
- Tap **Add to Home Screen**
- Done! 🎉

## Files
- `index.html` — Main app (UI + analysis engine)
- `db.js` — Ingredient database (600+ entries)

## How it works

### Offline analysis (Type/paste)
Ingredients are parsed from the text, each token looked up in `db.js`, and a verdict computed instantly — zero internet required.

### Barcode lookup
Uses the free [Open Food Facts API](https://world.openfoodfacts.org/) to find the product's ingredient list, then analyses it offline.

### Photo analysis
Currently shows a prompt to type the ingredients instead (photo analysis requires AI/API).

## Adding to the database
Open `db.js` and add entries to `INGREDIENT_DB`:
```js
"your-key": { name: "Display Name", status: "ok"|"warn"|"bad", detail: "Safety explanation." },
```
Or add aliases in `INGREDIENT_ALIASES`:
```js
"common name": "db-key",
```
