# Källgrund och redaktionell omprövning – generation 3–4, sökning, analys och AI

**Status:** Förslag till redaktionell grund, inte beslutad omarbetning av bokmanuset.  
**Datum:** 2026-11-08  
**Syfte:** Etablera en källförankrad begrepps- och kapitelstruktur för faktaboken *Från IT-leverantör till möjliggörare för digitalisering*, utan att göra texten längre eller mer repetitiv.

## 1. Slutsatser

1. Beskriv **generation 3** som *självständighet för professionella produkt- och utvecklingsteam över tjänstens livscykel*, möjliggjord av plattformar som interna produkter. Stöd: CNCF:s Platform Engineering Maturity Model och Team Topologies.
2. Beskriv **generation 4** som *ökad förmåga för verksamhetens medarbetare och team att själva skapa, anpassa och förvalta digitala lösningar*. Stöd: citizen development, low-code, fusion teams samt ny AI-assisterad utveckling. Det är en redaktionell syntes, inte en etablerad universell generationsmodell.
3. Skilj på **sökning (hitta relevant information)**, **analys och BI (beräkna, undersöka och presentera samband och mått)** och **AI (prediktion, klassificering, generering och i vissa fall handlande)**. Dessa samverkar ofta, men har olika syfte, teknisk logik, risker och historik.
4. Säg inte att AI i sig är nytt. Symbolisk AI, maskininlärning och NLP är äldre fält. Den förändring som ger generation 4 dess särskilda prägel är **brett tillgänglig generativ AI, assistenter, agentfunktioner och AI-assisterat skapande**.
5. Behåll CAP-IT-05 som paraplyförmåga enligt de 13 redan fastställda förmågorna, men ge den **tre tydligt separerade delområden**. Undvik en lång produkt- eller tekniklista.

## 2. Källförankring för generationsskillnaden

### Generation 3: plattform som intern produkt

CNCF beskriver en mognad mot plattformstjänster som produkt, frivilligt nyttjad självbetjäning, tydliga gränssnitt och utvecklarupplevelse. Team Topologies beskriver plattformsteam vars uppgift är att minska belastningen på team som levererar användarvärde. Vi översätter detta till följande kärnbudskap:

> Professionella utvecklings- och produktteam ska kunna utveckla, driftsätta, observera, felsöka, förändra och avveckla sina tjänster inom gemensamma säkra och robusta ramar, utan att rutinåtgärder kräver manuella överlämningar.

**Skillnad mot traditionell driftorganisation:** Båda behöver säkerhet, tillgänglighet och kompetent drift. Plattformsteamet har dessutom ett uttryckligt *produktuppdrag* att göra de andra teamen självständiga, mäter faktisk användbarhet och undanröjer återkommande beroenden, inte bara utför infrastrukturomställningar.

### Generation 4: fler kan skapa lösningar

Citizen development, low-code och fusion teams är äldre än den generativa AI-vågen. Microsofts mognadsmodell beskriver styrning, utvecklargemenskap, återanvändbara komponenter och samarbete mellan professionella och verksamhetsnära utvecklare. Gartner (2026) lyfter särskilt att AI-assisterad citizen development kan skapa oägda och oförvaltade lösningar om inte livscykelansvaret följer med.

> Verksamhetsmedarbetare kan själva forma, skapa och utveckla exempelvis assistenter, arbetsflöden, automatiseringar och applikationer – inom riskanpassade ramar och med professionellt stöd när det behövs.

**Varför:** Fler lokala förbättringsbehov kan hanteras nära arbetet, kortare avstånd mellan domänkunskap och lösning, snabbare experiment och bättre användning av professionell utvecklingskapacitet. Dessa är rimliga motiv, inte garanterade effektutfall.

**Viktig reservation:** Organisationer kan nå detta utan att först ha uppnått hög plattformsmognad. Modellen är en pedagogisk riktning, inte en deterministisk mognadstrappa.

## 3. Tre olika delområden inom CAP-IT-05

