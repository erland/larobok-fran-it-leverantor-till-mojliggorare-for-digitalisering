# Redaktionell revision r0050 – säkert körande av verksamhetsskapade applikationer

## Syfte
Riktade tillägg efter granskning av hur verksamhetsskapade och AI-genererade applikationer kan köras utan att skada andra IT-stöd. Kapitel 11, 13 och 14 revideras. Övriga manus och källmodeller förblir oförändrade.

## Genomförda ändringar

| Kapitel | Ändring | Ansvarsgräns |
|---|---|---|
| 11 – Slutanvändarmiljö och klientplattform | Skiljer mellan webb/PWA, förvaltad low-code och lokalt installerad kod; beskriver begränsade lokala behörigheter och att webbläsarisolering inte garanterar säkerhet. | Klientmiljön ansvarar för lokal körning, hantering och skydd, inte appens verksamhetsfunktion. |
| 13 – Utveckling och teknisk leverans | Kopplar publicering till obligatorisk skyddad kör- eller klientprofil och fortsatta kontroller efter driftsättning. | Leveransvägen tillämpar profiler; kör- och klientplattformarna tillhandahåller skyddet. |
| 14 – Applikationsexekvering och körmiljö | Konkretiserar isolering och gränser för CPU, minne, lagring, samtidighet, körtid och skalning samt sammanlagda kvoter; kan begränsa/stoppa felaktiga arbetslaster. | Körmiljön skyddar delad exekvering; integrations-/API-tjänster måste separat skydda mottagande system från anropsstormar. |

## Kritiska kontroller
- Tilläggen gör inga absoluta påståenden om riskfri körning eller perfekt isolering.
- Resursgränser för enskilda appar skiljs från sammanlagd belastning.
- Publikation, exekvering och klientdistribution hålls åtskilda.
- Ingen ny obligatorisk produkt, teknik eller plattform föreskrivs.
- G3:s utvecklingsteams självbetjäning och G4:s verksamhetsnära behovsstyrning är oförändrade.
- Källmodeller och andra förmågekapitel har inte ändrats.

## Kvarstående kontrollpunkter
Oberoende teknisk sakgranskning och formellt redaktionellt godkännande återstår. Vid helhetsgranskning bör särskilt kontroll göras av gränsen mellan belastningsskydd på API-/integrationsnivå och resursisolering i körmiljön.
