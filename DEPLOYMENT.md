# MADLOG Deployment Guide

This guide covers multiple options for deploying MADLOG online.

## Option 1: Vercel (Recommended - Easiest)

Vercel offers free hosting with automatic deployments from GitHub.

### Steps:

1. **Push to GitHub** (if not already done):
   ```bash
   cd Asset-Manager
   git add .
   git commit -m "Add deployment configs"
   git push origin main
   ```

2. **Deploy to Vercel**:
   - Go to [vercel.com](https://vercel.com)
   - Click "Add New Project"
   - Import your GitHub repository
   - Configure project:
     - Framework Preset: Other
     - Root Directory: `artifacts/madlog`
     - Build Command: `cd ../.. && pnpm install && cd artifacts/madlog && PORT=3000 BASE_PATH=/ pnpm build`
     - Output Directory: `dist/public`
   - Add Environment Variables:
     - `PORT` = `3000`
     - `BASE_PATH` = `/`
   - Click "Deploy"

3. **Your app will be live** at: `https://your-project.vercel.app`

### Quick Deploy Button:
You can also use Vercel CLI:
```bash
npm i -g vercel
cd Asset-Manager/artifacts/madlog
vercel
```

---

## Option 2: Netlify

Netlify also offers free hosting with continuous deployment.

### Steps:

1. **Push to GitHub** (if not already done)

2. **Deploy to Netlify**:
   - Go to [netlify.com](https://netlify.com)
   - Click "Add new site" → "Import an existing project"
   - Connect to GitHub and select your repository
   - Netlify will auto-detect the `netlify.toml` configuration
   - Click "Deploy site"

3. **Your app will be live** at: `https://your-site.netlify.app`

### Manual Deploy (Drag & Drop):
```bash
cd Asset-Manager
PORT=3000 BASE_PATH=/ pnpm --filter @workspace/madlog run build
```
Then drag the `artifacts/madlog/dist/public` folder to Netlify's deploy page.

---

## Option 3: GitHub Pages

Free hosting directly from your GitHub repository.

### Steps:

1. **Build the app**:
   ```bash
   cd Asset-Manager
   PORT=3000 BASE_PATH=/DUMBATHON-TEAM-VISION/ pnpm --filter @workspace/madlog run build
   ```

2. **Deploy to GitHub Pages**:
   ```bash
   cd artifacts/madlog/dist/public
   git init
   git add .
   git commit -m "Deploy MADLOG"
   git branch -M gh-pages
   git remote add origin https://github.com/Bhaskar0624/DUMBATHON-TEAM-VISION.git
   git push -f origin gh-pages
   ```

3. **Enable GitHub Pages**:
   - Go to your repo settings
   - Navigate to "Pages"
   - Source: Deploy from branch `gh-pages`
   - Save

4. **Your app will be live** at: `https://bhaskar0624.github.io/DUMBATHON-TEAM-VISION/`

---

## Option 4: Render

Free tier available with automatic deployments.

### Steps:

1. **Push to GitHub**

2. **Deploy to Render**:
   - Go to [render.com](https://render.com)
   - Click "New" → "Static Site"
   - Connect your GitHub repository
   - Configure:
     - Name: madlog
     - Root Directory: `artifacts/madlog`
     - Build Command: `cd ../.. && pnpm install && cd artifacts/madlog && PORT=3000 BASE_PATH=/ pnpm build`
     - Publish Directory: `dist/public`
   - Click "Create Static Site"

3. **Your app will be live** at: `https://madlog.onrender.com`

---

## Option 5: Cloudflare Pages

Fast global CDN with free tier.

### Steps:

1. **Push to GitHub**

2. **Deploy to Cloudflare Pages**:
   - Go to [pages.cloudflare.com](https://pages.cloudflare.com)
   - Click "Create a project"
   - Connect to GitHub
   - Configure:
     - Framework preset: None
     - Build command: `cd ../.. && pnpm install && cd artifacts/madlog && PORT=3000 BASE_PATH=/ pnpm build`
     - Build output directory: `artifacts/madlog/dist/public`
   - Environment variables:
     - `PORT` = `3000`
     - `BASE_PATH` = `/`
   - Click "Save and Deploy"

---

## Quick Comparison

| Platform | Free Tier | Custom Domain | Auto Deploy | Speed |
|----------|-----------|---------------|-------------|-------|
| Vercel | ✅ Yes | ✅ Yes | ✅ Yes | ⚡ Fast |
| Netlify | ✅ Yes | ✅ Yes | ✅ Yes | ⚡ Fast |
| GitHub Pages | ✅ Yes | ✅ Yes | ⚠️ Manual | 🐢 Slow |
| Render | ✅ Yes | ✅ Yes | ✅ Yes | 🚀 Medium |
| Cloudflare | ✅ Yes | ✅ Yes | ✅ Yes | ⚡⚡ Very Fast |

## Recommended: Vercel

For the easiest deployment experience, use Vercel:
1. It auto-detects the configuration
2. Provides instant previews for pull requests
3. Has excellent performance
4. Free SSL certificates
5. Custom domains supported

---

## Testing Your Deployment

After deployment, test these features:
1. Create a journal entry
2. Wait for Still Alive button (20 seconds)
3. Test action-blocking popups
4. Verify sounds play correctly
5. Check stage progression
6. Test on mobile devices

---

## Troubleshooting

### Build fails with "PORT not defined"
Make sure environment variables are set:
- `PORT=3000`
- `BASE_PATH=/`

### Assets not loading
Check that `BASE_PATH` matches your deployment path:
- Root domain: `BASE_PATH=/`
- Subdirectory: `BASE_PATH=/your-path/`

### Sounds not playing
Ensure your hosting platform serves audio files correctly. All platforms listed above support this.

---

**Need help?** Check the platform-specific documentation or open an issue on GitHub.
