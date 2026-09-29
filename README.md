# Berlintapete® Smart Wallpaper Configurator

**Live:** https://earnest-peony-0c9a8e.netlify.app  
**Admin:** https://earnest-peony-0c9a8e.netlify.app/admin.html

## Was das ist
Single-File Web-App für individuell konfigurierbare Fototapeten.  
Gedruckt auf Canon Colorado (UVgel) · Deployment via Netlify.

## Features
- 160.000+ Motive via SmugMug API
- Canon Colorado FLXfinish+, 12 Materialien, Druckmodi
- Zahlungsarten: Rechnung, Überweisung, PayPal, Stripe (Kreditkarte/Apple Pay/Google Pay/SEPA)
- Easybill REST API — automatische Rechnungserstellung
- EU-weit: MwSt 30 Länder, DHL International
- DE/EN Sprachumschaltung, DSGVO-Banner
- WIX postMessage Bridge (iFrame-Embedding)
- Admin-Backend: /admin.html (SHA-256 geschützt)

## Dateistruktur
```
index.html                          ← Konfigurator (574KB, Single File)
admin.html                          ← Admin-Backend
_redirects                          ← Netlify API-Proxies
netlify.toml                        ← Netlify Config
netlify/functions/
  create-payment-intent.js          ← Stripe Payment Intent (serverless)
```

## API-Proxies (_redirects)
| Route | Ziel |
|---|---|
| /smugmug/* | SmugMug API |
| /smimg/* | SmugMug CDN |
| /easybill/* | Easybill REST API |

## Netlify Environment Variables (Secret Keys — niemals in Code!)
| Variable | Beschreibung |
|---|---|
| `STRIPE_SECRET_KEY` | Stripe Secret Key (sk_live_...) |

## Admin Setup
1. `admin.html` öffnen
2. 🧾 Easybill → API Key eintragen
3. 💳 Stripe → Publishable Key eintragen
4. 🖨 Canon Colorado → Druckparameter prüfen

## Stand
Version: 27.04.2026 · 52/52 Audit-Checks bestanden
