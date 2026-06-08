---
type: build-spec
section: seo
tenant_slug: multibord
last_updated: 2026-06-03
---

# SEO — Bygg-spec (Multibord)

Teknisk SEO-spec for bygging av nettsiden: title/meta-tags per side-type, JSON-LD-schema, tekniske krav, Google Bedriftsprofil-implementering, tracking-pixler.

---

## 1. Title + meta + heading-spec per side-type

### Forsiden

- **Title:** "Multibord — Sofa- og spisebord i ett | Italienske transformerbare bord | Oslo Showroom"
- **Meta:** "11 modeller transformerbare bord fra Altacom Italia. Trinnløs gassløft fra sofabord til spisebord. Test alle modeller på Bygdøy Allé Oslo. Fra 10 000 kr. 2 års garanti."
- **H1:** "Sofa- og spisebord . alt i ett" (matcher faktisk site)
- **OG-image:** Hero-bord i interiør-kontekst (1200x630)

### Produkt-sider (eksempel: Ares Fold)

- **Title:** "Ares Fold — Transformerbart spisebord 200-320 cm | Multibord"
- **Meta:** "Ares Fold utvides fra 120 til 220 cm — plass til 10 ved bordet. Italiensk håndverk fra Altacom. Test på showroom Oslo eller bestill direkte. 2 års garanti."
- **H1:** "Ares Fold — fra kompakt linje til spisebord for 10"
- **JSON-LD:** Product med pris, brand, availability, aggregateRating

### Kategori-side

- **Title:** "Transformerbare bord — Sofa- og spisebord-i-ett | Multibord Oslo"
- **Meta:** "11 modeller transformerbare bord fra Altacom Italia. Trinnløs høydejustering 11-88 cm. Test i Oslo showroom. Fra 10 000 kr."
- **H1:** "Sofa- og spisebord i ett — 11 modeller fra Italia"

### Showroom-side

- **Title:** "Showroom Oslo — Test alle 11 modeller | Multibord Bygdøy Allé"
- **Meta:** "Compact Living Store på Bygdøy Allé 69E Oslo. Test 11 modeller transformerbare bord. Åpent Man-Fre 11-17, Lør 11-16. Telefon +47 46 26 04 62."
- **H1:** "Test bordet på Bygdøy Allé før du bestiller"

### Blogg-pillar (eksempel)

- **Title:** "Heve-senk-bord 2026: komplett guide — gassløft, materialer, pris"
- **Meta:** "Komplett guide til heve-senk-bord. Gassløft vs elektrisk, italiensk vs masseprodusert, materialer, pris. Skrevet av Multibord — Norges spesialist."
- **H1:** "Heve-senk-bord — alt du trenger å vite før du kjøper"

---

## 2. JSON-LD-schema

### Organization (på alle sider, i layout)

```json
{
  "@type": "Organization",
  "name": "Multibord",
  "legalName": "Compact Living AS",
  "url": "https://multibord.no",
  "logo": "https://multibord.no/logo-multibord.png",
  "sameAs": ["https://www.instagram.com/multibord/"],
  "vatID": "NO921887922MVA",
  "taxID": "921887922"
}
```

### LocalBusiness (på kontakt + about)

```json
{
  "@type": "FurnitureStore",
  "name": "Multibord Showroom",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Bygdøy Allé 69E",
    "addressLocality": "Oslo",
    "postalCode": "0265",
    "addressCountry": "NO"
  },
  "openingHoursSpecification": [
    {"@type": "OpeningHoursSpecification", "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday"], "opens": "11:00", "closes": "17:00"},
    {"@type": "OpeningHoursSpecification", "dayOfWeek": "Saturday", "opens": "11:00", "closes": "16:00"}
  ],
  "telephone": "+47 46 26 04 62",
  "email": "kontakt@multibord.no",
  "priceRange": "kr 10000-50300"
}
```

### Product (per produkt-side, alle 11 modeller)

```json
{
  "@type": "Product",
  "name": "Ares Fold",
  "brand": {"@type": "Brand", "name": "Altacom"},
  "offers": {
    "@type": "Offer",
    "price": "29700",
    "priceCurrency": "NOK",
    "availability": "https://schema.org/InStock"
  },
  "aggregateRating": { "ratingValue": "4.8", "reviewCount": "44" }
}
```

### FAQPage (på FAQ-side + per produkt der det passer)

Hver Q&A i 3-FAQ blir et FAQPage-entry. Hjelper AI Overviews + Google snippet-rangering.

### BreadcrumbList (på alle indre sider)

Forsiden → Kategori → Produkt

### Article (per blogginnlegg)

author, datePublished, image, headline

---

## 3. Tekniske SEO-krav

- Lighthouse Performance ≥90 (mobil)
- LCP <2.5s
- INP <200ms
- CLS <0.1
- WebP for alle produktbilder
- Lazy-load alt under fold
- Sitemap.xml + robots.txt
- hreflang om vi gjør engelsk-versjon
- Canonical URLs på alle paginerte sider
- 404-side med søk + populære produkter
- Breadcrumbs på ALLE sider (ikke bare produktsider)

---

## 4. AI-trafikk teknisk implementering

### Fakta-bokser på produktsider

- Hver produktside har "Fakta-boks" med tall: "Mål: 95×72 cm | Høyde: 27-81 cm | Trinnløst | 2 års garanti | Pris fra kr 20 200"
- Tall i tekst > tall i bilder
- Korte påstander med kilde: "Altacom Italia produserer hver enhet ved fabrikk i [region]"

### E-E-A-T-signaler

- Author-bio på blogg-artikler (Marius / Multibord-team)
- "Sist oppdatert" dato på alle informasjons-sider
- Lenke til Altacom Italia som leverandør (kilde-autoritet)
- Org.nr 921 887 922 synlig i footer
- MVA-nummer NO921887922MVA synlig

### llms.txt + ai.txt

- `/llms.txt` — kort fil som forteller AI hva siden handler om, hovedprodukter, kontakt
- `/ai.txt` — policy for AI-crawling (vi tillater citering)

### FAQ-format på informasjons-sider

- AI-svar-snippet-vennlig: spørsmål → kort konkret svar (2-3 setninger)
- Direkte fra `3-FAQ.md`

### Lokale referanser

- "Oslo", "Bygdøy", "Frogner", "Norge" naturlig vevd inn i innhold

---

## 5. Tracking + måling

- **Plausible** (cookiefritt, GDPR-trygt) — trafikk, hendelser, kilder
- **Google Search Console** — posisjoner, klikk, impressions per søkeord
- **Bing Webmaster Tools** (for AI-trafikk — Bing driver mange AI-svar)
- **Google Bedriftsprofil Insights** — visnings-anrop, ruter, anmeldelses-vekst
- **Platform-events** — leads, bookings, ordrer per kilde

Ukentlig sjekk: posisjoner på Tier 1-søkeord + nye AI-Overview-siteringer.
