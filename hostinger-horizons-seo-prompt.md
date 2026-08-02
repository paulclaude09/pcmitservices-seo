# Hostinger Horizons — SEO fix prompt (PCM IT Services)

Copy everything inside the block below into **Hostinger Horizons AI** (or your Horizons project chat). Adjust only if your builder UI labels differ.

---

```
You are editing the PCM IT Services website (local IT support in Moncton, Dieppe, Riverview, and Greater Moncton, NB). Phone: 506-218-1888. Primary email: support@pcmitservices.com. Service area: Greater Moncton — do not add a fake street address.

## Problem (must fix first)

This is a Hostinger Horizons SPA. The initial HTML served for every route still has:
<title>Hostinger Horizons</title>

After JavaScript runs, per-page titles and meta descriptions are correct, but Google, social previews, and curl/view-source only see "Hostinger Horizons" on all URLs. That is blocking local SEO.

## Your goals

1. Make the **first HTML response** (before JS) include the correct <title> and <meta name="description"> for each public route — not "Hostinger Horizons".
2. Keep existing visible page content, design, and client-side routing; do not break forms, quote builder, or chat.
3. Align NAP everywhere: business name "PCM IT Services", phone 506-218-1888, email support@pcmitservices.com.
4. Set utility/internal pages to noindex (or equivalent) so they are not primary SEO targets.
5. Ensure LocalBusiness / Organization / Service JSON-LD uses the same email as the site (support@, not info@).

## How to implement (Horizons / Hostinger)

- Check **Site settings** (or global project settings) for any default site title or brand name set to "Hostinger Horizons" and change it to "PCM IT Services".
- For **each public page**, use **Page settings → SEO** (title + meta description). If Horizons supports pre-render, static export, or server-side meta injection for routes, enable it so meta tags are in the initial HTML shell, not only via React/document.title after load.
- If there is a single shared index.html template, update it so route-specific title/description can be injected at build or request time per path.
- After changes, verify: fetching the homepage HTML with curl (no browser) must show a PCM title, not Hostinger Horizons. Repeat for /contact and one service URL.

## Pages — SEO title + meta (paste into Page SEO settings)

Homepage (/)
- Title (48 chars): IT Support Moncton | Managed IT | PCM IT Services
- Meta (155 max): Managed IT support and cybersecurity for Moncton, Dieppe & Riverview small businesses. On-site & remote help. Call 506-218-1888.
- H1 (keep one): PCM IT Services - On-Site & Remote IT Support in Moncton, NB

/about
- Title: About PCM IT Services | Managed IT Support in Moncton
- Meta: Learn about PCM IT Services — managed IT partner for Greater Moncton small businesses. Expert support and proactive guidance.

/contact
- Title: Contact PCM IT Services | Moncton NB | 506-218-1888
- Meta: Contact PCM IT Services for managed IT support in Greater Moncton. Call 506-218-1888 or use our online form.

/services
- Title: Managed IT Services Moncton | PCM IT Services
- Meta: Managed IT, cybersecurity, Wi-Fi, backups, and business tech services for Moncton, Dieppe, and Riverview. Free consultation.

/services/small-business-it-support
- Title: Managed IT Services Moncton | PCM IT Services
- Meta: Complete managed IT for Greater Moncton small businesses — monitoring, help desk, security, and on-site support.

/services/wifi-networking-setup
- Title: Wi-Fi Setup Moncton | Business Networks | PCM IT
- Meta: Professional Wi-Fi and network setup for Moncton businesses. Secure, reliable coverage for offices and retail.

/services/virus-malware-removal
- Title: Virus Removal Moncton | Malware Help | PCM IT
- Meta: Virus and malware removal for Moncton businesses. Fast cleanup, prevention, and remote or on-site support.

/services/retail-pos-system-setup
- Title: POS System Setup Moncton | Retail IT | PCM IT
- Meta: Retail POS setup and support in Greater Moncton. Secure checkout, networking, and ongoing IT help.

## Noindex these routes (utility — not for Google)

Apply "hide from search engines" / noindex on:
- /quote-builder
- /client-onboarding
- /ai-readiness-assessment
- /it-service-assessment
- /ai-agent-requirements

Remove them from main navigation if they are linked for SEO; keep functional links from emails or admin only.

## New page to create (high priority)

Create a new public page:
- Path: /it-support-moncton
- Title: IT Support Moncton NB | Small Business | PCM IT
- Meta: Local IT support in Moncton, Dieppe & Riverview. Help desk, cybersecurity & on-site techs. Free consultation — 506-218-1888.
- H1: IT Support in Moncton, Dieppe & Riverview
- Content: 500–800 words — who we serve, services (help desk, managed IT, security, backup), why local on-site matters, FAQ (response times, remote vs on-site), CTA with phone and link to /contact.
- Add internal links from homepage, /services, and footer.

## Schema (JSON-LD)

On homepage and contact, ensure LocalBusiness includes:
- name: PCM IT Services
- telephone: +1-506-218-1888
- email: support@pcmitservices.com
- areaServed: Moncton, Dieppe, Riverview, Greater Moncton, NB
- url: production site root

Do not duplicate conflicting Organization blocks with a different email.

## Sitemap

Regenerate sitemap in Hostinger SEO settings after publishing. Confirm /sitemap.xml returns 200 and lists public pages only (exclude noindex utility pages if the platform allows).

## Done when

1. curl/view-source on / shows PCM title in raw HTML.
2. Each major service page has unique title + meta in raw HTML.
3. support@ is consistent in footer, contact, and schema.
4. Utility pages are noindex.
5. /it-support-moncton exists and is linked internally.

List every file or setting you changed and any limitation Horizons imposes on server-side meta.
```

---

## Short version (if character limit)

If the Horizons chat has a tight limit, use this:

```
Fix SEO for PCM IT Services (Moncton NB MSP). Raw HTML on all routes still shows <title>Hostinger Horizons</title>; client-side titles are correct after JS. Change global/site title, enable per-route title+meta in initial HTML (pre-render or SEO shell). Set Page SEO on /, /about, /contact, /services, and all /services/* pages using our audit copy. NAP: PCM IT Services, 506-218-1888, support@pcmitservices.com in footer and JSON-LD (remove info@). Noindex: quote-builder, client-onboarding, ai-readiness-assessment, it-service-assessment, ai-agent-requirements. Create /it-support-moncton with H1 "IT Support in Moncton, Dieppe & Riverview". Verify with curl that homepage title is not Hostinger Horizons.
```
