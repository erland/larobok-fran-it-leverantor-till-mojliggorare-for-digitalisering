# Applikationsexekvering och körmiljö

Förmågan *Applikationsexekvering och körmiljö* ska erbjuda förvaltade miljöer där applikationer och arbetslaster kan köras med kända egenskaper, utan en unik teknisk installation för varje IT-stöd. Behovet kan gälla ett äldre verksamhetssystem, ett API, ett schemalagt jobb eller en verksamhetsskapad applikation.

Körmiljön ansvarar för exekveringens tekniska förutsättningar, inte för att bygga applikationen eller garantera dess funktion. Valet ska utgå från arbetslastens krav, inte från vilken teknik som uppfattas som modern.

## Körmiljöer som gemensamma tjänster

### Flera typer av arbetslaster

Olika arbetslaster kan kräva olika tjänster:

| Körmiljötjänst | Typiska behov |
|---|---|
| Virtuella maskiner och applikationsservrar | System med operativsystem-, middleware- eller äldre teknikberoenden. |
| Containerplattformar | Paketerade tjänster som behöver isolering, orkestrering, skalning och kontrollerade uppdateringar. |
| Förvaltade applikationsplattformar (PaaS) | Applikationer och API:er som kan köras utan att teamet själv administrerar servrar eller containerplattform. |
| Serverlös och händelsestyrd körning | Funktioner som aktiveras av anrop eller händelser och förbrukar resurser efter behov. |
| Batch- och beräkningsplattformar | Schemalagda, parallella eller resurskrävande jobb som behöver köhantering och omkörning. |
| Specialiserad AI-exekvering | Modellservering, inferens eller träning med särskilda krav på exempelvis acceleratorer och minne. |

Kategorierna överlappar: en förvaltad applikationsplattform kan använda containrar, och serverlösa funktioner kan vara containerbaserade. De är inte sex obligatoriska produkter, och en traditionell applikationsserver kan fortfarande vara rätt val. Förmågan ska erbjuda eller säkerställa tillgång till lämpliga körprofiler efter arbetslastens krav.

### Vad tjänsterna behöver omfatta

Varje körprofil behöver ange vilka arbetslaster och versioner som stöds, kapacitetsgränser, erbjuden teknisk tillgänglighet och villkor för uppgraderingar. Körmiljön ska erbjuda isolering, säker grundkonfiguration och anslutning till gemensam hantering av hemligheter samt tydligt ansvar för operativsystem, grundbilder, runtime-versioner och patchning. Plattformens tillgänglighet är dock inte detsamma som ett helt IT-stöds kontinuitet. Anslutning till godkända data- och integrationstjänster ska ske genom återanvändbara lösningar, inte specialkonfiguration för varje team.

Erbjudandet ska omfatta start, stopp, resursändring och avveckling samt, där det behövs, skalning, hälsokontroller och kontrollerade uppdateringar. Teamen behöver kunna se körstatus, resursförbrukning och relevanta fel utan att få administratörsrättigheter till den delade plattformen. Körmiljön ska exponera loggar, mätvärden och händelser som kan tas om hand av *Driftbarhet och motståndskraft*. En plattform som kan starta flera instanser gör dock inte automatiskt en tillståndsbunden applikation skalbar.

För batchkörning behövs schemaläggning, tidsgränser, återförsök och kontrollerade omkörningar. Applikationen måste fortfarande hantera risken att en åtgärd utförs två gånger.

### Körmiljöer bakom andra plattformstjänster

Dataflöden och analytiska jobb behöver beräkningskapacitet, AI-modeller kan behöva specialiserad exekvering och integrationslösningar kan starta kortlivade funktioner när en händelse inträffar. Körmiljön kan då ingå i en färdig tjänst som erbjuds av *Datahantering och informationslagring*, *Analys, sökning och intelligent informationsbearbetning* eller *Integration och informationsutbyte*. Användaren behöver inte alltid se eller själv välja den underliggande körmodellen.

