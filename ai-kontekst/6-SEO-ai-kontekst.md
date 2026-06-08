---
type: ai-kontekst
section: seo
tenant_slug: multibord
last_updated: 2026-06-03
---

# SEO — AI-kontekst (Multibord)

Strategi-rationale og AI-instrukser for SEO. Kunden ser ikke dette, men AI trenger det for å forstå hvorfor strategien er som den er og hvordan AI-trafikk skal optimaliseres over tid.

---

## 1. Hvorfor denne strategien fungerer

Lav konkurranse i norsk premium-kategori for "transformerbare bord" / "sofa- og spisebord-i-ett" gjør at Multibord kan vinne raskt med rett strategi. Tier 1-søkeordene er transaksjonelle med LAV konkurranse — dette er sjeldent og må utnyttes før konkurrenter våkner.

Strategien er bygd på faktisk data fra brand-fila (voice → headlines), bedrift-fila (identitet → LocalBusiness JSON-LD), FAQ-fila (long-tail søkeord + FAQPage schema), og markedsanalyse (konkurrenter + personas → søkeord-prioritering).

---

## 2. Volum-tall — usikkerhet og verifisering

Volum-tall i søkeord-tabellene er estimater basert på autocomplete + bransje-erfaring. Må verifiseres med Google Search Console når data er tilgjengelig (etter site har vært live noen uker). Strategi-beslutninger er solide uten eksakte tall fordi konkurranse-nivåer er kjente.

Når Search Console-data kommer (~6-12 uker etter live):
1. Verifiser at Tier 1-søkeordene faktisk har søkevolum
2. Re-prioriter Tier 2 basert på reell impressions
3. Identifiser ukjente long-tail-vinnere (søkeord vi ikke planla men ranker på)

---

## 3. AI-trafikk-strategi (hvorfor)

Når Claude/GPT/Perplexity skriver svar om "transformerbare bord Norge", vil de sitere kilder som er strukturerte, faktabaserte og verifierbare. Multibord MÅ være siterbart.

**Hvorfor dette er kritisk fra 2025+:**
- AI-svar tar trafikk vekk fra Google klassisk søk
- Sitering i AI-svar = brand-eksponering selv uten klikk
- AI elsker å sitere kilder som selv siterer kilder

**Hvordan vi skriver for AI-citering:**
- Tall og fakta tydelig markert
- Direkte påstander med kilde-autoritet (Altacom Italia, org.nr)
- FAQ-format som matcher AI-snippet-mønster
- Strukturert data (JSON-LD) overalt slik at AI lett kan parse

**Hvorfor llms.txt + ai.txt:**
- Vi signaliserer eksplisitt at AI får sitere oss
- Vi gir AI en kortfattet kilde å bygge svar på
- Lite oppside hvis det ikke virker, men gratis å implementere

---

## 4. Pillar-strategi — rationale

**Hvorfor 4 pillars, ikke flere:**
- For mange pillars = ingen får dybde
- 4 stk dekker hele kjøps-funnel: informasjon (heve-senk-guide), problem (liten leilighet), verdi (italiensk håndverk), trust (showroom-test)

**Hvorfor showroom-test som egen pillar:**
- Differensiator mot rene nettbutikker
- Lokal-SEO signal (Oslo)
- Trust-bygging (du kan teste FØR du kjøper)
- Direkte mot konkurrenters svakhet (nett-only uten fysisk tilstedeværelse)

**Hvorfor italiensk-håndverk som egen pillar:**
- Premium-posisjonering
- Kilde-autoritet (Altacom Italia)
- Differensiator mot masseproduserte konkurrenter
- Støtter høyere prispunkt

---

## 5. Lokal SEO — rationale

**Hvorfor Bygdøy/Frogner-fokus:**
- Showroom-adresse = Bygdøy Allé 69E
- Premium-område matcher prispunkt
- Lite konkurranse på "møbel showroom bygdøy"

**Hvorfor ikke aggressiv Bergen/Stavanger/Trondheim ennå:**
- Vi har ikke fysisk tilstedeværelse der
- Falske lokal-landinger skader trust
- Aktiveres når Showroom #2 åpner

---

## 6. Anmeldelses-strategi — rationale

Mål 4.8+ snitt, 50+ totalt innen Q4 2026.

**Hvorfor 4.8 og ikke 5.0:**
- 5.0 ser kjøpt ut
- 4.8 = "premium med menneskelig variasjon"
- Google Bedriftsprofil-algoritmen favoriserer 4.5-4.9-range

**Hvorfor 2 uker etter levering:**
- Kunden har rukket å bruke bordet
- Wow-faktoren er fortsatt fersk
- Ikke for sent at minnet er gått tapt

---

## 7. Sjekkliste fremover

- Sett opp llms.txt + ai.txt på multibord.no
- Implementere Product JSON-LD på alle 11 produktsider
- Sett opp Google Bedriftsprofil Q&A med 10 seed-spørsmål fra FAQ
- Aktivere innholdsmaskin med juli-pillar-plan
- Verifisere søkeord-volumer via Search Console når data er tilgjengelig
