# Kritisk granskning – CAP-IT-13, version 2.0

*7 november 2026 · Granskning av faktabokstext och YAML-modell. Intern redaktionell och teknisk granskning, inte en oberoende certifiering.*

## Samlad bedömning

Kapitlet har en god grund: det börjar i generation 2, skiljer på kvarvarande generationsarv och skalningsproblem, och rekommenderar inte nätverksprodukter som universallösningar. **Det bör behållas som kapitelunderlag efter revisionen**, men käll- och prioriteringsbedömningarna måste läsas som scenariobaserade arkitekturbedömningar, inte som absoluta krav.

## Kritiska iakttagelser och åtgärder

| Granskning | Risk i version 1 | Genomförd justering |
|---|---|---|
| Centralt plattformsbehov | YAML klassade flera gemensamma plattformstjänster som kritiska i G3/G4 även då en hanterad extern tjänst eller mindre lösning kan vara tillräcklig | Mjukat upp bedömningen för ingress, extern systemanslutning, fjärråtkomst, internet/edge och webb/API-skydd. Villkor gäller även DNS, plattformskonnektivitet och segmentering i G2. |
| Grundproblemet eller nästa generation? | Läsaren riskerade att se nätproblem som skäl att införa självbetjäning | Nytt diagnostiskt prov av normalfall, avveckling och blockerad anslutning; skiljer funktionsbrist från återkommande manuell flaskhals. |
| Spårbarhet | Formuleringen kunde tolkas som krav på loggning av all nättrafik | Förtydligat proportionerlig loggning och integritets-/lagringsavvägningar. |
| Robusthet | Nätverksredundans riskerade att framstå som garanti för fungerande verksamhetsflöde | Förtydligat att applikationens felhantering också måste verifieras. |
| Service mesh | Risken att läsaren tolkar det som rekommenderad standard för all tjänstkommunikation | Förtydligat drifts- och felsökningskostnaden och behovsstyrt val. |
| Livscykel för nätprofiler | Automatiserad skapning betonades mer än ändring och förvaltning | Förstärkt hantering av felaktig policyändring, återhämtning, avveckling och kostnadsmätning. |
| AI/egress | Nätfilter kunde ges för bred säkerhetsbetydelse | Förtydligat begränsningarna med destinationsfilter och att nätstopp inte återkallar redan genomförda handlingar. |
| Specialisttjänster | Risk för att kontextberoende tjänster ses som generationskrav | Tydligare villkor för medier och verksamhetskritisk fältkommunikation i YAML. |

## Källgranskning

- De **12 direkta tjänstekopplingarna och ID-numren** grundas på modellbaseline v1.1 och ska ligga fast.
- NIST SP 800-207 ger stöd för att nätposition inte ensam skapar tillit, men fastställer **inte** den här bokens generationsmodell.
- NIST SP 800-204A beskriver bland annat service mesh som ett arkitekturalternativ. Det ger **inte** ett generellt krav att införa service mesh.
- CNCF:s mognadsmaterial stödjer skillnaden mellan standardiserade verktyg och faktisk självbetjäning; CNCF-nivåerna kan **inte** översättas direkt till G1–G4.
- Alla krav på indikatorer, prioriteringsnivåer och arbetsordning är **analytiska rekommendationer**, inte observerade fakta om en viss organisation.

## Kvarstående frågor inför publicering

1. Sätt mätmål för nätändringar, återställning, tillgänglighet och tekniskt skydd per verksamhetsrisk; det finns inga universella tröskelvärden i källorna.
2. Gör en tvärkapitelsgranskning mot CAP-IT-06, CAP-IT-07 och CAP-IT-12 för att undvika dubbelt ansvar för integration, identitet och skydd.
3. Låt en nätverks- och säkerhetsspecialist sakgranska exempel på policy, DNS och återställningsprov innan tryck.
4. Anpassa begreppen *ingress*, *egress*, *workload* och *Zero Trust* konsekvent i hela boken.

## Kontroller för denna leverans

- 12 unika PLS-ID:n med fyra profiler vardera.
- 48 tjänste-/generationsprofiler bevarade.
- Modellens YAML kan tolkas av standardparser.
- Kommentarer och bedömningar gör inte anspråk på faktisk organisationsmognad.

**Slutsats:** Kapitel och YAML är lämpliga som nästa granskade bokunderlag, men slutlig faktagranskning och redaktionell harmonisering med övriga kapitel återstår.
