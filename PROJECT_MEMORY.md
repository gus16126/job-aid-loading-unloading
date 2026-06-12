# Project Memory: Job Aid - Loading and Unloading - 2 Car Hauler
*This document acts as a persistent memory and developer log. Any AI agent modifying this project must read, update, and respect the guidelines in this file.*

---

## 🎯 Project Context & Target User
- **User**: Gustavo Guallar (CarMax Transport Examiner / Driver)
- **Use Case**: A mobile-friendly guideline and reference application for safe vehicle loading/unloading on 2-car haulers.
- **Core Requirement**: The app **must run completely offline** with zero cell signal (e.g. at highway shoulders, weigh stations, or remote dealership lots).
- **Project Folder**: `C:\Users\trans\Downloads\Job Aid-Loading & Unloading`
- **Hosting URL**: `https://gus16126.github.io/job-aid-loading-unloading/`

---

## ⚙️ AI Coding Guidelines & Architectural Constraints

### 1. Framework Constraint (Keep it lightweight)
* Keep it as a single-page application (SPA) centered in `index.html` with vanilla Javascript, HTML5, and CSS3. Do not use external frontend frameworks (like React, Vue, or Tailwind) to keep load times near-zero.

### 2. Browser Compatibility (Must support Safari)
* The application must be fully tested and compatible with **iOS Safari**.
* Do not use proprietary Chrome APIs. Ensure the app works seamlessly in standalone fullscreen mode when added to the iOS home screen.

### 3. PWA & Service Worker Rules
* **Offline Caching**: Any new reference photos, scripts, or styles added to the project must be manually registered in the `ASSETS` array inside `sw.js` to ensure they are cached locally.
* **Auto-Update Cycle**: Whenever code is updated, increment the `CACHE_NAME` constant (e.g., `job-aid-cache-v1` to `v2`) in `sw.js`. This notifies client browsers to download the latest files.
* **Bypass Browser HTTP Cache**: Same-origin fetches must use `new Request(..., { cache: 'reload' })` to prevent iOS Safari from caching old files and blocking live updates.

---

## 💾 Data Schema & Local Storage Layout

### Checked Safety Rules (`jobAidSafetyChecked`)
Saves checked safety rule IDs dynamically to help drivers remember what they have read.
```json
{
  "1": true,
  "3": true
}
```

---

## 📜 Changelog & Completed Milestones
* **2026-06-11 (v1):**
  - Read guidelines from raw markdown file `Job Aid-Loading & Unloading.md`.
  - Created offline PWA assets: `index.html`, `sw.js`, `manifest.json`, and custom SVG icon (`icon.svg`).
  - Implemented 15 interactive safety mandates checklist with `localStorage` persistence.
  - Added navigation tabs for Safety, Equipment, Pre-Loading, Placement, and Specialty Vehicles.
  - Implemented instant client-side search with yellow match highlighting.
