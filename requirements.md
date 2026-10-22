# System & Project Requirements
**Project:** VeriPulse OSINT - Username Authenticity & Fake Account Auditor

VeriPulse OSINT is built as a zero-dependency, client-side web application. It does not require a backend server, database, or package manager (like npm or pip) to run locally.

## 1. System Requirements
* **Operating System:** Cross-platform (Windows, macOS, Linux, iOS, Android).
* **Hardware:** Any device capable of running a modern web browser.
* **Network:** Active internet connection is required to fetch CDNs (Tailwind, Fonts, Icons) and query live CORS APIs (GitHub, Reddit).

## 2. Software & Environment Requirements
* **Web Browser:** A modern, up-to-date web browser that supports ES6 JavaScript, HTML5 Canvas, and modern CSS properties (e.g., Grid, Flexbox, Backdrop-filter). 
  * Recommended: Google Chrome (v90+), Mozilla Firefox (v88+), Microsoft Edge (v90+), or Apple Safari (v14+).
* **Local Server (Optional but Recommended):** While you can open the `index.html` file directly via the `file://` protocol, running it through a simple local server prevents potential local CORS policy restrictions.
  * Examples: VS Code Live Server, `python -m http.server`, or `npx serve`.

## 3. External Dependencies (Loaded via CDN)
The application automatically fetches the following libraries at runtime. No installation is required.

* **Tailwind CSS:** (v3.x) Loaded via CDN (`https://cdn.tailwindcss.com`) for rapid utility-class styling and responsive design.
* **Phosphor Icons:** Loaded via CDN (`https://unpkg.com/@phosphor-icons/web`) for UI iconography.
* **Google Fonts:** Loads `Inter` (sans-serif) and `JetBrains Mono` (monospace) from `fonts.googleapis.com`.

## 4. API Endpoints Used (No API Keys Required)
* **GitHub REST API:** `https://api.github.com/users/{username}` (Public unauthenticated endpoint).
* **Reddit API:** `https://www.reddit.com/user/{username}/about.json` (Public unauthenticated JSON endpoint).

## 5. Deployment Requirements
To deploy VeriPulse OSINT to the web, simply host the `index.html` file on any static hosting provider:
* GitHub Pages
* Vercel
* Netlify
* Cloudflare Pages
* Any standard Apache/Nginx web server.