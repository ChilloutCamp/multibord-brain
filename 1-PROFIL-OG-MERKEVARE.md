---
type: bedrift-data
section: profil-og-merkevare
tenant_slug: multibord
syncs_to_brain: brand (palett/fonts), identity (usp/positioning), visual_signature
last_updated: 2026-06-05
fill_order: 1
ui_section: "Profil og merkevare"
---

# Profil og merkevare — Multibord

> **Selvstendig om:** Brand-identitet (palett, fonts, logo, Visual Signature, USP, posisjonering).
>
> **System v3.3:** Voice + målgrupper (personas) flyttet til `3-STEMME-OG-MALGRUPPER.md` som egen seksjon.

---

## 1. USP og posisjonering

### usp_short (faktisk på multibord.no)
"Sofa- og spisebord . alt i ett" (H1) — "Et bord som gir alt" (tagline) — "Inviter gjester til middag, i stor eller liten leilighet" (subheading)

### usp_long_form
Multibord er én ting: bord som er sofabord OG spisebord i én. Trinnløs gassløft, italiensk fabrikkmontert, test alle 11 modeller på Bygdøy Allé Oslo før du kjøper.

### usp_proof
- **Alt-i-ett-funksjon:** Sofabord OG spisebord i samme produkt — ikke kompromiss
- **11 modeller å teste:** Bygdøy Allé 69E Oslo, Man-Fre 11-17 / Lør 11-16
- **Italiensk produksjon:** Altacom Italia — sekundær fordel, ikke hovedvinkling
- **2 års garanti** + 14 dagers angrerett
- **Gratis frakt Oslo, fra 990 kr nasjonalt**

### usp_emotional_payoff
"Endelig kan jeg ha både sofabord og spisebord — i samme leilighet, samme bord. Inviter gjester til middag uten å rydde først." Følelse: praktisk frihet + sikkerhet (testet i showroom).

### positioning_short
**Kategori-spesialist på sofa-/spisebord-i-ett**. Lokal Oslo-showroom + nasjonal levering. Mellom Bolia/BoConcept (generelt premium) og Resource Furniture (ultra-premium internasjonal).

---

## 2. Visual Signature

### chosen_signature
**Transformasjon-i-aksjon-hero** — video-loop som viser bordet bevege seg fra sofabord-høyde til spisebord-høyde.

### why_this_signature
1. Produkt ER handling — statisk bilde kommuniserer ikke verdien
2. Resource Furniture (nærmeste konkurrent) gjør ikke dette med video
3. AI-Overview-bonus: vi blir sitert som "siden som demonstrerer transformasjonen"
4. Mobile-vennlig: 3-sek loop, ≤500KB komprimert

### eksisterende_assets
**Herovideo.mp4 finnes allerede** i `/public/videos/`. Verifiser at den viser transformasjon (sannsynligvis ja, basert på marketing-analyse mars 2026 som anbefalte dette).

### implementation_specs
- 3-sek loop, mp4 + webm
- Desktop: 1920×1080, Mobile: 1080×1350 (4:5)
- Bordet i interiør-kontekst (ikke studio-isolated)
- Lyd: ingen (autoplay-vennlig)
- Poster-fallback for prefers-reduced-motion

### secondary_signature
**Editorial italiensk magazine-typografi** som overlay (Fraunces display-serif H1/H2).

---

## 3. Anti-konkurrent (hva vi gjør motsatt av)

- **BoConcept gjør:** generell premium møbelhandel → **Vi:** spesialist på transformerbare bord
- **IKEA gjør:** plassbesparende billig → **Vi:** premium italiensk håndverk, varig
- **Resource Furniture gjør:** internasjonal, online-fokusert → **Vi:** norsk showroom-først
- **Calligaris gjør:** italiensk premium uten lokal tilstedeværelse → **Vi:** italiensk DNA + norsk showroom

---

## 4. Visuell identitet — farger

### palette_philosophy
Italiensk premium med norsk varme. Ikke kald-svart eller cold-grafisk. Kobber + sort + krem gir håndverker-følelse + premium-vekt + lyse pust.

### colors
- **Primary:** Sort #1A1A1A (dyp grafitt — premium-vekt)
- **Secondary:** Kobber #B87333 (varm aksent, italiensk håndverk)
- **Accent:** Logo-oransje #E8A52F (Altacom Italia offisiell — CTA der det skal merkes)

### backgrounds
- Hero: Sort/grafitt eller fullbleed video-loop
- Cards: Hvit #FFFFFF eller varm krem #F4F0E8
- Sekundære seksjoner: Krem #F4F0E8
- Mørke kontrast-seksjoner: Sort #1A1A1A

### text_colors
- text_primary: #1A1A1A på lys, #F4F0E8 på mørk
- text_secondary: #4A4A4A
- text_muted: #8A8A8A

### color_distinctness
Konkurrenter:
- BoConcept: dempet grafisk, ikke kobber
- Bolia: hvit + sort + grønne aksenter
- Resource Furniture: brunt + hvit
- **Vi: kobber + sort + krem** — distinkt nordisk-italiensk

### contrast
WCAG AA 4.5:1 sjekket for tekst. Knapper passerer 3:1.

---

## 5. Typografi

### body_font
**Inter** (variable, vekt 400-600) — varm grotesk, god lesbarhet, gratis via Google Fonts.

### heading_font
**Fraunces** (display-serif, vekt 500-700) — italiensk-feeling display, gratis Google Fonts. Bryter med "Inter-overalt"-cliché.

