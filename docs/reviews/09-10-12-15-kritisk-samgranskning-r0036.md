# Kritisk samgranskning – integration, identitet, cybersäkerhet och nätverk (r0036)

## Underlag och avgränsning

Fullständig genomläsning av manuskapitel 9, 10, 12 och 15 i projektets revision r0035. Kapitel 13, 14 och 16 har använts som gränskontroll där utvecklings-, körmiljö- och driftbarhetstjänster berörs. Syftet var att granska **tjänsteerbjudandenas ansvar, logiska gränser, generation 3 och 4, teknisk precision och repetition**. Revisionen utgår från projektets befintliga underlag och gör inga anspråk på oberoende produkt- eller implementationsverifiering.

## Kritiska fynd och genomförda ändringar

1. **Nätpolicy och API-åtkomst riskerade att blandas samman.** Kapitel 15 förklarade att nätåtkomst inte ger behörighet, men skillnaden mot en gateway var inte tillräckligt synlig. Nätförmågan tillåter eller nekar tekniska trafikrelationer; integrationsplattformen kan validera anrop och begränsa trafik; mottagande system prövar verksamhetsåtgärden. Kapitel 9 och 15 justerade samordnat.
2. **Mandatmekanism och verksamhetsbeslut låg för nära varandra i identitetskapitlet.** Kapitel 10 förtydligar nu att identitetsförmågan representerar, förmedlar, begränsar och återkallar mandat. Vilka uppdrag och åtgärder som faktiskt får förekomma beslutas av behörig verksamhetsfunktion och kontrolleras i mottagande tjänst. Ett sådant mandat kan baseras på delegering eller separat tilldelat uppdrag.
3. **Applikationstrafiksskyddet kunde uppfattas som nätsegmentering.** Kapitel 12 skiljer nu explicit skydd mot skadligt innehåll i applikationsanrop från regler för nåbarhet och nättrafik i kapitel 15. Detta kan bygga på överlappande produkter utan att tjänsteansvaret blir detsamma.
4. **Felsökning av en trafikrelation var inte tydligt skild från felsökning av verksamhetskedjan.** Kapitel 15 förklarar nätverksförmågans felsökningsgräns. Integrations- och driftbarhetstjänsterna behövs för end-to-end-spårning.
5. **Nätkontroll av extern SaaS-trafik var för generellt formulerad.** Kapitel 15 klargör att intern nätplattform inte automatiskt styr anslutningar inne i en extern förvaltad tjänst. Leverantörens kontroller och villkor behöver då ingå i det godkända erbjudandet.
6. **Skydd av logginnehåll.** Kapitel 9 har kompletterats med den praktiska begränsningen att felsökning och korrelation ska kunna ske utan att känsliga nyttolaster eller åtkomstbevis exponeras i loggar.

## Samlad ansvarsfördelning

| Förmåga/aktör | Primärt ansvar | Inte dess ensamma ansvar |
| --- | --- | --- |
| Nätverk och konnektivitet | DNS, nätförbindelser, teknisk nåbarhet, nätsegmentering och trafikregler | API-kontrakt, semantisk behörighet, fullständigt verksamhetsflöde |
| Integration och informationsutbyte | API:er, köer/händelser, kontrakt, gatewaykontroller och anropsspårbarhet | Fastställa behörighet till verksamhetsåtgärder |
| Identitet och tillit | Autentisering, tillit, tekniska identiteter och mekanismer för begränsade mandat | Besluta verksamhetsmandatens innehåll och verksamhetsregler |
| Cybersäkerhet och tekniskt skydd | Kompletterande skydd, innehålls- och exponeringskontroller, hotdetektion | Nätförbindelser, grundläggande inloggning, allmän driftövervakning |
| Verksamhetstjänst och dess ansvariga | Affärsregler, vilka åtgärder som är tillåtna och kontroll vid exekvering | Drifta alla gemensamma IT-tjänster |

## Generation 3 och 4 – samstämmighet

**Generation 3** beskrivs konsekvent som automatiserat, förvaltat självbetjäningsstöd för professionella utvecklingsteam. Det gäller hela livscykeln för nätanslutningar, API:er, tekniska identiteter och skyddsprofiler, inte endast deras etablering. Säkerhetskrav och undantag försvinner inte för att handläggningen automatiseras.

**Generation 4** beskrivs genom godkända skapandemiljöer, avsiktsbaserade anslutningar, begränsade mandat och riskanpassat skydd. Tekniken kan dölja protokoll och nätverksdetaljer, men får inte dölja vem som ansvarar för data, externa tjänster och verksamhetseffekter.

Inga större omstruktureringar rekommenderas. Viss upprepning av att nätåtkomst, autentisering och verksamhetsmandat är olika saker är motiverad för att varje kapitel ska vara begripligt separat. Ändringarna är därför avgränsade och de fyra kapitlens huvudstruktur har behållits.

## Kvarstående frågor inför formellt godkännande

- Oberoende teknisk sakgranskning av konkreta produkter och genomförande av mandat-/policymekanismer i den valda miljön.
- Ansvar och kontrollmodeller vid externt förvaltade SaaS-/AI-tjänster behöver konkretiseras vid organisationstillämpning.
- Kontrollera övergripande termkonsekvens och upprepningar när samtliga förmågekapitel är färdigskrivna.
- Inget formellt godkännande av manuskapitlen har gjorts i denna revision.
