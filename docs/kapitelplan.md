# Kapitelplan

**Status:** Godkänd disposition. Kapitel 01 och 02 är reviderade arbetsutkast i r0005 och inväntar kapitelgranskning; kapitel 03 är koncentrerat och redaktionellt granskat arbetsutkast i r0007; `00-inledning.md` är fortfarande ett kort utkast. Källkapitel finns under `docs/kallmaterial/kapitel/`.

| Nr | Föreslagen bokfil | Titel | Källförmåga | Status |
|---|---|---|---|---|
| 01 | `chapters/01-nar-it-blir-en-broms.md` | När IT blir en broms trots fungerande system | Nyskrivs | Utkast, inväntar granskning |
| 02 | `chapters/02-fyra-generationer.md` | Fyra generationer av IT – två förändringar i synsätt | Nyskrivs | Utkast, inväntar granskning |
| 03 | `chapters/03-it-formagor.md` | Vad en gemensam IT-förmåga egentligen är | Nyskrivs | Utkast, inväntar granskning |
| 04 | `chapters/04-interaktion-kanaler.md` | Interaktion, presentation och kanaler | CAP-IT-01 | Redaktionellt granskat arbetsutkast r0044 |
| 05 | `chapters/05-process-workflow.md` | Process, workflow och ärendehantering | CAP-IT-02 | Kritiskt samgranskat arbetsutkast r0043 |
| 06 | `chapters/06-regler-beslut.md` | Regler och beslut | CAP-IT-03 | Kritiskt samgranskat arbetsutkast r0043 |
| 07 | `chapters/07-datahantering.md` | Datahantering och informationslagring | CAP-IT-04 | Arbetsutkast r0016; samläst med kapitel 08 |
| 08 | `chapters/08-analys-ai.md` | Analys, sökning och intelligent informationsbearbetning | CAP-IT-05 | Omarbetat arbetsutkast r0012; konkret tjänsteerbjudande för sökning, BI och AI |
| 09 | `chapters/09-integration.md` | Integration och informationsutbyte | CAP-IT-06 | Arbetsutkast r0021; gräns mot datahantering och behovsstyrda G4-anslutningar granskad |
| 10 | `chapters/10-identitet-tillit.md` | Identitet och tillit | CAP-IT-07 | Arbetsutkast r0031 |
| 11 | `chapters/11-slutanvandarmiljo.md` | Slutanvändarmiljö och klientplattform | CAP-IT-11 | Redaktionellt granskat arbetsutkast r0046 |
| 12 | `chapters/12-cybersakerhet.md` | Cybersäkerhet och tekniskt skydd | CAP-IT-12 | Arbetsutkast r0033; samgranskat med identitet, utveckling och driftbarhet |
| 13 | `chapters/13-utveckling-leverans.md` | Utveckling och teknisk leverans | CAP-IT-10 | Arbetsutkast r0023; G3 utvecklarprodukt och G4 verksamhetsskapad livscykel |
| 14 | `chapters/14-kormiljo.md` | Applikationsexekvering och körmiljö | CAP-IT-08 | Arbetsutkast r0026; körprofiler, G3 självbetjäning och G4 behovsstyrd tilldelning |
| 15 | `chapters/15-natverk.md` | Nätverk och konnektivitet | CAP-IT-13 | Arbetsutkast r0035; granskat mot integration, identitet, cybersäkerhet och körmiljö |
| 16 | `chapters/16-driftbarhet.md` | Driftbarhet och motståndskraft | CAP-IT-09 | Arbetsutkast r0028; samgranskat mot körmiljö och utveckling |
| 17 | `chapters/17-it-nya-roll.md` | Från systemleverantör till möjliggörare – ansvar, arbetssätt och kompetens | Nyskrivs | Redaktionellt granskat arbetsutkast r0052 |

Inledningen planeras som `chapters/00-inledning.md`. Bilagor och referenser tillkommer efter kapitelredigering.


**Gränsdragning inför kapitel 07:** Warehouse, Lake och Lakehouse tillhör CAP-IT-04 som dataplattformstjänster. Kapitlet ska endast kort peka på hur BI, rapportering, sökning och AI konsumerar dem genom CAP-IT-05. Se `docs/reviews/08-gransdragning-data-bi-r0010.md`.

**Redaktionellt beslut r0011:** Kapitel 08 disponeras i sökning, analys/BI, AI och en kort tillämpning av G3/G4. Vid skrivning av kapitel 07 ska dataplattformens lagring, ingestion, metadata och livscykel avgränsas mot CAP-IT-05:s analys-/BI- och AI-tjänster.

