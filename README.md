# CompliBoss — Marketing Website

Public marketing site for CompliBoss (Next.js 16, React 19, Tailwind v4).
This is a standalone deploy target — it contains no product code or internal documents.

## Local development
```bash
npm install
npm run dev      # http://localhost:3005
```

## Production
```bash
npm install
npm run build
npm run start    # listens on $PORT (default 3005), binds 0.0.0.0
```

## Deploy on KloudBean (Next.js app)
1. Add Application → Next.js, 2–4 GB RAM (Node 20).
2. Code Delivery → Git: connect this repo, branch `main`.
3. Runtime config:
   - App Directory: `.` (repo root)
   - Node Version: `20`
   - Install: `npm install`
   - Build: `npm run build`
   - Start: `npm run start`
   - Port: leave KloudBean's assigned port (app reads `$PORT`)
4. Environment variables:
   ```
   NODE_ENV=production
   NEXT_TELEMETRY_DISABLED=1
   NODE_OPTIONS=--max-old-space-size=2048
   NEXT_PUBLIC_APP_URL=https://app.compliboss.com
   ```
5. Pull & Deploy, then add the custom domain + SSL.
