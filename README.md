# Digital Wedding Invitation (Shaadi Card)

A luxury, interactive digital Indian wedding card web application inspired by traditional royal aesthetics and Gond folk art.

This repository is a faithful replication of [kunika-navneet-wedding-card.vercel.app](https://kunika-navneet-wedding-card.vercel.app/).

---

## ✨ Features

- **🚪 Royal Gate Opening Ceremony**: Interactive royal palace doors with gold latches that part open on tap/click with smooth entrance choreography.
- **🎨 Gond Art & Traditional Motifs**: 100% procedural vector SVG artwork including:
  - Sacred Tree of Life with Peacocks and Lovebirds
  - Gond Rosettes, Floral Halos, and Jharokha Arches
  - Traditional Mango-Leaf & Marigold Toran
  - Sacred Mangal Kalash
- **🌸 Ambient Falling Petals**: Floating golden marigold petals drifting down the invitation.
- **⏳ Live Countdown Timer**: Animated Gond sun-dial counting down days, hours, minutes, and seconds in real-time.
- **📅 Interactive Itinerary**:
  - Filterable by day (Day One / Day Two)
  - Bilingual descriptions (English & Hindi)
  - Color-coded ceremony badges (Haldi, Ring Ceremony & Sangeet, Phere, Baraat & Reception)
  - Dress code recommendations
- **🗓️ 1-Click "Add to Calendar"**: Generates a standard `.ics` iCalendar file on the fly with all wedding events.
- **📍 Venue & Navigation**: Embedded venue card with one-tap Google Maps directions.
- **💌 Shareable**: Integrated with the Web Share API (native mobile share sheet) and a copy-to-clipboard fallback with toast notifications.
- **⚡ Zero Build Dependencies**: Built with pure HTML5, CSS3, and Vanilla JavaScript with Framer Motion (Motion library) loaded via CDN. No compilation or node_modules required.

---

## 🚀 Quick Start (Run Locally)

You can run this project locally without installing Node.js or any package managers.

### Option 1: Open Directly in Browser
Simply double-click [`index.html`](index.html) or right-click and choose **Open with > Chrome / Edge / Firefox / Safari**.

### Option 2: Using Python's Local Server
Run in your terminal from this folder:

```bash
python -m http.server 3000
```

Then open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🛠️ Customization Guide

You can easily adapt this wedding card for any couple (e.g. **Mridul & Anjali**).

### 1. Update the `CONFIG` Object in `index.html`
Open [`index.html`](index.html) and find the `CONFIG` block around line 697:

```javascript
const CONFIG = {
  // Commissioned portrait illustrations (drop PNGs in folder and put filenames here)
  portraits: { groom: '', bride: '' },

  // Venue details
  venue: {
    name: 'Your Wedding Venue Name',
    address: 'City, State, Country',
    mapUrl: 'https://maps.app.goo.gl/...'
  },

  // Countdown target date (ISO format with IST offset)
  countdownTo: '2026-12-02T12:00:00+05:30',

  // Days and events
  days: [
    {
      iso: '20261202',
      num: '02',
      month: 'December',
      weekday: 'Wednesday',
      label: 'Day One',
      events: [
        {
          icon: 'haldi',
          when: 'Afternoon',
          time: '',
          title: 'Haldi',
          hindi: 'हल्दी',
          accent: '#d98200',
          soft: '#fff0c9',
          desc: 'A sunshine-soaked afternoon of turmeric, marigolds and laughter...',
          descHi: 'हल्दी, गेंदे के फूलों और हँसी-ख़ुशी से भरी सुनहरी दोपहर...',
          dress: 'Shades of yellow',
          venue: ''
        },
        // ... more events
      ]
    }
  ]
};
```

### 2. Update Names and Headers
In [`index.html`](index.html), search and replace the couple's names:
- `<title>` and `<meta>` tags in `<head>`
- Rotating mantra ring text (`SHUBH VIVAH ✦ ...`)
- Main Hero section `<h1>` (`.names`)
- Portrait caption labels (`The Bride` / `The Groom`)
- Closing blessing signature (`With Love & Blessings`)

---

## 🚢 Deploying to Vercel

This repository is already configured with [`vercel.json`](vercel.json) for instant deployment:

1. Push this repository to GitHub:
   ```bash
   git add .
   git commit -m "Add wedding card web app"
   git push origin main
   ```
2. Log in to [Vercel](https://vercel.com/) and click **Add New > Project**.
3. Import this repository (`mirdul-anjali` or your repo name).
4. Leave all build settings at default (Framework Preset: **Other**, Build Command: empty).
5. Click **Deploy**. Your wedding card will be live with a free `.vercel.app` domain!

---

## 📱 Tech Stack

- **HTML5 & Vanilla JavaScript**
- **Custom CSS3** (Mobile-first, responsive paper card theme)
- **SVG / Vector Graphics** (Lightweight procedural Gond artwork)
- **Framer Motion (`motion.js`)** for spring animations and scroll choreography
- **Google Fonts**: Cormorant Garamond, Jost, Yatra One, Noto Serif Devanagari