**Redaktionellt beslut r0012:** Förmågekapitel ska beskriva tjänsteerbjudandet före användningsfallen. Kapitel 08 är pilot för strukturen: sökning, analys/BI och AI definieras med erbjudna tjänster, konsumtionsgränssnitt, livscykelstöd och särskilda kontrollbehov, följt av ett kort G2–G4-perspektiv. Kapitel 07 avgränsas fortsatt till CAP-IT-04:s dataplattformstjänster.

**Beslut r0013 för kapitel 08:** Generation 3 konkretiserar utvecklingsteamens hela livscykel; generation 4 konkretiserar erbjudandets fem steg (skapa, ansluta, prova, publicera/dela, förvalta/avveckla). Ett enda jämförande exempel. Sökning, BI och AI samt gränsen till CAP-IT-04 är oförändrade.

**Revision r0016:** Kapitel 07 har skrivits med huvudvikt på datatjänster för verksamhetssystem, warehouse/lakehouse, datakvalitet, metadata och informationslivscykel. BI/rapportering, sökning och AI hålls i kapitel 08. Interna koder förekommer inte i läsarmanuset.

**Revision r0017:** Kapitel 07 kompletterat med databaskategorier för IT-stöd, lagringsprofiler, ETL/ELT-gränsdragning, central DW-funktion i generation 2 kontra självbetjänade datapipelines i generation 3 och proportionerlig lagring i generation 4. Tjänsteval är behovs- och riskstyrda, inte generationsstyrda.

**Revision r0019:** För kapitel 07 är generation 4:s lagringserbjudande behovsstyrt: verksamheten anger informations- och skyddsbehov, plattformen matchar mot godkända tjänsteprofiler eller hänvisar till specialistprövning.

**Revision r0020:** Kapitel 07 och 08 korsgranskade; datainhämtning/ETL, sökindexering, data- respektive måttansvar och återanvändning av godkända data i generation 4 är tydligare avgränsade.

**Revision r0021:** Kapitel 09 utformat som integrationsförmågans konkreta tjänsteerbjudande: API, meddelanden/händelser, fil/extern anslutning och kontraktslivscykel. ETL/ELT och analytisk transformation ligger fortsatt i kapitel 07; G3 självbetjäning och G4 begriplig funktionskatalog tydliggjorda.

**Samgranskning r0022:** Kapitel 07–09 avgränsade mot varandra och den framtida förmågan *Utveckling och teknisk leverans*. Vid författande av dess kapitel ska G4:s gemensamma skapande-/publiceringslivscykel beskrivas där, inte dupliceras i varje annan förmåga.

**Revision r0023:** Kapitel 13 skrivet med fokus på gemensamma utvecklings-/leveranstjänster för professionella team och verksamhetsskapade lösningar. Gränsdragning mot data, integration, AI, körmiljö och driftbarhet granskad.

**Revision r0024:** Kapitel 13 kritiskt samgranskat. Tydligare gränser mellan utvecklings- och leveransväg respektive körmiljö/driftbarhet, G3:s leveranssjälvständighet, riskstyrda G4-skapandemiljöer och övergång till professionell förvaltning.

**Revision r0025:** Kapitel 7, 8, 9 och 13 samgranskade. Kapitel 8 och 13 justerade för att skilja AI-utvärdering som plattformstjänst från publiceringskontroller och för att korta upprepade agentexempel. Kapitel 7 och 9 oförändrade.

**Revision r0026:** Kapitel 14 infört. Körmiljöer avgränsas från utvecklingsleverans, data och driftbarhet; ingen teknisk runtime identifieras med en bestämd generation.

**Revision r0028:** Kapitel 16 infört. Gemensamma driftbarhetstjänster har avgränsats mot körmiljö, utveckling, data, AI och integration; generation 3 ger självbetjänade driftprofiler och generation 4 riskanpassat stöd till verksamhetsskapade lösningar.

**Revision r0029:** Kapitel 14 förtydligar flera körmodeller (VM/applikationsservrar, containrar, PaaS, serverlöst/händelsestyrt, batch och AI-exekvering) samt avgränsar exekvering bakom data-, integrations- och AI-tjänster. Ingen revidering av kapitel 16.

**Samgranskning r0030:** Kapitel 13, 14 och 16 har fått skarpare gräns mellan leverans, exekvering och driftbarhet samt ansvar för dataåterställning och processkompensation. Se `docs/reviews/13-14-16-kritisk-samgranskning-r0030.md`.

**Revision r0031:** Kapitel 10 *Identitet och tillit* skrivet utifrån källkapitlet. Fokus: identitetstjänster som erbjudande, G3 självbetjäning, G4 avgränsade agentmandat och resursnära auktorisation. Se `docs/reviews/10-redaktionell-granskning-r0031.md`.

**Revision r0032:** Kapitel 10 kritiskt samgranskat med integration, AI och utvecklingsplattform. Delegerat agentmandat skilt från teknisk identitet; upprepningar kortade.

