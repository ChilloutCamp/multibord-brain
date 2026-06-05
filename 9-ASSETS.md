---
type: bedrift-data
section: assets
tenant_slug: multibord
syncs_to_brain: assets, images, video, models_3d
last_updated: 2026-06-03
fill_order: 8
ui_section: "Assets (bilder)"
sources:
  - /public/ katalog (verifisert 2026-06-03)
  - 1-PROFIL-OG-MERKEVARE.md (imagery direction)
  - 6-PRODUKTER.md (per-modell bildebehov)
---

# Assets — Multibord

> **Selvstendig om:** Hele asset-biblioteket. Bilder, video, 3D-modeller, logoer, finish-prøver. Verifisert mot `Altacom/public/`-katalog 2026-06-03.

---

## 1. Status (TL;DR)

Multibord har **et rikt asset-bibliotek allerede produsert:**

- ✅ **Hero-video:** `Herovideo.mp4` finnes (1 av 2 — den andre er test-variant)
- ✅ **Per-produkt galleri:** 4-9 ferdige bilder per modell (10 av 11 modeller)
- ✅ **3D-modeller (GLB):** 7 produkter har Blender-baked modeller
- ✅ **Finish-prøver:** 7 baser (M-koder) + 4 topper (N-koder)
- ✅ **Logo-sett:** SVG primær + PNG-fallback + Altacom-merke + Compact Living-merke
- ✅ **Showroom-bilde:** night-shot av Bygdøy Allé 69E
- ✅ **Katalog-cover** (kan brukes for Lead Magnet)
- ⚠️ **Ciak (kampanje):** kun 2 bilder — trenger flere
- ⚠️ **OG-bilder per produkt:** mangler (må produseres)
- ⚠️ **Apple-touch-icon + favicon-32:** verifiser

---

## 2. Hero-video (Visual Signature)

### eksisterende_filer
- `/public/videos/Herovideo.mp4` — primær hero-video
- `/public/videos/hero-compact-test.mp4` — test-variant (kan slettes eller beholdes som backup)

### specs (matchet til 1-PROFIL § 2)
- 3-sek loop, mp4 + webm
- Desktop: 1920×1080, Mobile: 1080×1350 (4:5)
- Bordet i interiør-kontekst, ikke studio-isolated
- Lyd: ingen (autoplay-vennlig)
- Poster-fallback for `prefers-reduced-motion`

### todo_hero
- Verifisere at Herovideo.mp4 viser transformasjon (sofabord ↔ spisebord) per Visual Signature
- Hvis ikke: produsere ny 3-sek loop
- Optimalisere: ≤500KB komprimert, mp4 + webm formater
- Lage poster-fallback (statisk frame)

---

## 3. Produktbilder

> Per-modell-mapper i `/public/images/products/<modell>/`. Format: `hero.jpeg` + `gallery-N.jpeg` + `dimensions.png/jpg`.

| Modell | Hero | Gallery-bilder | Dimensions | OG-bilde | Status |
|---|---|---|---|---|---|
| Amelie | ✅ | 4 | ✅ (png+jpg) | ❌ | Komplett produkt-galleri |
| Ares Fold | ✅ | (sjekk) | ✅ | ❌ | Sannsynligvis komplett |
| Bessy | ✅ | (sjekk) | ✅ | ❌ | — |
| Calypso | ✅ | (sjekk) | ✅ | ❌ | — |
| Geniale | ✅ | (sjekk) | ✅ | ❌ | — |
| Gingillo | ✅ | (sjekk) | ✅ | ❌ | — |
| Helios | ✅ | (sjekk) | ✅ | ❌ | — |
| Lotus | ✅ | (sjekk) | ✅ | ❌ | — |
| Ulisse | ✅ | 8 | ✅ | ❌ | Mest rikt galleri |
| Universe | ✅ | (sjekk) | ✅ | ❌ | — |
| Ciak | ⚠️ 2 | 0 | ❌ | ❌ | **Trenger flere bilder** |

### specs
- Format: jpeg (eksisterende), bør konverteres til webp
- Hero maks: 500KB. Gallery maks: 300KB.
- Lazy-load alle utenfor viewport
- Lightbox med produkt-detaljer

