# Sunshine Second Grade

Private second-grade class website with:

- **Admin login page** that creates the teacher account (first visit) or signs in
- **2FA-gated family access** — unlock with a TOTP code from a shared QR
- **PDF newsletters** with a **bottom-right QR** that opens a hidden digital slideshow

## Quick start

```bash
npm install
npm run dev
```

Open [http://localhost:3000/admin/login](http://localhost:3000/admin/login).

1. **Create admin login** (class details + password).
2. Scan the **Admin QR** into your authenticator app, then sign in.
3. Share the **Family gate QR** from Admin → Family 2FA QR.
4. Create a newsletter — the PDF includes a QR in the bottom-right corner.
5. Scanning that QR opens the secret slideshow at `/s/<token>` (not linked in the site nav).

## Production notes

- Set `SESSION_SECRET` in `.env` (see `.env.example`).
- Set `NEXT_PUBLIC_APP_URL` so newsletter PDF QR codes point at your real domain.
- Optionally set `COOKIE_SECURE=true` behind HTTPS.
- Config, newsletters, and PDFs live under `data/` (gitignored).
