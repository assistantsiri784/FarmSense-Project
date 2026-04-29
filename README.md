# FarmSense

FarmSense is a mobile-first React demo for farmers to set up a profile, scan disease photos, review weather-driven advice, get multilingual guidance, and check market prices.

## Stack

- React + TypeScript
- React Router
- i18next
- Vite
- Offline-ready service worker and web manifest

## Run locally

```bash
npm install
npm run dev
```

## Optional API configuration

Copy [.env.example](.env.example) to `.env` and set any of the following values to connect real services:

- `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` for OTP login and profile persistence
- `VITE_ENABLE_REAL_APIS=true`
- `VITE_FARMSENSE_API_BASE_URL` for your FarmSense backend
- `VITE_OPENWEATHER_API_KEY` for live weather data
- `VITE_OPENWEATHER_BASE_URL` if you use a custom weather endpoint

If these values are not set, the app uses the built-in demo data and still works end-to-end.

If Supabase OTP emails are not arriving, check that email auth is enabled in the Supabase dashboard and that the project's SMTP/deliverability settings are configured. The app will now show the Supabase error instead of silently switching to demo mode.

The login page now sends OTP with a redirect back to `/login` and includes a resend button for users who do not receive the first message.

### Backend contract

The frontend now sends typed request payloads for weather, disease scan, advisor, market guidance, and yield prediction. Use the shared schema in [src/contracts/farmSenseApi.ts](src/contracts/farmSenseApi.ts) when implementing the backend.

## Build

```bash
npm run build
```

## What is included

- Landing page with a pitch-style hero
- Farm profile setup with GPS detection support
- Dashboard with weather, health, alert, and yield cards
- Disease scanner demo with treatment output
- Multilingual AI advisor mock flow
- Market price advisor with local mandi suggestions