Alternativer: Cormorant, Playfair Display (begge gratis Google).

### type_scale
- H1 desktop: 60-80px / mobile: 36-48px
- H2: 40-56 / 28-32px
- H3: 24-32 / 20-24px
- Body: 16-18px line-height 1.5-1.7
- Eyebrow: 12-14px tracking 0.1em

### type_personality
Editorial, varmt, italiensk, presist, premium

---

## 6. Layout og avstand

- Container max-width: 1280px
- Desktop padding: 32px / Mobile: 20px
- Section gap desktop: 96-128px / Mobile: 64-80px

### border_radius_strategy
Subtile 4-8px for premium-feel. **Ikke** `rounded-2xl` (cliché).
- Knapper: 6px / Kort: 8px / Bilder: 4px / Input: 6px

---

## 7. Logo

### logo_files
- `/public/images/logo2.png` (Multibord-wordmark — primær)
- `/public/images/logo2-transparent.png` (transparent versjon)
- `/public/images/altacom-logo.svg` (sekundær — vises som leverandør i footer/about)
- `/public/images/altacom-logo-white.svg` (mørk bakgrunn-variant)
- `/public/images/logocompact.png` + `/public/images/logocompact-transparent.png` (Compact Living-logo, hovedmerke)
- `/public/favicon.ico`

### logo_color
#E8A52F (Altacom oransje)

### todo_logo
- Lage SVG-versjon av Multibord-wordmark (nå bare PNG) for crisp på alle skjermer
- apple-touch-icon.png (180x180) + favicon-32.png hvis ikke finnes

---

## 8. Reference sites

| URL | Hva vi tar med | Hva vi ikke tar med |
|---|---|---|
| resourcefurniture.com | Rikt produkt-storytelling, "rooms" before/after | Deres farger, og statisk hero |
| cassina.com | Italiensk premium-følelse, editorial typografi | For tungt for mid-premium-posisjon |
| native.no | Editorial blogg-layout (allerede i innholdsmaskin) | Matt grafisk-stil — vi er varmere |

### visual_style
editorial, varmt, italiensk-håndverk-vibrant, premium-uten-å-skryte, funksjonelt

### overall_feel
"Du går inn i et italiensk møbel-magasin, ikke en nettbutikk. Bordene transformeres foran deg. Du føler kvalitet uten å bli overveldet."

---

## 9. Imagery Direction

### imagery_priority
1. **Kundebilder** (eksisterer: 4-9 per produkt i `/public/images/products/`)
2. **Showroom-bilder** (eksisterer: `Compactlivingstorenightoutside.jpeg`)
3. **Transformasjon-video/loop** (eksisterer: `Herovideo.mp4`)
4. **3D-modeller** (eksisterer: GLB for 7 produkter i `/public/models/`)
5. (siste utvei) AI-genererte mood-bilder

### photography_style
- Naturlig lys
- Ekte rom, ikke studio-only
- Bordet i kontekst (rommet vises rundt)
- Italiensk-eleganse-feeling
- Unngå: smiling-stock-people, AI-genererte ansikter, klisjé "tom hvit bakgrunn"

---

## 10. Interaction & Motion Identity

### ambition_level
Premium moderne — signatureffekter, smooth scroll, ikke over-the-top

### signature_effects
1. Transformasjon-video-hero (se § 2)
2. Smooth scroll (Lenis)
3. Subtile produkt-card-hover (lift + skygge)

### hover_behavior
- Knapper: subtile scale + farge-shift
- Kort: lift (subtle shadow + 2px transform)
- Lenker i tekst: underline-draw
- Bilder: zoom 1.05x i 700ms

### scroll_behavior
- Smooth scroll via Lenis
- Seksjoner: subtle fade-up
- Hero: parallax på bilde (kun hvis poster-fallback)

### reduced_motion_strategy
- prefers-reduced-motion respekteres
- ScrollReveal vises umiddelbart
- Video-hero → statisk poster
- Parallax av

---

## 11. Stemme og målgrupper

> **Flyttet til `3-STEMME-OG-MALGRUPPER.md`** (system v3.3 — egen seksjon for voice + personas).

---

## 12. Anti-pattern-tabell

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

## 13. Genericity-check (etter første build)

- [ ] Hero er ikke "fullbleed bilde + h1 + sub + 2 CTA" — det ER video-transformasjon
- [ ] Visual Signature er konkret implementert (video lever, lazy-loadet)
- [ ] Minst 2 seksjoner har layout som ikke finnes i andre prosjekter
- [ ] Palett er distinkt (kobber/sort/krem implementert)
- [ ] Typografi har personlighet (Fraunces synlig på H1/H2)

---

## TODO

- Implementere Fraunces + Inter i siden (next/font/google)
- Verifisere Herovideo.mp4 viser transformasjon (eller produsere ny)
- Playwright-screenshots av reference sites (resourcefurniture, cassina, native)
- Lage SVG-versjon av Multibord-wordmark

---

## NOTES

Brand-profil bygger på faktisk site-voice (verifisert via WebFetch multibord.no juni 2026). Det skiller seg fra eldre kilder (KUNNSKAPSBASE + Marketing-analyse fra mars 2026) som vektla "italiensk håndverk"-vinkling. Den nye voicen er minimalistisk skandinavisk + benefit-driven — vi følger live-versjon, ikke arkiv.
