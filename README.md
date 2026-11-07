# Salah · Live Prayer Times

A fast, mobile-friendly prayer time app for the USA and the rest of the world.

## Features
- **Live countdown** to the next prayer, updated every second
- **Sky theme** on the main card that changes with the time of day (Fajr, Dhuhr, Asr, Maghrib, Isha)
- **Any city worldwide**: search by name, or use your phone's location
- **Correct method by country**: ISNA for the USA, Umm al-Qura for Saudi Arabia, and so on. You can change it in Settings.
- Standard or Hanafi Asr, 12 or 24-hour clock
- **Qibla compass** with live phone-compass mode and distance to the Kaaba
- 7-day timetable, Hijri date, Jumuʿah on Fridays
- Prayer notifications while the app is open
- Settings are saved on your device. Times are calculated on your device, so they still work offline.

## How to run it (step by step)
1. Open this folder in VS Code.
2. Open a terminal: **Terminal → New Terminal**.
3. The first time only, run: `npm install`
4. Start the app: `npm run dev`
5. Open the link it prints (usually http://localhost:5173) in your browser.

To try it on your phone, run `npm run dev -- --host`. Then open the "Network" link it prints on your phone. Your phone must be on the same Wi-Fi.

## Commands
| Command | What it does |
| --- | --- |
| `npm run dev` | Starts the app for development. It reloads automatically when you save a file. |
| `npm run build` | Checks for errors and creates an optimized version in `dist/`, ready to publish |
| `npm run preview` | Lets you preview the built version |

## Publishing it online (free)
Run `npm run build`, then drag the `dist` folder onto https://app.netlify.com/drop.
You can also connect the project to Vercel or Netlify.

## Project structure
```
src/
  lib/          Pure logic (no UI)
    prayer.ts     Prayer time calculation, current/next prayer, Qibla
    methods.ts    Calculation methods + default method per country
    geo.ts        City search, device location, popular cities
    format.ts     Time/date formatting helpers
  store/        Saved app state (location + settings)
  hooks/        React hooks: live clock, prayer data, notifications
  components/   UI pieces (HeroCard, PrayerList, QiblaCard, ...)
    ui/           Reusable building blocks (Card, Sheet, Switch, ...)
```

## Tech
React 19 · TypeScript 7 · Vite 8 · Tailwind CSS 4 · adhan (astronomical calculations) · Zustand · Inter font · Lucide icons.
City search uses the free Open-Meteo geocoding API. Location names come from BigDataCloud. Neither needs an API key.
