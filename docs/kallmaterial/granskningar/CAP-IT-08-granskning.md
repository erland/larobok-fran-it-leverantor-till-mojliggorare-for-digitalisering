# Kritisk granskning – CAP-IT-08, version 2

*7 november 2026 · Underlag till faktabok, ej publiceringsgodkännande*

## Samlad bedömning

Kapitlet har en tydlig kärna: generation 2 är referenssituationen; container, VM och applikationsserver är alternativa tekniker och inte en generationsskala. Det är läsbart utan förkunskap om ursprungsmodellen och skiljer i huvudsak på grundläggande stabilisering av G2 och argument för G3. **Bedömning: god grund, men version 1 behövde ett mer stringent bedömningsstöd och verkligt tjänstespecifika kontroller.**

## Identifierade brister och utförda korrigeringar

| Granskning | Risk i version 1 | Korrigering i version 2 |
|---|---|---|
| Teknisk precision | Körmiljön beskrevs i inledningen som den som skalar eller byter version av arbetslasten | Förtydligat att applikationsarkitektur avgör om detta fungerar utan avbrott |
| Förmågeavgränsning | Risk att körning, återställning och release blir en odifferentierad helhet | Förtydligat praktiska beroenden och uppgraderingsansvar; CAP-IT-09/10/12 ligger kvar som skilda förmågor |
| G2-diagnostik | Tekniska varningssignaler kunde misstas för automatiska produktbytesargument | Förstärkt kontroll av produkt kontra process, implementation och ansvar |
| G2-livscykel | Batchjobb nämnde omkörning utan konkret risk för dubbelexekvering | Lagt till timeout, idempotens-/dubbeleffektproblematik och provbar kontroll |
| G3 | Självbetjäning kunde mätas endast vid nybeställning | Lagt till undantag, uppgradering, avveckling och faktisk supportbelastning |
| G4 | Indikatorn antydde att alla kostsamma arbetslaster kan stoppas utan prövning | Förtydligat automatiskt stopp **eller** förutbestämd granskning enligt risk |
| Pedagogik | Saknade ett sammanhängande exempel med olika arbetslasttyper | Lagt in ett ärendehanteringsexempel med äldre middleware, API och nattjobb |
| YAML-kvalitet | Nästan identiska verifieringar för sex mycket olika PLS-tjänster | 18 separata G2/G3/G4-prov samt särskilda G1-kontroller |
| Källprecision | NIST-guiden kunde uppfattas som aktuell teknisk benchmark | Årtalet 2017 och begränsningen till principnivå anges; CNCF är ett kompletterande perspektiv |

## Kvarvarande begränsningar

- Kapiteltexten är en konceptuell faktaboksbeskrivning och inte en specifikation av runtime, hypervisor eller molnprodukt.
- Kritikalitet varierar per arbetslast och informationsklass; bedömningen kan inte fastställas universellt per PLS.
- Exemplen på plattformsbeteende är arkitekturbedömningar, inte bevis för att en viss produkt har eller saknar funktion.
- Källregistret i den färdiga boken behöver harmoniseras mellan kapitlen; publikationsdatum och tekniska versioner behöver kontrolleras inför utgivning.
- G4 är ett framtidsscenario och ska förbli explicit villkorat.

## Slutkontroller

- G2 är huvudperspektivet och arv från G1→G2 är ett separat resonemang.
- Teknikindikatorer, tillräckligt-stöd-indikatorer och beredskap G2→G3 finns.
- Sex tjänste-ID (PLS-031, 032, 033, 034, 078, 091) och båda PLT-referenserna bevaras.
- YAML innehåller sex tjänster × fyra generationsprofiler, med separata tester per tjänst för G2–G4.
- Inga krav på obligatorisk containerisering eller generellt produktbyte.

**Rekommendation:** använd version 2 som mall för CAP-IT-10. Bevara samma balans mellan faktatext och prövbara indikatorer, men låt kommande kapitel ha olika tyngdpunkt efter förmågans karaktär.
