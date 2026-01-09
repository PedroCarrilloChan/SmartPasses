# Smart Passes Website

## Overview
Website for Smart Passes, a digital wallet marketing platform. Includes the main marketing site for businesses and a separate landing page for the Android wallet app.

## Project Structure
```
/
├── index.html              # Main marketing page for businesses
├── wallet.html             # Android wallet app landing page (for Play Store)
├── wallet-privacy-policy.html  # Privacy policy for wallet app (Play Store)
├── wallet-terms-of-service.html # Terms of service for wallet app
├── privacy-policy.html     # Privacy policy page (main platform)
├── terms-of-service.html   # Terms of service page (main platform)
├── api-docs.html           # API documentation
├── server.js               # Express.js server
├── script.js               # Main JavaScript
├── style.css               # Additional styles
├── package.json            # Node.js dependencies
└── attached_assets/        # Images and assets
```

## Routes
- `/` - Main marketing page (B2B)
- `/wallet` - Android wallet app landing page (B2C, for Play Store)
- `/wallet-privacy-policy` - Privacy policy for wallet app (Play Store compliant)
- `/wallet-terms-of-service` - Terms of service for wallet app
- `/privacy-policy` - Privacy policy (main platform)
- `/terms-of-service` - Terms of service (main platform)

## Tech Stack
- Node.js with Express.js
- Tailwind CSS (CDN)
- Vanilla JavaScript

## Running the Project
```bash
npm start
```
Server runs on port 5000.

## Recent Changes
- 2026-01-09: Created separate wallet.html page for Android app (Play Store landing page)
- 2026-01-09: Added /wallet route and navigation link from main page

## Play Store Requirements
The wallet.html page is designed to serve as the app's landing page for Google Play Store submission:
- Privacy Policy link: /privacy-policy
- Terms of Service link: /terms-of-service
- Contact email: support@smartpasses.app
- App download button with Google Play badge
