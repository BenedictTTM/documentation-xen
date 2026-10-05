# XenChat Documentation Portal 💬📚

Official interactive documentation site for the **XenChat** platform — a real-time messaging, WebRTC calling, and ephemeral status-sharing web application built with ASP.NET Core 8, SignalR, PostgreSQL, and Cloudinary.

---

## 📁 Folder Contents

This directory is an entirely self-contained static site with zero external build requirements:

| File | Purpose |
| :--- | :--- |
| **`index.html`** | Complete interactive documentation single-page app (hero, architecture, API tables, SignalR reference, syntax highlighting, search, interactive copy) |
| **`404.html`** | Custom themed 404 error page matching dark-glass aesthetic |
| **`favicon.ico`** | Project favicon |
| **`assets/`** | Static assets (e.g. `logo.png`) |
| **`robots.txt`** & **`sitemap.xml`** | SEO crawler configurations |
| **`vercel.json`** | Vercel deployment config (clean URLs, security headers, caching) |
| **`netlify.toml`** | Netlify deployment config |
| **`_headers`** & **`_redirects`** | Cloudflare Pages / Netlify security headers and fallback redirects |
| **`.nojekyll`** | GitHub Pages flag to disable Jekyll processor |
| **`Dockerfile`** & **`nginx.conf`** | Production-ready Alpine Nginx container setup with gzip and security headers |
| **`package.json`** | Optional local preview runner |

---

## 🚀 Deployment Options

### 1. GitHub Pages (Free & Instant)

#### Option A: Deploy from branch/folder
1. Push this repository to GitHub.
2. Go to **Settings** &rarr; **Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose your branch (e.g. `main`) and select the `/documentation` folder from the dropdown.
5. Click **Save**. Your documentation site will be live at `https://<username>.github.io/<repo>/`.

#### Option B: Dedicated `gh-pages` branch
```bash
git subtree push --prefix documentation origin gh-pages
```

---

### 2. Vercel (1-Click)

Using the Vercel CLI:
```bash
cd documentation
npx vercel
# Follow the interactive prompts, accept defaults.
# For production:
npx vercel --prod
```

Or via the [Vercel Dashboard](https://vercel.com/):
- **Import Git Repository** &rarr; Set **Root Directory** to `documentation`.
- Framework preset: **Other** / **Static Site**.
- Click **Deploy**.

---

### 3. Netlify

Using the Netlify CLI:
```bash
cd documentation
npx netlify deploy
# For production:
npx netlify deploy --prod --dir .
```

Or drag-and-drop:
- Go to [Netlify Drop](https://app.netlify.com/drop) and drag the entire `documentation` folder into the browser window.

---

### 4. Cloudflare Pages

1. Log into your **Cloudflare Dashboard** &rarr; **Workers & Pages** &rarr; **Create application** &rarr; **Pages**.
2. Connect your Git repository.
3. Configure build settings:
   - **Framework preset**: None
   - **Build output directory**: `documentation`
4. Click **Save and Deploy**.

---

### 5. Docker Container (Self-Hosted / VPS)

To build and run the high-performance Alpine Nginx container:

```bash
# Build the Docker image
docker build -t xenchat-docs ./documentation

# Run on port 8080 (or any port of your choice)
docker run -d -p 8080:80 --name xenchat-docs xenchat-docs
```

Visit `http://localhost:8080` to view the site.

---

### 6. Local Preview

You can test the site locally using any static web server:

```bash
cd documentation

# Option A: Node.js serve
npx serve .

# Option B: Python 3
python -m http.server 3000

# Option C: Direct Browser
# Double-click index.html or open it directly in Chrome/Edge/Firefox
```