### hero-mappe (separat)
- `/public/images/hero/`: geniale-1.jpg, geniale-2.jpg, geniale-3.jpg, geniale-4.jpg
- `/public/images/hero/lcp/`: LCP-optimaliserte varianter for Lighthouse

### 3d-renders-mappe
- `/public/images/products/3d-renders/`: renders fra Blender (kan brukes som backup-hero eller AI-genererte miljøbilder)

---

## 4. 3D-modeller (GLB / Blender-baked)

> `/public/models/`. Format: `.glb` med både splittede og samlede versjoner. **Stor mulighet for interaktiv produkt-visualisering.**

| Modell | GLB-filer |
|---|---|
| Amelie | amelie-basso-split.glb |
| Ares Fold | ares-fold-basso-split.glb |
| Calypso | calypso-basso-split.glb |
| Geniale | geniale-ai-split.glb, geniale-ai.glb |
| Helios | helios-basso-split.glb |
| Ulisse | ulisse-alto-aperto-split.glb, ulisse-alto-chiuso-split.glb, ulisse-basso-split.glb |
| Tavolino Compact | flere varianter (alto-aperto/chiuso, basso, split) |

### bruksområder_3d
- **Interaktiv "trinnløs"-visualisering** — bruker drar slider, ser bordet bevege seg
- **AR-funksjon** — vis bordet i kundens rom via iPhone/Android (`<model-viewer>` web-komponent)
- **Konfigurator** — kunden kombinerer finish + base + top live
- **AI-trafikk-bonus:** 3D-viewer = AI-svar-snippets om "transformerbare bord" siterer oss
- **Markedsføring:** AI-genererte miljøbilder via Nano Banana 2 (allerede i stacken) + 3D-render

### mangler_3d
- Bessy, Gingillo, Lotus, Universe, Ciak (4-5 modeller mangler GLB)

### todo_3d
- Bygge interaktiv 3D-viewer (model-viewer / Three.js)
- Implementere AR-mode (model-viewer støtter dette)
- Produsere GLB for manglende modeller (Bessy, Gingillo, Lotus, Universe, Ciak)
- Konfigurator: bytt finish/base live (Three.js material swap)

---

## 5. Finish-bilder (materialprøver)

> `/public/images/finishes/`.

### baser (M-koder, 7 totalt — verifisert)
- M04 Matt sort
- M11 Grafitt
- M24 Hvit
- M25 Kobber
- M27 Mint
- M32 Sand
- M51 Gull

### topper (N-koder, 4 verifisert + 2 i KUNNSKAPSBASE)
Funnet i `/public/images/finishes/tops/`:
- N20 Bianco
- N35 Rovere nodato
- N43 Sherwood
- N47 *(verifiser hva dette er)*

Fra KUNNSKAPSBASE (kanskje ikke i public/ ennå):
- N24 Cemento
- N40 Noce antico
- N42 Rovere vecchio

### todo_finishes
- Verifisere at alle 6+ topp-finishes har bilder
- Lage hover/swatch-komponent som viser finish-bilde + navn
- Premium finishes (Glass, Malta, Ceramica) trenger også prøvebilder

---

## 6. Logo-sett

| Fil | Format | Bruk |
|---|---|---|
| `/public/images/altacom-logo.svg` | SVG | Primær Altacom-merke (leverandør) |
| `/public/images/altacom-logo-white.svg` | SVG | Mørk bakgrunn-variant |
| `/public/images/logo2.png` | PNG | Multibord-wordmark |
| `/public/images/logo2-transparent.png` | PNG | Transparent versjon |
| `/public/images/logocompact.png` | PNG | Compact Living-logo (hovedmerke) |
| `/public/images/logocompact-transparent.png` | PNG | Compact Living transparent |
| `/public/favicon.ico` | ICO | Browser-favicon |

### todo_logo
- Lage SVG-versjon av Multibord-wordmark (nå bare PNG) for crisp på alle skjermer
- Lage `apple-touch-icon.png` (180x180) hvis mangler
- Lage `favicon-32.png` + `favicon-16.png`
- Verifisere at OG-bilder for sosiale plattformer eksisterer

