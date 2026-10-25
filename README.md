# Digital Wedding Invitation (Shaadi Card)

A luxury, interactive digital Indian wedding card web application inspired by traditional royal aesthetics and Gond folk art.

This repository is a faithful replication of [kunika-navneet-wedding-card.vercel.app](https://kunika-navneet-wedding-card.vercel.app/), customized for **Mridul & Kunika** with the **Groom details positioned first**, and upgraded with a **dynamic configuration system** (`config.json` & `config.js`).

---

## ✨ Features

- **🤵 Groom Details First**: Mridul Raj & Kunika Singh. Groom's name and illustrated portrait are positioned first throughout the entire invitation (Hero, Portraits, Royal Seal, Loader, Blessings, Calendar, and Share Dialog).
- **📂 Dynamic Configuration (`config.json` & `config.js`)**: All names, dates, events, venues, descriptions, and greetings are decoupled from HTML.
- **🌐 100% Offline & Online Compatibility**: Works seamlessly both when double-clicked directly from your file system (`file:///`) and when served over HTTP/HTTPS (Vercel, local server).
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

## 🚀 Quick Start (Run & Preview)

### Option 1: Direct File Open (Offline)
Simply double-click [`index.html`](index.html) to open in your favorite web browser. Thanks to the `<script src="config.js">` bridge, your customized details will load without local file CORS blocking.

### Option 2: Using Python's Local Server
Run in your terminal from this folder:

```bash
python -m http.server 3000
```

Then open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🛠️ Customizing Details

You can edit your wedding details in either [`config.json`](config.json) (for web hosting / Vercel) or [`config.js`](config.js) (for local offline opening).

```json
{
  "meta": {
    "title": "Mridul & Kunika · Shubh Vivah",
    "description": "You are invited to the wedding of Mridul Raj & Kunika Singh · 2–3 December 2026"
  },
  "couple": {
    "groom": {
      "name": "Mridul Raj",
      "heroName": "Mridul",
      "hindi": "मृदुल राज",
      "role": "The Groom",
      "portrait": ""
    },
    "bride": {
      "name": "Kunika Singh",
      "heroName": "Kunika",
      "hindi": "कुनिका सिंह",
      "role": "The Bride",
      "portrait": ""
    },
    "monogram": "M & K"
  },
  "wedding": {
    "topBlessing": "॥ जय जिनेन्द्र ॥",
    "subBlessing": "॥ शुभ विवाह ॥",
    "sealMantra": "SHUBH VIVAH ✦ MRIDUL & KUNIKA ✦ 2 & 3 DECEMBER 2026 ✦",
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
    // Haldi, Ring Ceremony, Phere, Baraat & Reception details
  ],
  "blessings": {
    "sectionHindi": "आशीर्वाद",
    "sectionTitle": "With Love & Blessings",
    "lead": "Your presence and blessings will make our celebration complete.",
    "leadHi": "आपकी उपस्थिति और आशीर्वाद से हमारा उत्सव पूर्ण होगा।",
    "signature": "Mridul & Kunika",
    "family": "with our families",
    "closingMantra": "॥ जय जिनेन्द्र ॥"
  }
}
```

---

## 🚢 Deploying to Vercel

1. Push your changes to GitHub:
   ```bash
   git add .
   git commit -m "Configure wedding card for Mridul & Kunika"
   git push origin main
   ```
2. Log in to [Vercel](https://vercel.com/) and click **Add New > Project**.
3. Import your repository.
4. Leave all settings at default (**Other** preset, no build command).
5. Click **Deploy**. Your wedding card will be live instantly!