| Delområde | Primär fråga | Typiska gemensamma tjänster | Utveckling och historik | Exempel på resultat |
|---|---|---|---|---|
| **Sökning och informationsåtervinning** | Var finns relevant information? | Indexering, sök-API, relevansrankning, metadata, dokumentbehörigheter, hybrid-/vektorsökning | Etablerat sedan flera decennier | Träfflista, relevant dokument eller passage |
| **Analys, BI och beslutsstöd** | Vad har hänt, hur utvecklas det, vilka mönster finns? | Analysmotorer, semantiska modeller, gemensamma mått, BI, visualisering, rapportpublicering och schemaläggning | Etablerat sedan flera decennier | Nyckeltal, rapport, dashboard, analytisk modell |
| **AI och intelligent bearbetning** | Vad kan identifieras, förutsägas, genereras eller utföras? | Modellåtkomst, modellhantering, RAG-koppling, assistent- och agentbyggblock, verktygsanrop, utvärdering, spårning, skydd | AI är äldre; generativ AI:s breda tillgänglighet och AI-assisterat skapande är det nya skiftet | Klassificering, prognos, genererat svar, assistent, automatiserad åtgärd |

**Överlappningar ska förklaras, inte döljas:** BI kan använda maskininlärning. Sök kan använda AI-modeller. RAG kombinerar informationsåtervinning med generativ AI. En AI-agent kan anropa såväl sök- och BI-tjänster som transaktions-API:er. Det gör dem inte till samma delområde.

**Enkel pedagogisk jämförelse med samma information:**
- Sökning: *Hitta de tre styrdokument som gäller för den aktuella situationen.*
- Analys: *Visa hur antalet avvikelser har förändrats över tid och mellan enheter.*
- AI: *Ta fram ett granskningsbart förslag utifrån dokumenten och föreslå nästa arbetsmoment.*

## 4. Ansvarsgränser mot CAP-IT-04 och andra förmågor

- **CAP-IT-04 Datahantering och informationslagring:** dataplattformstjänster som lake, warehouse, lakehouse, dataåtkomst, kvalitet, katalog, metadata och lagringslivscykel. Flera produkter innehåller också SQL-motorer – en fysisk produkt behöver inte motsvara exakt en förmåga.
- **CAP-IT-05 Sökning/analys/AI:** indexerings- och söktjänster, BI/semantiska tjänster, modellåtkomst, AI-utvärdering, assistent-/agentbyggblock. Återanvänder CAP-IT-04 där det är relevant.
- **CAP-IT-06 Integration och informationsutbyte:** styrda anslutningar och API:er som exempelvis agenter använder för åtgärder.
- **CAP-IT-07 Identitet och tillit, CAP-IT-12 Cybersäkerhet:** identiteter, behörigheter, policyer, loggning och tekniska skydd. Inte en separat säkerhetsstack i varje förmågekapitel.
- **CAP-IT-08/09/10:** körmiljö, driftbarhet och utvecklingsvägar för att bygga och förvalta de applikationer som nyttjar CAP-IT-05.

**Rapporter:** Den gemensamma BI-/rapportplattformen hör till CAP-IT-05. En publicerad rapport, dashboard eller verksamhetsspecifik semantisk modell är vanligtvis en produkt eller informationsartefakt som den ansvariga verksamheten eller produktteamet förvaltar. Reglerad officiell rapportering kan kräva särskild versionsstyrning, attest och spårbarhet. Operativa rapporter behöver inte nödvändigtvis baseras på warehouse/lakehouse; de kan bygga på operativa datakällor för aktualitet.

## 5. Rekommenderad ny disposition för pilotkapitlet

**Rubrik:** CAP-IT-05 – Sökning, analys och AI: tre förmågor på en gemensam grund.

1. **Varför denna förmåga behövs** (kort, 100–150 ord): team ska kunna bygga tre olika slags funktioner utan att själva etablera infrastrukturen.
2. **Sökning och informationsåtervinning** (250–350 ord): index, relevans, metadata, behörigheter, skillnad från databasuppslag; vad teamet kan bygga.
3. **Analys och BI** (250–350 ord): analysmotor, semantik, mått, BI och rapportpublicering; gräns mot datalagring.
4. **AI och intelligent bearbetning** (450–650 ord): äldre ML/NLP kontra nya generativa tjänster; modellåtkomst, RAG, verktyg/skills, agentkörmiljö, evals, observation, kostnad, livscykel och risk.
5. **Från generation 3 till 4** (200–300 ord): först utvecklingsteamens självständiga användning av tjänsterna, därefter verksamhetsskapade sökningar, dashboards, AI-assistenter och automationer; avgränsa professionellt och verksamhetsägt ansvar.
6. **En kort slutsats** (40–60 ord): gränsen mellan delområdena och nyttan med återanvändbara byggblock.

