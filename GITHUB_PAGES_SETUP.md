# GitHub Pages Setup Guide

## Initial Setup (One-time only)

1. **Go to your repository settings on GitHub:**
   - Navigate to https://github.com/kitpaddle/pluppen
   - Click "Settings" (top right)
   - Scroll to "Pages" in the left sidebar

2. **Configure Pages:**
   - Under "Source", select "Deploy from a branch"
   - Select branch: `gh-pages`
   - Select folder: `/ (root)`
   - Click "Save"

3. **First time only:**
   ```powershell
   npm run deploy
   ```
   This will create the gh-pages branch and push your built site.

## After Initial Setup

Every time you want to update your live site, just run:
```powershell
npm run deploy
```

This will:
1. Build your Vue app
2. Push it to the `gh-pages` branch
3. GitHub will automatically deploy it

Your site will be live at: https://kitpaddle.github.io/pluppen/

## Local Development

To work on changes locally:
```powershell
npm run dev
```

Then open http://localhost:5173 in your browser. Changes will auto-reload!

## How It Works

- `npm run dev` - Starts the local dev server
- `npm run build` - Builds the app to `dist/` folder
- `npm run deploy` - Builds and pushes to GitHub Pages

The `vite.config.js` already has `base: '/pluppen/'` set, which is correct for a project repository (not a user/organization site).
