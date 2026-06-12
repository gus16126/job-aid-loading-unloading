# Job Aid - Loading and Unloading - 2 Car Hauler

A mobile-friendly, offline-capable Progressive Web Application (PWA) designed to guide transport drivers through safe vehicle loading and unloading procedures for 2-car haulers (Cottrell models).

---

## 📱 Installation

Once hosted online (e.g. via GitHub Pages), you can install this app on your mobile device:
* **iOS (Safari)**: Tap the **Share** button, and select **"Add to Home Screen"**.
* **Android (Chrome)**: Tap the three dots menu, and select **"Install App"** or **"Add to Home Screen"**.

The application runs in standalone mode and functions **completely offline** (no cellular signal required).

---

## ✨ Features
* **Category Tab Navigation:** Easy tab-switching between Safety Rules, Equipment & Tools, Pre-Loading, Placement Planning, and Specialty Vehicles.
* **15 Non-Negotiable Safety Mandates:** Interactive checklist allowing drivers to review and cross off rules. Completed mandates are styled with a strike-through.
* **Instant Search & Filter:** A real-time search bar dynamically highlights matched text and hides irrelevant guidelines inside the active tab.
* **State Persistence:** Checklist ticks are saved automatically to `localStorage` and persist even if the browser is closed or refreshed.
* **Offline Caching:** Powered by a Service Worker (`sw.js`) with cache-bypassing updates (`cache: 'reload'`).
* **Visual Warning Indicators:** Important caution boxes highlight high-risk guidelines (such as the 6" clearance rule and non-runner mandates).

---

## 🛠️ Technical Details
* **Zero-Dependency Single-Page App (SPA):** Built purely in vanilla HTML5, CSS3, and JavaScript.
* **Fonts:** Uses premium typography (`Outfit` for headings, `Inter` for guidelines) loaded from Google Fonts.
* **Responsive Layout:** Tailored with CSS variables and flexbox structures for ideal layout on iOS Safari and Android Chrome screen sizes.
