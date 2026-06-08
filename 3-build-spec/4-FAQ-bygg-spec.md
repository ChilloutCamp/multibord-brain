---
type: build-spec
section: faq
tenant_slug: multibord
last_updated: 2026-06-03
---

# FAQ — Bygg-spec

Teknisk instruks for å bygge FAQ-side og SEO-implementering på multibord.no.

---

## JSON-LD FAQPage schema

Alle spørsmål-svar i `4-FAQ.md` genereres automatisk som JSON-LD `FAQPage` schema på nettsiden for bedre Google-synlighet og AI-sitering.

- Schema-implementering: se `5-SEO.md` § 5
- Generer schema fra alle FAQ-spørsmål i seksjon 1-9
- Inkluder hvert spørsmål som `Question`-node med `acceptedAnswer` av type `Answer`

---

## Krysshenvisninger til andre filer

- Full modell-sammenligning: `6-PRODUKTER.md` eller `6-produkter/per-produkt/`-mappa
- Full prisliste: `6-produkter/14-priser-komplett.md`
- Garanti- og legal-detaljer: `9-LEGAL.md`
