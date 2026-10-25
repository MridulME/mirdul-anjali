# Digital Wedding Invitation (Shaadi Card)

A luxury, interactive digital Indian wedding card web application inspired by traditional royal aesthetics and Gond folk art.

This repository is a faithful replication of [kunika-navneet-wedding-card.vercel.app](https://kunika-navneet-wedding-card.vercel.app/), upgraded with a **dynamic JSON-driven configuration system** (`config.json`).

---

## ✨ Features

- **📂 JSON-Driven Architecture**: All names, dates, events, venues, descriptions, and greetings are decoupled from HTML and loaded dynamically from [`config.json`](config.json).
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
- **⚡ Zero Build Dependencies**: Pure HTML5, CSS3, and Vanilla JavaScript with Framer Motion (`motion.js`) loaded via CDN. No compilation or node_modules required.

---

## 🚀 Quick Start (Run Locally)

You can run this project locally without installing Node.js or any build tools.

### Option 1: Using Python's Local Server (Recommended)
Run in your terminal from this folder:

```bash
python -m http.server 3000
```

Then open [http://localhost:3000](http://localhost:3000) in your browser. Any edits you make to `config.json` will instantly reflect when you refresh the page!

### Option 2: Open Directly in Browser
You can also double-click [`index.html`](index.html). The app includes an embedded fallback configuration so it renders even if local file fetching (`file:///`) is restricted by the browser.

---

## 🛠️ Dynamic Configuration (`config.json`)

To customize the wedding invitation, simply edit [`config.json`](config.json). **No need to touch the HTML!**

```json
{
  "meta": {
    "title": "Anjali & Mridul · Shubh Vivah",
    "description": "You are invited to the wedding of Anjali & Mridul · 2–3 December 2026",
    "ogTitle": "Anjali & Mridul · Shubh Vivah",
    "ogDescription": "Haldi, Ring Ceremony, Sangeet, Phere, Baraat & Reception · 2–3 December 2026"
  },
  "couple": {
    "bride": {
      "name": "Anjali",
      "hindi": "अंजलि",
      "role": "The Bride",
      "portrait": ""
    },
    "groom": {
      "name": "Mridul",
      "hindi": "मृदुल",
      "role": "The Groom",
      "portrait": ""
    },
    "monogram": "A & M"
  },
  "wedding": {
    "topBlessing": "॥ जय जिनेन्द्र ॥",
    "subBlessing": "॥ शुभ विवाह ॥",
    "sealMantra": "SHUBH VIVAH ✦ ANJALI & MRIDUL ✦ 2 & 3 DECEMBER 2026 ✦",
    "sealTap": "Tap to open",
    "gateInviteHi": "आप सादर आमंत्रित हैं",
    "gateInviteEn": "You are cordially invited",
    "gateDate": "2 – 3 December 2026",
    "eyebrow": "Together with their families",
    "invitationLine": "request the honour of your presence as they begin their forever",
    "dates": {
      "ariaLabel": "Wednesday 2 and Thursday 3 December 2026",
      "startDay": "Wed",
      "startDate": "02",
      "endDay": "Thu",
      "endDate": "03",
      "monthYear": "December 2026"
    }
  },
  "countdown": {
    "target": "2026-12-02T12:00:00+05:30",
    "note": "until the haldi begins · Wednesday, 2 December"
  },
  "venue": {
    "name": "Krishnam Resort & Marriage Garden",
    "address": "Damoh, Madhya Pradesh",
    "mapUrl": "https://maps.app.goo.gl/imVwWHP4Yv332h2F8"
  },
  "days": [
    {
      "iso": "20261202",
      "num": "02",
      "month": "December",
      "weekday": "Wednesday",
      "label": "Day One",
      "tabLabel": "Day One",
      "tabSub": "Wed · 2 Dec",
      "events": [
        {
          "icon": "haldi",
          "when": "Afternoon",
          "time": "",
          "title": "Haldi",
          "hindi": "हल्दी",
          "accent": "#d98200",
          "soft": "#fff0c9",
          "desc": "A sunshine-soaked afternoon of turmeric, marigolds and laughter...",
          "descHi": "हल्दी, गेंदे के फूलों और हँसी-ख़ुशी से भरी सुनहरी दोपहर...",
          "dress": "Shades of yellow",
          "venue": ""
        }
      ]
    }
  ],
  "blessings": {
    "sectionHindi": "आशीर्वाद",
    "sectionTitle": "With Love & Blessings",
    "lead": "Your presence and blessings will make our celebration complete.",
    "leadHi": "आपकी उपस्थिति और आशीर्वाद से हमारा उत्सव पूर्ण होगा।",
    "signature": "Anjali & Mridul",
    "family": "with our families",
    "closingMantra": "॥ जय जिनेन्द्र ॥"
  }
}
```

### Custom Illustrations
To use custom portrait artwork instead of the built-in Gond silhouettes:
1. Place your PNG/JPG illustration files in this repository (e.g., `groom.png` and `bride.png`).
2. Set `"portrait": "bride.png"` and `"portrait": "groom.png"` in [`config.json`](config.json).

---

## 🚢 Deploying to Vercel

1. Push your changes to GitHub:
   ```bash
   git add .
   git commit -m "Configure wedding card"
   git push origin main
   ```
2. Log in to [Vercel](https://vercel.com/) and click **Add New > Project**.
3. Import your repository.
4. Leave all settings at default (**Other** preset, no build command).
5. Click **Deploy**. Your wedding card will be live instantly!

---

## 📱 Tech Stack

- **Dynamic JSON configuration (`config.json`)**
- **HTML5 & Vanilla JavaScript**
- **Custom CSS3** (Mobile-first, responsive paper card theme)
- **SVG / Vector Graphics** (Procedural Gond art)
- **Framer Motion (`motion.js`)** for spring animations and scroll choreography
- **Google Fonts**: Cormorant Garamond, Jost, Yatra One, Noto Serif Devanagari
