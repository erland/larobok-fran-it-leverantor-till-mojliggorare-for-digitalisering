# Kritisk granskning – CAP-IT-05, version 2

## Bedömning

Grundstrukturen är hållbar och generation 2 är ett rimligt huvudperspektiv. Version 1 skiljer redan mellan grundproblem och verkliga motiv för gemensam plattform samt mellan analytisk korrekthet och teknisk funktion. En fördjupad granskning visade däremot flera luckor i tidslogik, säkerhet och testbarhet. Följande korrigeringar är gjorda i **både kapiteltext och YAML där det är relevant**.

## Identifierade brister, konsekvenser och ändringar

| Område | Granskningsfynd | Åtgärd i v2 |
|---|---|---|
| Semantiskt måttlager | PLS-098 hade samma generella kritikalitetsregel som själva analysfunktionen. Det kunde tolkas som att en separat måttplattform är nödvändig. | Kritikaliteten och centraliseringsbehovet görs uttryckligen situationsberoende; enkelt dokumenterat begreppsägarskap kan räcka. |
| Tidsdimensioner | Händelsetid, registreringstid och beräkningstid var inte tydligt separerade. | Nytt avsnitt och verifieringsprov för sena händelser, historiska rättelser och rapportversioner. |
| Datakvalitets-SLO | En grön pipeline kunde lätt tolkas som garanti för korrekt verksamhetsmått. | Separata mått för färskhet, fullständighet, fördröjning och innehållslig riktighet. |
| Söksekretess | Prov fokuserade främst på själva dokumentet och indexbehörighet. | Test även av träffrubriker, utdrag, förhandsvisningar och cache vid återkallad åtkomst. |
| Obetrodd retrieval | RAG behandlades främst som ett svarskvalitetsproblem. | Nytt avsnitt och testfall för instruktioner i källmaterial, otillåtna verktygsanrop och informationsläckage. |
| AI-utvärdering | Ett sammanvägt kvalitetsmått riskerar att dölja särskilt allvarliga fel. | Separata prov för retrieval, källstöd, sanningshalt, behörighet och konsekvens, även vid modellbyte. |
| Framtidsläckage | ML-beskrivningen var för allmän om tidskänslig träning och test. | Explicit prov för point-in-time-riktighet samt dubbletter mellan träning och test. |
| LLM-pilot | Testinstruktionen »känslig prompt« kunde uppmuntra att verkligt skyddsvärt innehåll skickas till pilot. | Ändrat till syntetisk testprompt och verifierad databehandlingspolicy. |
| Reproducerbar ML | Risk att experiment beskrivet som reproducerbart uppfattas som bitvis deterministiskt. | Särskilj dokumenterat experiment, jämförbar kvalitet och eventuell icke-determinism. |
| Modellrollback | För lätt att tolka tekniskt versionsbyte som återställning av redan publicerade resultat. | Nytt avsnitt om rättelse, kommunikation och verksamhetseffekter. |
| Medie- och platsdata | Testsuite fångade inte alltid gruppskillnader, små urval och raderingsbegränsningar. | Kompletterande prov för kvalitet per grupp, återidentifiering samt mellanresultat och beslutad gallring. |

## Teknikneutralitet och generationslogik

Samtliga 16 PLS-tjänster har behållits med ursprungliga PLT-kopplingar. De 64 generationsprofilerna finns kvar. ML-träning, semantiskt lager, grafdatabas, geospatial analys och generativ AI är inte obligatoriska per generation. Krav på gemensam plattform måste motiveras av återkommande behov, säkerhet, drift, kostnad och faktisk konsumentnytta.

## Källstöd och redaktionell status

Källmodellens identifierare, namn och relationer härrör från baselineunderlaget. Exempel, bedömningar, tjänsteprov och de nu tillagda kontrollpunkterna är **kompletterande arkitekturanalys**, inte uttryckliga krav i baseline eller påståenden om en viss organisations nuläge.

Kompletterande faktastöd: [Google SRE – Data Processing Pipelines](https://sre.google/workbook/data-processing/) beskriver färskhet, fullständighet och att datatransport inte garanterar innehållskvalitet. [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org/llm-top-10/) beskriver bland annat prompt injection, informationsläckage och svagheter i retrieval/embeddings. NIST AI RMF och NIST AI 600-1 är vägledningar, inte produktkrav.

## Återstående begränsningar

1. Kapitlet behöver extern fackgranskning av analys, sökning, ML och informationsskydd innan publicering.
2. Rättsliga regler om personuppgifter, register, bevarande, gallring och automatiserade beslut varierar med verksamhet och jurisdiktion; inga generella rättsliga slutsatser dras.
3. En tvärkapitelgranskning behöver harmonisera CAP-IT-05 med CAP-IT-04 (dataägarskap), CAP-IT-06 (dataöverföring), CAP-IT-07 (åtkomst), CAP-IT-03 (beslut) och CAP-IT-12 (skydd).
4. Tjänsteprofilerna är arkitekturexempel; de utgör inte en organisationsspecifik mognadsbedömning.