Gränsen går vid själva exekveringen. Integrationsförmågan förmedlar exempelvis en händelse; körmiljön kan starta en funktion som behandlar den. Dataplattformen ansvarar för sin databehandling och AI-förmågan för modell- och AI-tjänster, även när de använder körkapacitet som ytterst bygger på samma infrastruktur.

## Generation 3 – från miljöbeställning till självbetjänad exekvering

I generation 2 kan ett centralt driftteam behöva genomföra etablering och ändringar även när infrastrukturen är standardiserad. I generation 3 erbjuder körmiljöteamet i stället förvaltade standardprofiler för olika arbetslaster via självbetjäning. Produktteamen kan själva driftsätta, ändra, skala, felsöka och avveckla sina arbetslaster inom fastställda ramar.

Körmiljöteamet ansvarar för plattformens säkerhet, kapacitet, uppgraderingar och tjänstenivåer. Produktteamet ansvarar för applikationens funktion och konfiguration samt för att använda plattformens felsökningsstöd. Specialfall kan fortfarande kräva specialistinsatser, men normalt arbete ska inte fastna i en central ändringskö. Förflyttningen handlar om ansvar och tillgänglighet, inte om ett obligatoriskt byte från virtuella maskiner till containrar.

## Generation 4 – körmiljö efter behov, inte teknikval

I generation 4 bör den som skapar en lösning ange vad den ska göra, hur ofta den används och vilka krav som finns på skydd, svarstid och tillgänglighet. En godkänd skapandemiljö kan förmedla dessa behov till ett lämpligt körmiljöerbjudande, som föreslår eller tilldelar en godkänd profil med tydliga resurs-, kostnads- och livslängdsgränser. Användaren ska normalt inte behöva välja mellan virtuell maskin, container, PaaS eller serverlös körning – och ibland ingår exekveringen redan i den tjänst som används.

När många verksamhetsskapade applikationer körs samtidigt behöver plattformen skydda såväl andra arbetslaster som sina egna delade resurser. Godkända körprofiler bör därför begränsa processor, minne, lagring, antal samtidiga körningar, körtid och skalning där det är relevant. Kvoter behöver kunna gälla både per app och samlat för en verksamhetsgrupp eller delad miljö. Plattformen ska kunna upptäcka överdriven förbrukning och begränsa eller stoppa en arbetslast, utan att utlova att alla störningar kan förhindras. Sådana skydd får inte vara beroende av att den som skapat lösningen känner till containerteknik eller kapacitetshantering. [K005, K006]

En enkel automation kan till exempel tilldelas händelsestyrd körning med kostnadstak, medan en kontinuerligt använd tjänst kan få en annan profil. Höga krav på tillgänglighet eller informationsskydd kan kräva särskild prövning och en mer robust tjänst. Det är lösningens faktiska risker som styr, inte om den skapats av en professionell utvecklare eller en verksamhetsmedarbetare.

Skyddsklassning och kritiska undantag måste fortfarande prövas av ansvariga funktioner; en AI-genererad behovsbeskrivning är inte ett skyddsbeslut. Resursisolering i körmiljön skyddar inte automatiskt mottagande verksamhetssystem mot felaktiga eller mycket täta API-anrop. Godkända integrationsfunktioner och anslutningar behöver därför komplettera skyddet med relevanta anrops- och belastningsgränser.

En assistent som körs i en godkänd molntjänst behöver dessutom ingen separat intern körmiljö. Där blir leverantörens tjänstevillkor och organisationens kontroll av den externa tjänsten avgörande.

## Gräns mot övriga förmågor

Körmiljöförmågan erbjuder exekveringsprofiler och resurser. Leveransvägen tillhandahålls av *Utveckling och teknisk leverans* och gemensam övervakning och återhämtning av *Driftbarhet och motståndskraft*. Det behöver inte vara separata tekniska produkter.
