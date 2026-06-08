---
type: build-spec
section: markedsforingsplan
tenant_slug: multibord
last_updated: 2026-06-03
---

# Markedsføringsplan — bygg-spec (Multibord)

Teknisk leveranse-spesifikasjon for marketing-tiltak: SEO-implementering, sporings-pixler, lead magnet, CRO-endringer.

---

## 1. Teknisk SEO — implementering Q3 2026

### Filer som må settes opp på domenet

- `llms.txt` — opt-in for AI-crawlere
- `ai.txt` — preferanser for AI-crawlere
- `og-default.jpg` — fallback for Open Graph
- Per-produkt OG-bilder (1200x630 px, webp + jpg fallback)

### Strukturert data (JSON-LD)

- **Product JSON-LD** på alle 11 produktsider (name, image, description, brand, offers med priceCurrency=NOK, availability, sku)
- **FAQPage JSON-LD** på FAQ-side + per produkt der relevant
- **BreadcrumbList JSON-LD** på alle undersider
- **LocalBusiness JSON-LD** på forside + kontakt (adresse, åpningstider, telefon, geo-koordinater)

### Bilde-optimalisering

- Konvertere alle JPEG-bilder til WebP
- Hero-video: legge til poster-fallback (jpg/webp)
- `loading="lazy"` på alle bilder under fold
- `width` og `height`-attributter på alle img-tags

### Navigasjon

- Breadcrumbs implementert på ALLE undersider (flagget i marketing-audit som mangel)
- Bygges som visuelt synlig nav + BreadcrumbList JSON-LD

### Internasjonalisering (når engelsk lanseres)

- `hreflang`-tags på alle lokaliserte sider (nb-NO / en)
- `og:locale` + `og:locale:alternate`
- Korrekt URL-struktur per locale

### Lighthouse-mål

- Performance: ≥ 90 (mobil), ≥ 95 (desktop)
- Accessibility: ≥ 95
- Best Practices: ≥ 95
- SEO: 100

---

## 2. Meta-tags og handlingsoppfordringer

### Meta description-standard

- Inneholder "Book visning"-handlingsoppfordring der det passer naturlig
- Maks 155 tegn
- Inkluderer target-keyword for siden

---

## 3. Sporing og måling

### Måleverktøy (teknisk oppsett)

- **Plausible Analytics** — first-party-sporing, ingen cookies
- **Google Search Console** — verifisert via DNS TXT-record
- **Bing Webmaster Tools** — verifisert
- Tracking-snippet leveres via aihjelp1 platform tracker-pattern (text/plain + fetch keepalive + first-party proxy)

### Målrettet annonsering (planlagt, ikke aktivt Q3 2026)

- Meta Pixel-installasjon — fired på key events: view_product, request_quote, book_showroom
- Custom audiences: 30/60/90-dagers besøkende, product-page-viewers, quote-requesters
- Lookalike audiences når base ≥ 1000

---

## 4. Lead magnet PDF — "Altacom Produktguide 2026"

### Tekniske krav

- Format: PDF (interaktiv) + statisk PDF for nedlasting
- Filstørrelse: < 5 MB
- Sider: ~20-30
- Designer/produsent: engangs 2-3000 kr
- Levering: e-post med direktelink + auto-trigger til velkomst-serie

### Velkomst-serie (3 e-poster over 2 uker)

- E-post 1 (0 dager): PDF-leveranse + presentasjon av Multibord
- E-post 2 (5 dager): Showroom-invitasjon med direkte booking-lenke
- E-post 3 (14 dager): Case-studie eller anmeldelse + soft sales-trigger

---

## 5. Produktvelger-quiz — "Finn ditt bord"

### Tekniske krav

- 3-spørsmåls flow
- Bygges som modul i innholdsmaskin (ingen ekstra utvikling)
- Output: anbefaling av 1-2 modeller + handlingsoppfordring til showroom-booking
- Spørsmål:
  1. Hvor stort er rommet? (under 25 m², 25-50 m², over 50 m²)
  2. Hvor mange sitter rundt bordet til daglig? (2-4, 4-6, 6+)
  3. Viktigst funksjon? (kompakt sofabord, store middagsselskaper, fleksibilitet)
- Lagring: lead → CRM med quiz-resultater som metadata

---

## 6. Konverterings-endringer (frontend)

### Header

- Endre "Bestill her"-knapp til "Be om tilbud" eller "Book visning"
- A/B-test variantene mot hverandre

### Forside

- Fjern "Alle modeller"-grid fra forsiden
- Erstatt med 3-4 utvalgte modeller + "Se alle →"-lenke
- Test hero-tekst: "Slutt å velge mellom stue og spisestue" vs nåværende

### Produktsider

- Før/etter-bilder med tydelig merking "Sofabord-modus" / "Spisebord-modus"
- Prisankring-seksjon: "Ett bord, to funksjoner: Sofabord 8-15k + Spisebord 10-25k = 18-40k. Multibord: fra 10k."

### Fast handlingsknapp (sticky CTA)

- Implementeres også på desktop (mobil har allerede)
- Vises etter scroll-distanse 600px
- Skjul hvis bruker er i hero eller footer

### A/B-testing-infrastruktur

- Bruker eksisterende plausible custom-events for variant-måling
- Variant-split: 50/50 via cookieless seed (sticky per session)
- Mål-event: request_quote eller book_showroom

---

## 7. Google bedriftsprofil — teknisk integrasjon

### Anmeldelses-flyt (automatisering)

- Trigger: 14 dager etter ordre-levering (status=delivered)
- Kanal: e-post via Resend (cross-tenant-pattern)
- Innhold: kort melding + direktelink til GBP-anmeldelses-URL
- Modul: innholdsmaskin automatiserer
- Logging: track open + click til GBP-link

### GBP-anmeldelses-URL (direktelink)

- Format: `https://search.google.com/local/writereview?placeid={PLACE_ID}`
- Place ID lagres i tenant-config
