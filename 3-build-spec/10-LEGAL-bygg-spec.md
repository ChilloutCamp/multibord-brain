---
type: build-spec
section: legal
tenant_slug: multibord
last_updated: 2026-06-03
---

# Legal — Bygg-spec (Multibord)

Tekniske implementerings-spesifikasjoner for legal-relaterte UI-elementer (footer, lenker, sider).

---

## Klikkbare kontaktpunkter (footer)

| Element | Markup |
|---------|--------|
| E-post | `<a href="mailto:kontakt@multibord.no">kontakt@multibord.no</a>` |
| Telefon | `<a href="tel:+4746260462">+47 46 26 04 62</a>` |
| Adresse | `<a href="https://maps.google.com/?q=Bygdøy+Allé+69E+0265+Oslo">Bygdøy Allé 69E, 0265 Oslo</a>` |

---

## Policy-sider — ruter

| Side | URL (no) | URL (en) |
|------|----------|----------|
| Personvernerklæring | `/personvern` | `/en/privacy` |
| Kjøpsvilkår | `/vilkar` | `/en/terms` |
| Angrerett | `/angrerett` | `/en/right-of-withdrawal` |
| Garanti | `/garanti` | `/en/warranty` |
| Cookies | `/cookies` (eller integrert i `/personvern`) | `/en/cookies` |

---

## Cookie-banner

**Skal IKKE implementeres.** Multibord bruker kun:
- Session-cookie (teknisk nødvendig — unntatt fra consent-krav)
- LocalStorage for språk-valg (ikke server-cookie)
- Plausible analytics (cookiefritt)

Ingen tracking → ingen banner. Build skal IKKE inkludere consent-banner-komponent.

---

## Tracking — explicit ikke-liste

Disse skal IKKE installeres i `<head>` eller via tag-manager:
- Google Analytics (gtag, ga)
- Meta Pixel (fbq)
- Hotjar / Microsoft Clarity / Mouseflow
- TikTok Pixel
- LinkedIn Insight Tag
- Google Tag Manager

**Eneste tillatte analytics:** Plausible (self-hosted eller plausible.io) — cookiefritt, ingen consent nødvendig.

---

## Footer-komponent — datakilder

Footer-komponenten skal lese fra `10-LEGAL.md` følgende felter:
- Selskap → "Compact Living AS"
- Org.nr → "921 887 922"
- MVA-nummer → "NO921887922MVA"
- Registrert adresse → "Bygdøy Allé 69E, 0265 Oslo"
- Telefon → "+47 46 26 04 62"
- E-post → "kontakt@multibord.no"

---

## TODO (build-tasks)

- Lage policy-sider på multibord.no: `/personvern`, `/vilkar`, `/angrerett`, `/garanti`
- Bygge footer-komponent som leser fra 10-LEGAL.md
- Implementere språk-valg via localStorage (no/en)
- Verifisere WCAG 2.1 AA i Lighthouse for alle policy-sider
