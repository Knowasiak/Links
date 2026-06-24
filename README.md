# Premium Link-in-Bio Developer Profile

[![Live Site](https://img.shields.io/badge/Live-connect.adityagaurav.com-blue?style=for-the-badge&logo=cloudflare&logoColor=white&labelColor=0f172a&color=22d3ee)](https://connect.adityagaurav.com)
[![Stack](https://img.shields.io/badge/Stack-HTML5%20%7C%20CSS3%20%7C%20Vanilla%20JS-0f172a?style=for-the-badge&logo=javascript&logoColor=%23f7df1e)](https://connect.adityagaurav.com)
[![Performance](https://img.shields.io/badge/Performance-100%2F100-emerald?style=for-the-badge&logo=lighthouse&logoColor=white&labelColor=0f172a)](https://connect.adityagaurav.com)

A state-of-the-art, high-performance, and responsive personal link-in-bio hub designed for modern builders, founders, and creators. Featuring premium 3D animations, custom ambient lighting effects, search engine structured data, and a latency-compensated real-time location clock.

---

## 🌟 Key Technical Highlights

### 1. 🕒 Latency-Compensated Network Clock Sync
Traditional client-side clocks are vulnerable to local system clock drift. To resolve this:
- The page performs an asynchronous, lightweight HTTP `HEAD` request to its hosting server date headers.
- It calculates network round-trip latency (`(end - start) / 2`) and computes a precise time offset (`timeOffset = (serverTime + latency) - clientTime`).
- SFO time is updated at `1000ms` intervals using the calibrated server clock `new Date(Date.now() + timeOffset)`, ensuring absolute accuracy.

### 2. 🎭 Ambient-Reactive 3D Cascade Entrance
- **Hinge Unfolding**: Elements use `transform-origin: top center;` combined with a shared `perspective: 1200px` space on the page container, creating a realistic physical folding effect.
- **Spotlight Reactions**: Elements start tilted back at `-75deg`, set to low brightness (`brightness(0.2)`) and blurred. As they fold downward into the page, they catch the ambient illumination of the neon lamp spotlight, transitioning smoothly to full sharpness and brightness.
- **Staggered Orchestration**: Elements cascade sequentially from top to bottom, followed by automated brand-colored horizontal shimmer sweeps (`@keyframes initialShimmer`) precisely as they lock into position.

### 3. 🧠 Advanced SEO & AIO (AI Search Optimization)
Optimized for traditional search crawlers and AI LLM search models (SearchGPT, Google Gemini, Perplexity, etc.):
- **JSON-LD Structured Schema**: Embedded Schema.org `Person` markup detailing professional credentials, startup mentorship, IIT educational background, and linked social accounts.
- **LLM-specific Meta Fields**: Custom `ai-search-summary` and `ai-skills` tags designed to present structured summaries to LLM web agents directly, bypassing chunking errors.
- **Social Graph Optimization**: Complete OpenGraph and Twitter Card properties paired with an ultra-lightweight inline-encoded SVG Favicon.

### 4. 💎 Rich Interactive Aesthetics
- **Aceternity Lamp Glow**: A luminous neon spotlight header achieved using pure conic/linear gradients and blurring masks without static images.
- **Interactive Click Ripples**: Vanilla JS click-event listener that injects dynamic, localized radial ripples (`rippleAnim`) to provide mechanical feedback.
- **Phosphor Fill Palette**: Uniformly styled Phosphor Fill icons (`ph-fill`) rendering as semi-transparent white (`rgba(255,255,255,0.6)`) that transition to full opacity on hover.

---

## 🚀 Local Setup & Development

To view or work on the project locally:

1. Clone this repository:
   ```bash
   git clone https://github.com/Knowasiak/Links.git
   cd Links
   ```

2. Spin up a local static server to check the server date sync functionality:
   ```bash
   # Python 3
   python3 -m http.server 8000
   
   # Node.js
   npx serve .
   ```

3. Open [http://localhost:8000](http://localhost:8000) in your browser.

---

## ☁️ Deploying to Cloudflare Pages (Git Integrated)

Connecting this repository to Cloudflare Pages ensures your profile is globally distributed via Cloudflare's edge network and updates automatically on push:

1. Log in to the [Cloudflare Dashboard](https://dash.cloudflare.com/) and navigate to **Workers & Pages**.
2. Click **Create** -> **Pages** tab -> **Connect to Git**.
3. Choose **`Knowasiak/Links`** as your repository.
4. Set the following build settings:
   - **Production Branch**: `main`
   - **Framework Preset**: `None`
   - **Build Command**: *Leave blank*
   - **Build Output Directory**: *Leave blank (serves root)*
5. Click **Save and Deploy**.
