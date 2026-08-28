# Innovex Technologies — Website

A modern, self-contained website for **Innovex Technologies (PTY) LTD** (Pietermaritzburg).
It ships with an **AppShell** switcher (bottom of the screen) that lets you preview **three complete designs** and pick the one you want:

| Design | Feel | Palette |
|--------|------|---------|
| **Aurora** | Dark, futuristic, glassmorphic (your dark + accent style) | Indigo / violet / cyan |
| **Meridian** | Light, editorial, corporate & trustworthy | Teal / amber on white |
| **Pulse** | Bold, vibrant, colour-blocked bento | Blue / lime / coral |

No build step, no dependencies — one `index.html`. Fonts load from Google Fonts.

---

## 1. Deploy to Vercel

**Option A — GitHub (recommended)**
1. Create a new GitHub repo and push these files (`index.html`, `README.md`, `vercel.json`).
2. Go to [vercel.com](https://vercel.com) → **Add New… → Project** → import the repo.
3. Framework preset: **Other**. No build command needed. Click **Deploy**.

**Option B — Vercel CLI**
```bash
npm i -g vercel
cd innovex-site
vercel          # follow prompts for a preview
vercel --prod   # publish to production
```

## 2. Connect your domain (innovextechnologies.co.za)

1. In the Vercel project → **Settings → Domains → Add** → enter `innovextechnologies.co.za` (and `www.innovextechnologies.co.za`).
2. Vercel will show DNS records. At your `.co.za` registrar, set:
   - **A record** `@` → `76.76.21.21` *(Vercel shows the exact value — use theirs)*
   - **CNAME** `www` → `cname.vercel-dns.com`
3. Wait for DNS to propagate (minutes to a couple of hours). Vercel issues HTTPS automatically.

## 3. Pick ONE design for production (optional)

The switcher is great for choosing. Once you've decided, you can lock it:

- **Quick way:** in `index.html`, find `setDesign(initial||'aurora',false)` and change `'aurora'` to `'meridian'` or `'pulse'`. Then delete the whole `<div class="appshell">…</div>` block to hide the switcher.
- You can also test any design live via URL: `?design=meridian` or `?design=pulse`.

> Tell me which one you like and I'll produce a clean, single-design version (and, if you want, a full **Next.js** project).

## 4. Make the contact form send real emails

Right now the form opens the visitor's email app addressed to `hello@innovextechnologies.co.za` (a `mailto:` fallback that needs no backend). To receive submissions directly:

1. Create a free form endpoint at [formspree.io](https://formspree.io) (or use a Vercel serverless function).
2. In `index.html`, find the `form[data-contact]` submit handler and post the `FormData` to your endpoint instead of building the `mailto:` link.

## 5. Things to customise

- **Email:** currently `hello@innovextechnologies.co.za` — set up this mailbox (Microsoft 365 / Google Workspace / registrar mail).
- **WhatsApp:** `083 317 2092` (links to `wa.me/27833172092`).
- **Services & copy:** edit the `SERVICES`, `WHY`, and `STEPS` arrays in the `<script>` — content updates all three designs at once.
- **Logo:** a lightweight "ix" monogram favicon is embedded. Swap in your real logo when ready.

---
*Innovating today, empowering tomorrow.*