**Revision r0033:** Säkerhetskapitlet skrivet från det kritiskt granskade underlaget. Gemensamt tjänsteerbjudande för workloadskydd, exponeringshantering, säkerhetsdetektion och automatiserade kontroller; G3 säker självbetjäning och G4 riskanpassat skydd. Gränser mot identitet, AI, nätverk och driftbarhet prövade.

**Samgranskning r0034:** Kapitel 10 och 12 prövade tillsammans med 9 och 13. Agentmandat, skyddad tjänsts slutliga behörighetskontroll, säkerhetsincidenters samordning och AI-riskernas begränsningar preciserade.

**Revision r0035:** Kapitel 15 nätverk och konnektivitet skrivet från kritiskt granskat källmaterial. Grundtjänster, nätpolicy, felsökning och livscykel; G2 funktionsbrister kontra G3 självbetjäning och G4 behovsstyrd nätåtkomst. Gränser mot integration, identitet och säkerhet förtydligade.

**Samgranskning r0036:** Kapitel 9, 10, 12 och 15 samordnade. Skillnaden mellan nätpolicy, API-kontroll, identitetsmekanismer, verksamhetsmandat och skydd av applikationsanrop preciserad.

**Revision r0037:** Kapitel 05 om process, workflow och ärendehantering skrivet utifrån kritiskt granskat källmaterial. Fyra tjänstekategorier, särskilda krav på samtidighet och processversionering, G3 självbetjäning och G4 verksamhetsnära automation.

**Revision r0038:** Kapitel 05 och 09 samgranskade och justerade avseende teknisk kvittens, processinstans, dubbletter, sena svar och verksamhetsansvar. Kapitel 10 och 13 kontrollerade utan textändring.

**Revision r0039:** Kapitel 05:s generation 4 förtydligar full verksamhetsstyrd livscykel för ärendeflöden och riskanpassad självpublicering, utan att duplicera utvecklingsplattformens allmänna erbjudande.

**Revision r0040:** Kapitel 05 generation 3: central plattform som intern produkt; utvecklingsteam har hela livscykeln för sina processlösningar och platformteamet förvaltar gemensamma tekniska komponenter. Skillnad mot generation 4 ska fortsatt vara vem som självständigt kan skapa (professionella team respektive verksamheten).

**Revision r0041:** Kapitel 05 kontroll av isolerade teamkonfigurationer, test utan verkliga sidoeffekter och uttrycklig gräns mellan publicering och behörighet till verksamhetsbeslut.

**Revision r0044:** Kapitel 04 om interaktion, presentation och kanaler tillagt från kritiskt granskat källmaterial. Tydlig G3-självbetjäning för utvecklingsteam och G4-självbetjäning för verksamhetens gränssnitt; separata ansvar för formulär, processer, integration och generell publicering.

**Revision r0045:** Kapitel 04, 05 och 06 samgranskade med kapitel 13 som kontroll. Funktionella gränser för formulär, notifiering, testning och publicering förtydligade; fortfarande arbetsutkast utan formellt godkännande.

**Revision r0046:** Kapitel 11 infört med fyra tjänsteområden från källmodellen, bred klientprofilering och tydliga gränser mot interaktion, identitet, cybersäkerhet och utvecklingsleverans. Alla 13 förmågekapitel har nu manusutkast; kapitel 17 återstår.

**Revision r0047:** Alla 13 förmågekapitel genomgångna i en samordnad redaktionell harmonisering. G3/G4, specialistansvar och hänvisningar har koncentrerats utan förändrad kapitelindelning. Kapitel 17 återstår; inga förmågekapitel formellt godkända.

**Redaktionell inriktning r0051 inför kapitel 17:** Ekonomisk hållbarhet i generation 4 behandlas i huvuddrag här: finansieringsmodell för central baskapacitet kontra ovanlig förbrukning, kostnadsansvar och budgetramar, licensmodeller (skapare/användare/app/anslutning/anrop), upphandlings- och leverantörsberoenden, exitmöjlighet samt balans mellan självbetjäning och rimlig ekonomisk kontroll. Undvik att upprepa kapitel 03:s princip och kapitel 13:s konkreta publiceringserbjudande.

**Revision r0052:** Kapitel 17 skrivet som syntes av ansvar, arbetssätt, kompetens och ekonomisk styrning. Det tidigare fallet om ofullständiga ärendeunderlag följs genom G2–G4. Kapitel 00–16 och ursprungliga källmodeller oförändrade; oberoende sakgranskning och helhetsgranskning återstår.

**Revision r0053:** Kapitel 17 kritiskt granskat och justerat som synteskapitel. AI-förslag kontra verksamhetsregel, separata plattformsansvar, beslutsvägar, licensspridning och konkret förändringsuppföljning förtydligade. Övriga kapitel oförändrade.
