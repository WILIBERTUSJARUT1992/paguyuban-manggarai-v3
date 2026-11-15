<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://ai.google.dev/static/site-assets/images/share-ais-513315318.png" />
</div>

# Run and deploy your AI Studio app

This contains everything you need to run your app locally.

View your app in AI Studio: https://ai.studio/apps/0781c63f-9db3-4cf5-804b-f649dd67414b

## Run Locally

**Prerequisites:**  Node.js


1. Install dependencies:
   `npm install`
2. Set the `GEMINI_API_KEY` in [.env.local](.env.local) to your Gemini API key
3. Run the app:
   `npm run dev`

\n## Firebase setup\n
Firebase web configuration is in `src/firebase.ts`. Administrator sign-in uses Firebase
Authentication for `wilibertusjarut124@gmail.com`. Member-code login remains the legacy
local flow and is not yet Firebase Authentication.

Realtime Database paths:
- `paguyuban/members`
- `paguyuban/contributions`

Run `npm install` and `npm run dev`. Before production use, configure restrictive
Realtime Database Security Rules. Do not enable public read/write access.

\nImportant: Firebase Authentication login is wired in this build. Realtime Database
read/write synchronization is intentionally not enabled yet. Configure and verify
database security rules and decide how to migrate existing member/finance records
before enabling cloud writes, so sample/demo data is not accidentally uploaded.


## GitHub Pages deployment
This project is configured for the repository path `/paguyuban-manggarai-v3/`. The included GitHub Actions workflow builds and deploys the Vite app to GitHub Pages when changes are pushed to the `main` branch. In the repository settings, set Pages source to **GitHub Actions**. Add `wilibertusjarut1992.github.io` to Firebase Authentication Authorized domains.
