# Utveckling och teknisk leverans

En utvecklingsplattform ska göra det möjligt att genomföra förändringar säkert och självständigt – inte bara samla utvecklingsverktyg på ett ställe. Förmågan *Utveckling och teknisk leverans* erbjuder vägen från skapande och test till kontrollerad publicering, uppdatering och avveckling. I generation 3 är den utformad för professionella utvecklingsteam. I generation 4 behöver samma grund även stödja verksamhetsmedarbetare som skapar egna digitala lösningar.

## Gemensamma tjänster för professionell utveckling

### Källkod, bygg, test och leverans

Erbjudandet omfattar versionshantering av kod och konfiguration, kodgranskning, bygg- och testmiljöer, artefaktregister och automatiserade leveransflöden. Ett team behöver kunna se vilken förändring som ingår i en version, hur den testats och vad som faktiskt publicerats. Godkända mallar och färdiga leveransvägar för vanliga typer av IT-stöd minskar behovet av egna lösningar för paketering, konfiguration och release.

Utvecklingskedjan behöver skydda hemligheter och signeringsnycklar, kontrollera beroenden, ge spårbarhet från källkod till levererad artefakt och stödja granskning av förändringar. Säkerhetskontroller bör ingå i de ordinarie leveransvägarna, med synliga resultat och en dokumenterad väg för undantag. En automatiserad pipeline är däremot ingen garanti för säker kod, reproducerbara byggen eller felfri driftsättning. [K001, K010]

### Självbetjäning för förändringar och avveckling

Team ska kunna etablera utvecklings- och testmiljöer, ansluta godkända plattformstjänster, leverera nya versioner, undersöka misslyckade leveranser och avveckla sina lösningar utan att varje steg kräver en manuell beställning. Förmågan behöver erbjuda återställnings- och korrigeringsvägar som passar tjänstens risker. En programversion kan ibland rullas tillbaka snabbt; datamigreringar eller externt distribuerade klienter kan kräva andra åtgärder.

Utvecklingsplattformen ansvarar för att leveransvägen fungerar och tillämpar avsedda kontroller. Den skapar däremot inte i sig en robust applikation. Leveransvägen behöver samverka med *Applikationsexekvering och körmiljö* och *Driftbarhet och motståndskraft*, så att teamet kan följa en version från test till fungerande drift och hantera en misslyckad förändring.

## Generation 3 – från överlämning till teamets egen leverans

I generation 2 kan utvecklingsteam ha egna byggverktyg men ändå behöva lämna över releaser, miljöändringar och felsökning till centrala funktioner. Generation 3 förändrar uppdraget för det gemensamma utvecklingsplattformsteamet: det förvaltar en intern produkt med dokumenterade, säkra och användbara leveransvägar, inte en kö av manuella leveransuppdrag. [K002]

Det professionella teamet kan därmed självt bygga, testa, publicera, följa upp leveransfel, ändra och avveckla sin tjänst inom givna ramar. Plattformsteamet ansvarar för kvalitet och vidareutveckling av leveranstjänsterna; produktteamet ansvarar för applikationens kod, funktion och förändringar. Gemensam granskning kan fortfarande behövas för förändringar med särskilt höga konsekvenser. Det avgörande är att normalfallet inte kräver ett överlämnande.

## Generation 4 – en skapandemiljö som också fungerar efter publicering

När verksamhetsmedarbetare kan skapa assistenter, automationer och applikationer med AI-stöd eller visuella verktyg behöver erbjudandet bli mer behovsstyrt. Användaren ska kunna beskriva vad lösningen ska göra och få hjälp att välja godkända mallar, dataanslutningar och funktioner utan att själv välja källkodsverktyg, körmiljö eller integrationsprotokoll. Förmågan behöver därför erbjuda begripliga skapandemiljöer, teststöd och kontrollerade publiceringsvägar.

En sådan miljö måste också hantera tiden efter publicering. Erbjudandet behöver registrera ägare, versioner, beroenden och användning samt stödja ändringar, överlåtelse och avveckling. AI-genererad kod behöver genomgå relevanta kod- och säkerhetskontroller. För lösningar som använder AI ska leveransvägen kunna kräva och ta emot utvärderingsresultat från *Analys, sökning och intelligent informationsbearbetning*; själva AI-utvärderingstjänsterna beskrivs där.

Skapandemiljön behöver även göra lösningens ekonomiska konsekvenser synliga före delning och publicering. En enkel app kan rymmas inom befintliga licenser när den provas av en person men kräva nya användarlicenser, betalda anslutningar eller löpande AI- och API-förbrukning när den sprids. Den som skapar lösningen bör kunna se vilka delar som ingår, få en begriplig uppskattning av tillkommande kostnader och möta automatiska budget- eller förbrukningsgränser där det är möjligt. Större ekonomiska åtaganden behöver en godkänd beslutsväg, utan att varje liten förändring blir ett separat inköpsärende. Vid val av skapandemiljö behöver organisationen även väga in licensmodell och möjligheten att exportera eller återskapa lösningar om plattformen ska lämnas; kod, data, flöden och agentkonfiguration går inte alltid att flytta utan omarbete. [K009]

Det gemensamma erbjudandet bör skilja mellan tre användningsnivåer:

| Användning | Vad leveransvägen behöver ge |
|---|---|
| Personligt experiment | Avgränsad testmiljö, begränsad åtkomst och enkel radering. |
| Delad verksamhetslösning | Identifierad ägare, tester, godkända anslutningar, kontrollerad publicering och möjlighet att ta över förvaltningen. |
| Verksamhetskritisk eller särskilt skyddsvärd lösning | Fördjupad prövning, professionell utveckling eller förvaltning där det behövs, och högre krav på spårbarhet och kontinuitet. |

När en verksamhetsskapad app publiceras ska den godkända leveransvägen också koppla den till en skyddad kör- eller klientprofil med obligatoriska resurs- och åtkomstbegränsningar. Skaparen ska inte kunna kringgå profilens skydd bara genom ett annat publiceringssätt. Kontrollerna måste fortsätta gälla efter driftsättning; de ersätter inte uppföljning av den körande lösningen.

Det är lösningens användning, information och möjliga konsekvenser som avgör kontrollnivån, inte vem som byggt den. Om ett personligt experiment börjar delas brett eller får tillgång till känsliga uppgifter ska dess ägarskap, granskning och leveransväg kunna omprövas. Den godkända leveransvägen behöver ansluta tjänster för identitet, integration och säkerhetsskydd; mandat- och behörighetskontrollerna måste också verkställas av de verksamhetstjänster som anropas.

Förmågan behöver även stödja överlämning till professionell förvaltning genom export eller dokumentation av kod, konfiguration, beroenden och ägarskap när verktygen medger det. Överlämningen kan kräva ombyggnad; den får inte förutsättas vara automatisk.

## Gräns mot övriga förmågor

Den generella leveransvägen samlar godkända specialisttjänster i ett begripligt arbetsflöde. Varje specialistförmåga ansvarar fortsatt för sin tjänst och sina kontroller.