---

## 7. Showroom-bilder

| Fil | Bruk |
|---|---|
| `/public/images/Compactlivingstorenightoutside.jpeg` | Night-shot eksteriør Bygdøy Allé 69E |
| `/public/images/catalog-cover.jpeg` | Katalog-cover (kan brukes for Lead Magnet PDF-omslag) |

### todo_showroom
- Produsere flere showroom-bilder: interiør med bord-displays, kunde-besøk, team
- Tas i dagslys + kveldslys for variasjon
- 5-10 bilder for GBP-feed
- Bilder for "Om oss"-side på multibord.no

---

## 8. OG-bilder (Open Graph for social/SEO)

> **Mangler i stor grad. Må produseres.**

### specs
- Dimensjon: 1200×630 px
- Format: jpg eller webp
- Maks-størrelse: 300KB

### filer_som_trengs
- `og-default.jpg` — forside, bordet i interiør-kontekst
- `og-product-<modell>.jpg` × 11 — per produkt
- `og-showroom.jpg` — showroom-fokus
- `og-blog-default.jpg` — fallback for blogginnlegg uten egen image
- `og-pillar-<topic>.jpg` × 4 — per content-pillar (se 5-SEO § 3)

### todo_og
- Lage `og-default.jpg` med hero-video-poster + Multibord-logo + tagline
- Generere per-produkt-OG-bilder fra produktbilder
- Bruk Nano Banana 2 for blogg-OG-bilder

---

## 9. Bildeformat og standardisering

### prioritet_for_konvertering
1. **WebP** for alle photos (smaller filer, support 96%+ browsere)
2. **AVIF** for hero-bilder (enda mindre, support 90%+ — fallback til WebP)
3. **SVG** for logo + ikoner

### maksstørrelser (matchet til system TECH-STANDARDS)
- Hero: ≤500KB
- Gallery-bilder: ≤300KB
- Cards/thumbnails: ≤200KB
- OG-images: ≤300KB
- Favicon: ≤10KB

### responsive_strategi
- `<picture>` med srcset for mobile/tablet/desktop varianter
- `next/image` (Next.js) håndterer det automatisk

---

## 10. Bilde-attribution / lisens

- **Alle produkt-bilder:** levert av Altacom Italia eller fotografert av Multibord
- **Stock-bilder:** IKKE i bruk (kundebilder + showroom prioriteres)
- **Showroom-bilder:** tas av Multibord / Compact Living-teamet
- **AI-genererte miljøbilder:** Nano Banana 2 (når brukt for blogg)

---

## 11. Plausible-tracking på asset-load

- Hero-video har egen Plausible-event ved play
- Lightbox-åpning: tracket
- 3D-viewer-interaksjon: tracket (når implementert)
- AR-mode-aktivering: tracket (når implementert)

---

## TODO (prioritert)

### Høy prioritet
- Verifisere Herovideo.mp4 (er det transformasjons-loop?)
- Lage OG-images (forsiden + per produkt + showroom)
- Konvertere alle jpegs til webp
- Lage poster-fallback for hero-video
- Produsere flere bilder av Ciak (kun 2 nå)

### Middels prioritet
- Bygge 3D-viewer-komponent med model-viewer
- Lage SVG-versjon av Multibord-wordmark
- Apple-touch-icon + favicon-32 hvis mangler
- Flere showroom-bilder (5-10 for GBP)

### Lav prioritet
- GLB for Bessy, Gingillo, Lotus, Universe, Ciak
- Finish-hover-komponent
- AR-mode-implementering
- AI-genererte miljøbilder via Nano Banana 2 for blogg

---

## NOTES

Multibord har **vesentlig rikere asset-bibliotek enn antatt** — hero-video og 3D-modeller eksisterer allerede. Discovery ga oss ekte data: vi bygger PÅ eksisterende, ikke fra null. Det reduserer produksjonskost dramatisk og lar oss prioritere det som mangler (OG-images, Ciak-bilder, webp-konvertering). 3D-modeller + AR er stor mulighet ingen norsk konkurrent har implementert.
