# Kritisk samgranskning kapitel 7–9 och koppling till Utveckling och teknisk leverans – r0022

## Underlag och status
Granskningen utgår från läsarmanusen för kapitel 7–9 i projekt r0021, godkänd bokplan, redaktionell canon och kritiskt granskat källmaterial för *Utveckling och teknisk leverans*. Utvecklingsförmågan saknar ännu färdigt bokkapitel; slutsatserna om den är därför redaktionell avgränsning inför kommande författande, inte en granskning av ett färdigt kapitel. Ingen oberoende extern sakgranskning har utförts.

## Iakttagelser och ändringar
1. **Överlapp mellan dataplattform och integration:** Kap 7 återgav stora delar av kap 9:s integrationsgräns. Förkortat till att pipeline- och datapubliceringsansvar ligger i dataförmågan, transport och tjänstegränssnitt i integrationsförmågan.
2. **Sökindexering kontra ETL/ELT:** Kap 8 behåller indexets söksyfte; kap 7 fokuserar på förvaltade datamängder. Ingen omklassificering av sökindex till lakehouse eller dataplattform.
3. **Rapporter/assistenter och lagring:** Kap 7 förklarar att återanvändning av godkända datamängder är normalfall och egen beständig lagring bara behövs när lösningen kräver det. Tillägg om att dataförmågan publicerar villkor och kvalitet, medan anslutning och skapandemiljö ägs av andra förmågor.
4. **Generation 3:** Kap 7 behåller två distinkta självbetjäningsfall – förvaltad databas och självbetjänad datapipeline. Kap 9 behåller teamens rätt att själva hantera integrationskontrakt och fel; ingen ny beställningsmodell. Kap 8 erbjuder sök/BI/AI som produkter.
5. **Generation 4:s oskarpa gräns mot utvecklingsplattformen:** I kap 8 gav en uppräkning av skapa, testa, publicera och avveckla intrycket att sök/AI-plattformen bar hela lösningens livscykel. Justerat till förmågespecifik konfiguration, utvärdering och driftinsyn.
6. **Generation 4:s integrationsgräns:** Kap 9 skilde tidigare inte tydligt på integrationsförmågans katalog över godkända verksamhetsfunktioner och skapandemiljön som använder dem. Nu anges att *Utveckling och teknisk leverans* erbjuder en gemensam, kontrollerad bygg- och publiceringsväg, medan integration förser den med trygga anslutningar, kontrakt, mandat och spårbarhet.
7. **Ägarskap och säkerhet:** Skiljer verksamhetsfunktionens ägare från anslutningens driftsansvar, samt läsning från åtgärder som ändrar tillstånd. Kritiska mandatbeslut och säkerhetskontroller kräver betrodda funktioner utanför AI-modellen.

## Samlad ansvarskarta
| Förmåga | Särskilt tjänsteansvar i G3 | Tillkommande erbjudande i G4 |
|---|---|---|
| Datahantering och informationslagring | Databaser, ETL/ELT, datamängder, självbetjänade datapipelines | Godkända dataset och behovsstyrd lagring |
| Analys, sökning och intelligent informationsbearbetning | Sökindex/BI-/AI-tjänster, sök- och modell-API:er, utvärdering | Rapport-/sök-/assistentbyggstenar som går att konfigurera utan specialistkunskap |
| Integration och informationsutbyte | API-, meddelande- och filutbytestjänster, kontrakt, felhantering | Upptäckbara, godkända verksamhetsfunktioner och anslutningar, begränsade mandat |
| Utveckling och teknisk leverans (planerat) | Kod-/bygg-/test-/releasetjänster för professionella team | Skapande-, test-, publicerings-, ägarbytes- och avvecklingsvägar för verksamhetens lösningar |

En och samma utvecklingsportal kan använda alla tjänsterna. Ansvarskartan beskriver därför inte nödvändigtvis fyra produktteam eller plattformar.

## Kvarstående frågor inför fortsättningen
- När *Utveckling och teknisk leverans* skrivs som bokkapitel: pröva helheten för godkända skapandemiljöer, AI-genererad kod, registrering av ägare, riskklassning, testning, versionshistorik, publicering och avveckling – utan att förmågan tar över integrationens mandat- eller AI-plattformens modellansvar.
- I framtida kapitel om *Identitet och tillit*, *Cybersäkerhet och tekniskt skydd* och *Process, workflow och ärendehantering*: precisera mandat, behörighet, kontroll och beslutspunkter.
- Kontrollera de tekniska exemplen mot faktiska produktgarantier inför publicering. Inga särskilda produkter, standarder eller regelkrav är verifierade av denna granskning.
- Formellt kapitelgodkännande och oberoende sakgranskning återstår.

## Redaktionell slutbedömning
Kapitlen har nu tydligare komplementära uppdrag. G4 är inte en uppsättning parallella lågkodsverktyg i varje plattform, utan en sammanhängande användarupplevelse byggd på gemensamma datatjänster, sök/BI/AI, godkända verksamhetsfunktioner och en kontrollerad teknisk leveransväg. Texten har kortats eller ändrats där samma livscykelansvar berättades om flera gånger; kapitel 7–9 bevarar sitt eget konkreta tjänsteerbjudande.
