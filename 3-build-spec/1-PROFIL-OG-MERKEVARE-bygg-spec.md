---
type: build-spec
section: profil-og-merkevare
tenant_slug: multibord
last_updated: 2026-06-05
---

# Profil og merkevare — bygg-spec (Multibord)

Teknisk bygg-instruks for design-system, layout, motion og assets. Brukes av AI som bygger nettsiden.

---

## 1. Visual Signature — implementasjonsspec

### Hero-video (hovedsignatur)
- Type: 3-sek loop, mp4 + webm
- Desktop oppløsning: 1920×1080
- Mobile oppløsning: 1080×1350 (4:5)
- Komposisjon: bordet i interiør-kontekst (ikke studio-isolated)
- Lyd: ingen (autoplay-vennlig)
- Poster-fallback for `prefers-reduced-motion`
- Filstørrelse: ≤500KB komprimert
- Filsti: `/public/videos/Herovideo.mp4`

### Sekundær signatur
Editorial italiensk magazine-typografi som overlay. Fraunces display-serif på H1/H2.

---

## 2. Farger — kontrast og bruk

WCAG AA 4.5:1 sjekket for tekst. Knapper passerer 3:1.

| Token | Hex | Bruk |
|---|---|---|
| primary | #1A1A1A | Dyp grafitt, premium-vekt |
| secondary | #B87333 | Kobber, varm aksent |
| accent | #E8A52F | Altacom oransje, CTA-merking |
| bg-light | #FFFFFF | Cards lys |
| bg-cream | #F4F0E8 | Sekundære seksjoner |
| bg-dark | #1A1A1A | Mørke kontrast-seksjoner |
| text-primary-light | #1A1A1A | Tekst på lys bg |
| text-primary-dark | #F4F0E8 | Tekst på mørk bg |
| text-secondary | #4A4A4A | Sekundær tekst |
| text-muted | #8A8A8A | Dempet tekst |

---

## 3. Typografi — implementasjon

### Fonter
- Brødtekst: **Inter** (variable, vekt 400-600) — via `next/font/google`
- Overskrifter: **Fraunces** (display-serif, vekt 500-700) — via `next/font/google`

### Type-skala
| Element | Desktop | Mobile |
|---|---|---|
| H1 | 60-80px | 36-48px |
| H2 | 40-56px | 28-32px |
| H3 | 24-32px | 20-24px |
| Body | 16-18px (line-height 1.5-1.7) | 16-18px |
| Eyebrow | 12-14px (tracking 0.1em) | 12-14px |

---

## 4. Layout og avstand

- Container max-width: 1280px
- Desktop padding: 32px
- Mobile padding: 20px
- Section gap desktop: 96-128px
- Section gap mobile: 64-80px

### Border-radius-strategi
Subtile 4-8px for premium-feel. **Ikke** `rounded-2xl` (cliché).

| Element | Radius |
|---|---|
| Knapper | 6px |
| Kort | 8px |
| Bilder | 4px |
| Input | 6px |

---

## 5. Logo — filer og bruk

### Filer
- `/public/images/logo2.png` — Multibord-wordmark (primær)
- `/public/images/logo2-transparent.png` — transparent versjon
- `/public/images/altacom-logo.svg` — sekundær, leverandør i footer/about
- `/public/images/altacom-logo-white.svg` — mørk bakgrunn-variant
- `/public/images/logocompact.png` + `/public/images/logocompact-transparent.png` — Compact Living-logo (hovedmerke)
- `/public/favicon.ico`

### Logo-farge
#E8A52F (Altacom oransje)

### TODO assets
- SVG-versjon av Multibord-wordmark (kun PNG i dag) for crisp på alle skjermer
- `apple-touch-icon.png` (180x180) hvis ikke finnes
- `favicon-32.png` hvis ikke finnes

---

## 6. Imagery Direction

### Prioritering av bildekilder
1. **Kundebilder** (eksisterer: 4-9 per produkt i `/public/images/products/`)
2. **Showroom-bilder** (eksisterer: `Compactlivingstorenightoutside.jpeg`)
3. **Transformasjon-video/loop** (eksisterer: `Herovideo.mp4`)
4. **3D-modeller** (eksisterer: GLB for 7 produkter i `/public/models/`)
5. (siste utvei) AI-genererte mood-bilder

### Foto-stil
- Naturlig lys
- Ekte rom, ikke studio-only
- Bordet i kontekst (rommet vises rundt)
- Italiensk-eleganse-feeling

### Unngå
- Smiling-stock-people
- AI-genererte ansikter
- Klisjé "tom hvit bakgrunn"

---

## 7. Interaction & Motion Identity

### Ambisjonsnivå
Premium moderne — signatureffekter, smooth scroll, ikke over-the-top.

### Signatureffekter
1. Transformasjon-video-hero (se § 1)
2. Smooth scroll (Lenis)
3. Subtile produkt-card-hover (lift + skygge)

### Hover-oppførsel
- Knapper: subtile scale + farge-shift
- Kort: lift (subtle shadow + 2px transform)
- Lenker i tekst: underline-draw
- Bilder: zoom 1.05x i 700ms

### Scroll-oppførsel
- Smooth scroll via Lenis
- Seksjoner: subtle fade-up
- Hero: parallax på bilde (kun hvis poster-fallback)

### Reduced motion-strategi
- `prefers-reduced-motion` respekteres
- ScrollReveal vises umiddelbart
- Video-hero → statisk poster
- Parallax av

---

## 8. Reference sites

| URL | Hva vi tar med | Hva vi ikke tar med |
|---|---|---|
| resourcefurniture.com | Rikt produkt-storytelling, "rooms" before/after | Deres farger og statiske hero |
| cassina.com | Italiensk premium-følelse, editorial typografi | For tungt for mid-premium-posisjon |
| native.no | Editorial blogg-layout (allerede i innholdsmaskin) | Matt grafisk-stil — vi er varmere |

---

## 9. Anti-pattern-tabell

| Mønster | JA/NEI | Begrunnelse |
|---|---|---|
| Bento grid 1+2 | NEI | 11 produkter — produktgrid bedre |
| Scroll-pin process | NEI | "Vår prosess i 3 steg" cliché |
| Infinite marquee | NEI | 1 leverandør (Altacom) — ingen logo-scroll |
| Mørk CTA-seksjon nederst | JA | Etablert, fungerer for kontakt-CTA |
| Text-reveal hero | NEI | Video-hero er Visual Signature |
| Magazine-stil gallery | JA | Passer italiensk premium |
| Fullbleed hero med gradient | NEI | Vi har video-hero, ikke gradient |
| Standard footer 4-col | JA | Greit for kontakt + showroom-info |
| Inter font som body | JA | Inter på body, Fraunces på H1-H2 |
| rounded-2xl på alle kort | NEI | 4-8px subtile radier |
| Sand/grafitt/krem palett | NEI | Multibord = kobber/sort/krem |
| Cookie consent dark pill | JA | Trygt standard-format |

---

## 10. Genericity-check (etter første build)

- [ ] Hero er ikke "fullbleed bilde + h1 + sub + 2 CTA" — det ER video-transformasjon
- [ ] Visual Signature er konkret implementert (video lever, lazy-loadet)
- [ ] Minst 2 seksjoner har layout som ikke finnes i andre prosjekter
- [ ] Palett er distinkt (kobber/sort/krem implementert)
- [ ] Typografi har personlighet (Fraunces synlig på H1/H2)
