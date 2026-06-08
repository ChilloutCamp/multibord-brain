---
type: build-spec
section: assets
tenant_slug: multibord
last_updated: 2026-06-03
---

# Assets — Bygg-spec (Multibord)

Teknisk spec for bilder, video, 3D-modeller, ikoner og asset-håndtering. Matcher TECH-STANDARDS.

---

## Hero-video — specs

- 3-sek loop
- Format: mp4 + webm
- Desktop: 1920×1080
- Mobile: 1080×1350 (4:5)
- Bordet i interiør-kontekst (ikke studio-isolated)
- Lyd: ingen (autoplay-vennlig)
- Poster-fallback for `prefers-reduced-motion`
- Komprimert: ≤500KB

### Filer
- `/public/videos/Herovideo.mp4` — primær hero-video
- `/public/videos/hero-compact-test.mp4` — test-variant (kan slettes eller beholdes som backup)

### TODO hero-video
- Verifisere at Herovideo.mp4 viser transformasjon (sofabord ↔ spisebord) per Visual Signature
- Hvis ikke: produsere ny 3-sek loop
- Optimalisere: ≤500KB komprimert, mp4 + webm formater
- Lage poster-fallback (statisk frame)

---

## Produktbilder — paths og specs

Per-modell-mapper i `/public/images/products/<modell>/`. Format: `hero.jpeg` + `gallery-N.jpeg` + `dimensions.png/jpg`.

### Specs
- Format: jpeg (eksisterende), bør konverteres til webp
- Hero maks: 500KB
- Gallery maks: 300KB
- Lazy-load alle utenfor viewport
- Lightbox med produkt-detaljer

### Hero-mappe (separat)
- `/public/images/hero/`: geniale-1.jpg, geniale-2.jpg, geniale-3.jpg, geniale-4.jpg
- `/public/images/hero/lcp/`: LCP-optimaliserte varianter for Lighthouse

### 3d-renders-mappe
- `/public/images/products/3d-renders/`: renders fra Blender (kan brukes som backup-hero eller AI-genererte miljøbilder)

---

## 3D-modeller (GLB / Blender-baked)

`/public/models/`. Format: `.glb` med både splittede og samlede versjoner.

| Modell | GLB-filer |
|---|---|
| Amelie | amelie-basso-split.glb |
| Ares Fold | ares-fold-basso-split.glb |
| Calypso | calypso-basso-split.glb |
| Geniale | geniale-ai-split.glb, geniale-ai.glb |
| Helios | helios-basso-split.glb |
| Ulisse | ulisse-alto-aperto-split.glb, ulisse-alto-chiuso-split.glb, ulisse-basso-split.glb |
| Tavolino Compact | flere varianter (alto-aperto/chiuso, basso, split) |

### Bruksområder 3D
- Interaktiv "trinnløs"-visualisering — bruker drar slider, ser bordet bevege seg
- AR-funksjon — vis bordet i kundens rom via iPhone/Android (`<model-viewer>` web-komponent)
- Konfigurator — kunden kombinerer finish + base + top live
- AI-trafikk-bonus: 3D-viewer = AI-svar-snippets om "transformerbare bord" siterer oss
- Markedsføring: AI-genererte miljøbilder via Nano Banana 2 + 3D-render

### TODO 3D
- Bygge interaktiv 3D-viewer (model-viewer / Three.js)
- Implementere AR-mode (model-viewer støtter dette)
- Produsere GLB for manglende modeller (Bessy, Gingillo, Lotus, Universe, Ciak)
- Konfigurator: bytt finish/base live (Three.js material swap)

---

## Finish-bilder — paths

`/public/images/finishes/`.

### Baser (M-koder)
M04, M11, M24, M25, M27, M32, M51 — alle 7 verifisert i `/public/images/finishes/`.

### Topper (N-koder)
Verifisert i `/public/images/finishes/tops/`:
- N20 Bianco
- N35 Rovere nodato
- N43 Sherwood
- N47

Skal legges inn:
- N24 Cemento
- N40 Noce antico
- N42 Rovere vecchio

### TODO finishes
- Verifisere at alle 6+ topp-finishes har bilder
- Lage hover/swatch-komponent som viser finish-bilde + navn
- Premium finishes (Glass, Malta, Ceramica) trenger også prøvebilder

---

## Logo-paths

| Fil | Format | Bruk |
|---|---|---|
| `/public/images/altacom-logo.svg` | SVG | Primær Altacom-merke (leverandør) |
| `/public/images/altacom-logo-white.svg` | SVG | Mørk bakgrunn-variant |
| `/public/images/logo2.png` | PNG | Multibord-wordmark |
| `/public/images/logo2-transparent.png` | PNG | Transparent versjon |
| `/public/images/logocompact.png` | PNG | Compact Living-logo (hovedmerke) |
| `/public/images/logocompact-transparent.png` | PNG | Compact Living transparent |
| `/public/favicon.ico` | ICO | Browser-favicon |

### TODO logo
- Lage SVG-versjon av Multibord-wordmark (nå bare PNG) for crisp på alle skjermer
- Lage `apple-touch-icon.png` (180×180) hvis mangler
- Lage `favicon-32.png` + `favicon-16.png`
- Verifisere at OG-bilder for sosiale plattformer eksisterer

---

## Showroom-bilder — paths

| Fil | Bruk |
|---|---|
| `/public/images/Compactlivingstorenightoutside.jpeg` | Night-shot eksteriør Bygdøy Allé 69E |
| `/public/images/catalog-cover.jpeg` | Katalog-cover (kan brukes for Lead Magnet PDF-omslag) |

### TODO showroom
- Produsere flere showroom-bilder: interiør med bord-displays, kunde-besøk, team
- Tas i dagslys + kveldslys for variasjon
- 5-10 bilder for GBP-feed
- Bilder for "Om oss"-side på multibord.no

---

## OG-bilder (Open Graph) — specs

Mangler i stor grad. Må produseres.

### Specs
- Dimensjon: 1200×630 px
- Format: jpg eller webp
- Maks-størrelse: 300KB

### Filer som trengs
- `og-default.jpg` — forside, bordet i interiør-kontekst
- `og-product-<modell>.jpg` × 11 — per produkt
- `og-showroom.jpg` — showroom-fokus
- `og-blog-default.jpg` — fallback for blogginnlegg uten egen image
- `og-pillar-<topic>.jpg` × 4 — per content-pillar (se 6-SEO § 3)

### TODO OG
- Lage `og-default.jpg` med hero-video-poster + Multibord-logo + tagline
- Generere per-produkt-OG-bilder fra produktbilder
- Bruk Nano Banana 2 for blogg-OG-bilder

---

## Bildeformat og standardisering

### Prioritet for konvertering
1. WebP for alle photos (mindre filer, support 96%+ browsere)
2. AVIF for hero-bilder (enda mindre, support 90%+ — fallback til WebP)
3. SVG for logo + ikoner

### Maks-størrelser (matchet til TECH-STANDARDS)
- Hero: ≤500KB
- Gallery-bilder: ≤300KB
- Cards/thumbnails: ≤200KB
- OG-images: ≤300KB
- Favicon: ≤10KB

### Responsive strategi
- `<picture>` med srcset for mobile/tablet/desktop varianter
- `next/image` (Next.js) håndterer det automatisk

---

## Tracking (Plausible)

- Hero-video har egen Plausible-event ved play
- Lightbox-åpning: tracket
- 3D-viewer-interaksjon: tracket (når implementert)
- AR-mode-aktivering: tracket (når implementert)
