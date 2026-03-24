# Hodos Browser Website — Planning

**Created:** 2026-03-17
**Status:** Planning

---

## Purpose

Download site for Hodos Browser MVP. Users come here to:
1. Learn what Hodos is (briefly)
2. Download the installer
3. Find documentation/support links

---

## Decisions Made

### Domain & Hosting

| Decision | Choice | Rationale |
|----------|--------|-----------|
| **Registrar** | Cloudflare | At-cost pricing, best DNS/security, CDN included |
| **Domain** | `hodosbrowser.com` ✅ | Verified available 2026-03-17. Universal trust, descriptive, ~$10/yr |
| **Hosting** | Cloudflare Pages | Free, fast, auto-deploy from git, global CDN |
| **Email** | Cloudflare Email Routing → Gmail | Free forwarding, send via Gmail SMTP |

### Tech Stack

| Decision | Choice | Rationale |
|----------|--------|-----------|
| **Site type** | Static | Fast, cheap, no maintenance, perfect for download page |
| **Framework** | TBD: Astro or plain HTML | Astro if we want components; plain HTML if keeping it dead simple |
| **Styling** | TBD: Tailwind or vanilla CSS | |

---

## Domain Options

| Domain | TLD | Availability | Notes |
|--------|-----|--------------|-------|
| hodos.com | .com | ❌ Taken | Parked/for sale, expires 4/2026 |
| hodos.io | .io | ✅ Available | Tech vibe, ~$35/yr |
| **hodosbrowser.com** | **.com** | **✅ VERIFIED AVAILABLE** | Clear, trusted, ~$10/yr |
| hodosbrowser.app | .app | ✅ Likely available | Modern, forces HTTPS, ~$15/yr |
| gethodos.com | .com | ✅ Likely available | Action-oriented |

**DECISION:** `hodosbrowser.com` — locked in 2026-03-17

---

## Site Structure (MVP)

```
/                   → Landing page (hero, value prop, download button)
/download           → Download page with platform options (Windows first)
/docs               → Link to external docs or embedded getting started
/privacy            → Privacy policy
/terms              → Terms of service (if needed)
```

### Landing Page Content

1. **Hero section**
   - Tagline: TBD (something about owning your keys, native BSV wallet)
   - Download button (prominent)
   - Screenshot or mockup of browser

2. **Features section** (3-4 bullets max)
   - Native BSV wallet built-in
   - Your keys, your coins (self-custody)
   - BRC protocol support (identity, payments, etc.)
   - Fast Chromium-based browsing

3. **Download section**
   - Windows (MVP)
   - macOS (coming soon)
   - Linux (coming soon)

4. **Footer**
   - Links: GitHub, Discord/community, Marston Enterprises
   - Privacy policy, Terms

---

## Email Setup Plan

1. Register domain on Cloudflare
2. Add MX records for Cloudflare Email Routing
3. Create routes:
   - `hello@hodosbrowser.com` → matt@marstonenterprises.com (or personal Gmail)
   - `support@hodosbrowser.com` → same
   - Catch-all → same (optional)
4. Configure Gmail to send as `hello@hodosbrowser.com` via SMTP

---

## Migration Plan (Future)

### Marston Enterprises Domain

Currently on Hostinger. After Hodos is stable:

1. Transfer `marstonenterprises.com` to Cloudflare Registrar
2. Set up Cloudflare Email Routing for ME domain
3. Migrate website to Cloudflare Pages (or keep on Hostinger if working)

**Goal:** Single pane of glass for all domains on Cloudflare.

---

## Open Questions

- [x] Final domain choice: `.com` vs `.app`? → **hodosbrowser.com**
- [ ] Framework: Astro (components, markdown support) vs plain HTML?
- [ ] Branding: Do we have logo, colors, fonts defined?
- [ ] Legal: Need privacy policy template?
- [ ] Analytics: Cloudflare Analytics (free, privacy-respecting) or something else?

---

## Next Steps

1. Finalize domain choice
2. Set up folder structure for chosen framework
3. Create wireframe/mockup of landing page
4. Write copy (tagline, features, etc.)
5. Register domain when ready
