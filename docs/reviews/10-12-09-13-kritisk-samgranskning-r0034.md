# Kritisk samgranskning: identitet, cybersäkerhet, integration och utvecklingsleverans – r0034

## Underlag och metod

Genomlästa manuskapitel 10 (*Identitet och tillit*) och 12 (*Cybersäkerhet och tekniskt skydd*), med kapitel 9 (*Integration och informationsutbyte*) och 13 (*Utveckling och teknisk leverans*) som kontrollkapitel. Granskningen jämför tjänsteerbjudanden, ansvar, generation 3–4, konkretion och repetitioner. Tidigare kritiskt granskade källunderlag och kapitelplan har behållits som projektets referensram. Bedömningarna av samspel och föreslagna ändringar är redaktionell/arkitektonisk analys, inte oberoende faktaverifiering av specifika produkter.

## Huvudfynd och åtgärder

1. **Viktig distinktion mellan identitet, delegering och verksamhetsmandat (kapitel 10).** Ursprungstexten var i huvudsak korrekt men kunde läsas som att agentmandat alltid är användardelegering. Förtydligat att mandat även kan bygga på ett särskilt beslutat uppdrag, att det ska kunna avgränsas och återkallas samt att skyddad tjänst gör sista prövningen vid genomförande.
2. **Integrationsförmågans mandatansvar var för brett formulerat (kapitel 9).** Uttrycket ”ansvarar för ... mandatgränser” kunde läsas som att integrationsplattformen äger verksamhetsrättigheterna. Ersatt med ansvar för tekniska gränssnitt, anslutningskontroller och anropskontext; den mottagande verksamhetstjänsten äger och verkställer verksamhetsreglerna.
3. **Utvecklingsplattformen framställdes som gemensam utförare av behörighetskontroller (kapitel 13).** Texten preciserades: leveransvägen ansluter godkända tjänster och kontroller; verksamhetstjänsten verkställer relevanta åtkomstregler.
4. **Säkerhetsincidenters gräns mot driftbarhet var för ytlig (kapitel 12).** Kompletterat med behov av samordning av isolering, utredningsunderlag och säker återstart. Hotdetektion och allmän driftövervakning förblir separata tjänsteerbjudanden med samverkan.
5. **AI-risker skulle kunna framstå som tekniskt eliminerbara (kapitel 12).** Förtydligat att granskning och tester reducerar, men inte garanterat avlägsnar, manipulation via otillförlitligt innehåll. AI-utvärdering hör fortfarande till AI-förmågan och åtgärdsmandat till identitets-/verksamhetstjänster.
6. **Generationsbeskrivningarna är tillräckligt konsekventa.** G3: professionella team får automatiserade, säkra standardtjänster utan obligatoriska handläggningar. G4: verksamhetsskapade lösningar får godkända profiler; identiteter och mandat begränsas, och skyddet anpassas efter åtgärd och konsekvens. Inga breda omskrivningar behövs.

## Ansvarsmodell efter ändring

| Förmåga / aktör | Erbjuder eller ansvarar för | Ansvarar inte ensamt för |
| --- | --- | --- |
| Identitet och tillit | Inloggning, arbetslastidentiteter, tillit, mandatmekanismer och återkallelse | Verksamhetsregelns sista beslut |
| Cybersäkerhet och tekniskt skydd | Skyddsprofiler, sårbarhetshantering, hotdetektion och säkerhetskontroller | Inloggningens grundtjänster, allmän driftövervakning, verksamhetsbeslut |
| Integration och informationsutbyte | Godkända gränssnitt, tekniska anslutningar, anropskontext och spårbarhet | Fastställande av verksamhetssystemets tillåtna åtgärder |
| Utveckling och teknisk leverans | Skapande-, test- och publiceringsvägar med integrerade kontroller | Slutlig behörighetsprövning i mottagande verksamhetstjänst |
| Verksamhetstjänst/produktteam | Verksamhetsregler, åtgärdsbehörighet, korrekt effekt av utförd åtgärd | Drift av gemensamma plattformstjänster |

## Omfattning och kvarstående risker

Ändringarna är avsiktligt små. Kapitel 10, 12, 9 och 13 har ändrats; andra kapitel, kapitelplanernas grundstruktur och kanoniska YAML-underlag har lämnats oförändrade. Vissa liknande begrepp förekommer fortsatt eftersom de fyller olika roller i olika kapitel.

**Kvarstående:** Produkt- och organisationsspecifik kontroll av hur delegerade mandat, tokens och återkallelse fungerar; hur incidentansvar och incidentledningen fördelas i praktiken; hur AI-baserade verktygsanrop verifieras och loggas i valda lösningar. Detta är fortfarande redaktionella arbetsutkast, inte formellt godkända kapitel.
