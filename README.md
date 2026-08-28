# Innovex Technologies — Website

A modern one-page website for **Innovex Technologies (PTY) LTD** (Pietermaritzburg), built on the **Aurora** design and skinned to your brand colours.

- **Petrol teal** `#073235` / `#0C4E52` base · **mint accent** `#3CDAAC`
- Your logo is embedded directly in the page (no separate image file needed)
- Self-contained `index.html` — no build step, no dependencies. Fonts load from Google Fonts.

`innovex-logo.png` is the cropped/optimised logo, included for reuse (social, email signatures, etc.).

---

## 1. Deploy to Vercel

**GitHub (recommended)**
1. Push these files to a new GitHub repo (`index.html`, `vercel.json`, `README.md`).
2. [vercel.com](https://vercel.com) → **Add New… → Project** → import the repo.
3. Framework preset: **Other**. No build command. **Deploy**.

**CLI**
```bash
npm i -g vercel
cd innovex-site
vercel --prod
```

## 2. Connect your domain

1. Vercel project → **Settings → Domains → Add** → `innovextechnologies.co.za` and `www.innovextechnologies.co.za`.
2. At your `.co.za` registrar, add the DNS records Vercel shows (typically an **A** record for `@` and a **CNAME** for `www` → `cname.vercel-dns.com`).
3. HTTPS is issued automatically once DNS resolves.

## 3. Make the contact form send real emails

The form currently opens the visitor's mail app addressed to `hello@innovextechnologies.co.za` (a `mailto:` fallback, no backend needed). To capture submissions directly, create a free endpoint at [formspree.io](https://formspree.io) and post the form's `FormData` to it inside the `form[data-contact]` handler in `index.html`.

## 4. Customise

- **Email:** set up the `hello@` mailbox (Microsoft 365 / Google Workspace / registrar mail).
- **WhatsApp:** `083 317 2092` → links to `wa.me/27833172092`.
- **Services & copy:** edit the `SERVICES` and `WHY` arrays in the `<script>`.
- **Logo:** embedded as a data URI in the hero, plus an SVG pulse mark in the nav/footer and favicon. Re-export from `innovex-logo.png` if you refine the brand.

---
*Innovating today, empowering tomorrow.*
