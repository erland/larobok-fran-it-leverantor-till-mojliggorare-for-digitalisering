# Kritisk samgranskning – kapitel 13, 14 och 16 (r0030)

## Granskat material
- Kapitel 13: *Utveckling och teknisk leverans*, r0029.
- Kapitel 14: *Applikationsexekvering och körmiljö*, r0029.
- Kapitel 16: *Driftbarhet och motståndskraft*, r0029.
- Närliggande manuskapitel 7–9 har använts som kontroll av gränsdragningar, utan att ändras.

## Samlad bedömning
De tre kapitlen har en tydlig och användbar ansvarsfördelning. Några formuleringar riskerade dock att göra plattformstjänsterna ansvariga för ett helt IT-stöds robusthet, och sammanfattningar upprepade redan förklarade beroenden. Därför har endast avgränsade preciseringar gjorts.

## Genomförda ändringar
1. **Kapitel 13**: förtydligar att leveransvägens kontroller inte garanterar att applikationen fungerar robust efter publicering. Kortar resonemang om överlämning av verksamhetsskapade lösningar och upprepad katalog över andra förmågor.
2. **Kapitel 14**: skiljer körmiljöns tekniska tillgänglighet från hela IT-stödets kontinuitet. Preciserar att körmiljön exponerar driftsignaler och kortar den upprepade ansvarskatalogen.
3. **Kapitel 16**: skiljer lagringsplattformens säkerhetskopiering från driftbarhetsförmågans samordning och verifiering av återställning av hela IT-stödet. Förtydligar att kompensation för redan utförd verksamhetsåtgärd kräver process- och applikationsansvar, inte kan delegeras till integrationsplattformen. Avslutningen koncentreras.

## Kontroll mot generationerna
- Generation 3: utvecklingsteam kan leverera och driva sin egen tjänst med självbetjäning, men plattformsteamen ansvarar för sina respektive tjänster och tvärgående incidenter behöver samordnas.
- Generation 4: verksamhetsskapade lösningar får behovsstyrd leverans och körning samt riskanpassade driftbarhetsfunktioner. De får inte automatiskt verksamhetskritisk kvalitet eller återställbarhet.
- Körmiljötyperna i kapitel 14 kvarstår, inklusive VM, containrar, PaaS, serverlös körning, batch och AI-exekvering.

## Öppna granskningsbehov
- Fördelningen mellan produktteamets jouransvar och central incidentledning behöver beskrivas i bokens avslutande ansvarskapitel, inte upprepas i varje förmågekapitel.
- Konkreta exempel på RPO/RTO, dataskydd och kontinuitetskrav ska faktaverifieras innan publicering.
- Granskningen är redaktionell och teknisk rimlighetsbedömning, inte oberoende sakkunniggranskning eller formellt kapitelgodkännande.