**Riktvärde:** cirka 1 300–1 800 ord; styrs av innehåll och inte sidmål. En längre text är försvarbar bara om den ger ny kunskap.

## 6. Redaktionella krav för hela boken

- *En gång på rätt plats:* Generationsmodellen förklaras i kapitel 2. Förmågekapitlen beskriver konsekvensen för just förmågan, inte hela modellen igen.
- *Leverantörsneutralitet:* Produkter endast som illustrativa exempel; byggblock och ansvar är viktigare.
- *Saklig precision:* AI som historiskt forskningsfält skiljs från genombrottet för lättillgänglig generativ AI. Begreppen generativ AI, maskininlärning och agent ska inte likställas.
- *Tre nivåer:* Gemensam förmåga, delad plattformstjänst och verksamhetsägd lösning tydliggörs.
- *Riskanpassning:* Att skapa en personlig assistent är inte samma sak som att ge en agent tillgång att ändra verkliga system eller fatta beslut med rättsliga konsekvenser.
- *Källhänvisningar:* Ange källor till externt verifierbara tekniska påståenden, tydliggör att våra fyra generationer är en syntes.

## 7. Utvalda faktakällor och deras funktion

1. CNCF TAG App Delivery, **Platform Engineering Maturity Model** – intern plattform som produkt och utvecklarsjälvbetjäning. https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/
2. Team Topologies, **Team Interaction Modeling with Team Topologies** – plattformsteam, strömorienterade team, minskad kognitiv belastning. https://teamtopologies.squarespace.com/key-concepts-content/team-interaction-modeling-with-team-topologies
3. CNCF, **What is platform engineering?** (2025) – utvecklingsteamens bygg-, leverans- och förvaltningsflöde. https://www.cncf.io/blog/2025/11/19/what-is-platform-engineering/
4. Microsoft Learn, **Power Platform adoption maturity model** (2026) – citizen development, fusion teams, ansvar och styrning. https://learn.microsoft.com/en-us/power-platform/guidance/adoption/maturity-model-details
5. Gartner, **Successful AI Citizen Development Requires End-to-End Life Cycle Governance** (2026; offentligt abstract) – ägarskap/livscykel. https://www.gartner.com/en/documents/8338217
6. IEEE Technology Navigator, **Information retrieval** – sökning och informationsåtervinning som långvarigt forsknings- och teknikområde. https://technav.ieee.org/topic/information-retrieval/
7. IEEE Technology Navigator, **Business intelligence** – BI:s historik och distinktion från transaktionssystem. https://technav.ieee.org/topic/business-intelligence/
8. IBM, **What is information retrieval?** (2024) – indexering, relevans och informationsåtervinning. https://www.ibm.com/think/topics/information-retrieval
9. NIST, **Artificial Intelligence Risk Management Framework** (2023) – AI-risker över livscykeln. https://www.nist.gov/itl/ai-risk-management-framework
10. NIST, **Generative AI Profile** (2024) – ytterligare risker vid generativ AI. https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence
11. Microsoft Learn, **Retrieval augmented generation and indexes** – sökning + generativ AI, tekniskt skilda men komponerbara. https://learn.microsoft.com/azure/ai-studio/concepts/retrieval-augmented-generation
12. Martin Fowler / Thoughtworks, **Emerging Patterns in Building GenAI Products** (2025) – RAG, utvärdering och produktionsmönster. https://www.martinfowler.com/articles/gen-ai-patterns/

### Källkritisk kommentar

CNCF, Team Topologies, IEEE och NIST används som begreppslig eller metodisk grund. Microsofts material är värdefullt för citizen development men speglar också en specifik leverantörsplattform. Gartner-punkten ovan bygger endast på det öppet tillgängliga abstractet, inte på den betalväggsskyddade fulltexten. Ingen av dessa källor formulerar exakt vår fyra-generationsmodell; den är en redaktionell tolkning och ska beskrivas som sådan.

## 8. Nästa redaktionella beslut

**Rekommendation:** Godkänn denna indelning som styrande princip innan fler CAP-IT-kapitel omarbetas. Uppdatera därefter kapitel 8, gränsdragningsdokumentet och i förekommande fall korta hänvisningar i kapitel 2–3. Undvik att skriva om de övriga kapitlen på en gång; kontrollera först att CAP-IT-04 och CAP-IT-05 kompletterar varandra.
