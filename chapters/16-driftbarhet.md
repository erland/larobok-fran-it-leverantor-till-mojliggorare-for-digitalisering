# Driftbarhet och motståndskraft

Förmågan *Driftbarhet och motståndskraft* ska erbjuda gemensamma tjänster för att upptäcka störningar, förstå deras konsekvenser och återställa fungerande IT-stöd. Enskilda servrar kan vara tillgängliga samtidigt som ett ärende, en betalning eller ett informationsutbyte har fastnat. Därför behöver erbjudandet omfatta både tekniska komponenter och de verksamhetsflöden som komponenterna tillsammans stöder.

Driftbarhet handlar om insyn och hantering under normal drift och vid incidenter. Motståndskraft handlar om att begränsa konsekvenser och kunna återhämta sig. Behoven är olika: ett internt hjälpverktyg kan tåla avbrott, medan ett tidskritiskt verksamhetsflöde kan kräva dokumenterade och regelbundet prövade återställningsförmågor.

## Vad den gemensamma förmågan behöver erbjuda

### Insamling av driftinformation och felsökning

Ett gemensamt stöd för loggar, mätvärden och distribuerade spårningar gör det möjligt att följa en begäran genom flera tjänster. Tjänsterna behöver standardiserade sätt att lämna ifrån sig signaler, gemensamma korrelationsidentifierare, sökbarhet, relevanta åtkomstregler och rimliga kostnads- och lagringsgränser. Instrumenteringen kan ske via körmiljöernas standardfunktioner och utvecklingsplattformens mallar; driftbarhetsförmågan erbjuder själva insamlingen, analysmöjligheterna och felsökningsstödet. [K008]

### Övervakning, tjänstekvalitet och larm

Erbjudandet behöver omfatta övervakning av tillgänglighet, svarstider, fel och köfördröjningar, men också möjligheten att mäta om hela verksamhetsflödet fungerar. För kritiska tjänster bör team kunna definiera tjänstekvalitetsmått och mål, ofta kallade SLI och SLO, samt få åtgärdbara larm. Larm behöver ha mottagare, prioritet och tydlig väg till incidenthantering. Fler instrumentpaneler gör ingen nytta om ingen ansvarar för att agera.

### Säkerhetskopiering och verifierad återställning

Gemensamma skydds- och återställningsprofiler bör ange vilka krav som gäller för återläsning och hur den ska provas. *Datahantering och informationslagring* kan utföra själva säkerhetskopieringen inom sina förvaltade datatjänster; driftbarhetsförmågan behöver stödja samordnad återställning av hela IT-stödet. Kraven ska komma från verksamhetens tolerans för informationsförlust och avbrott: RPO anger acceptabel dataförlust uttryckt i tid och RTO hur snabbt en tjänst behöver kunna återställas. En lyckad backupkörning räcker inte; återläsning och beroenden behöver provas.

I distribuerade system måste även beroenden beaktas. En databas kan återställas till ett tidigare läge, medan meddelanden redan har skickats till andra organisationer. Sökindex kan i vissa fall byggas upp på nytt, men en utförd extern handling kan kräva avstämning eller kompensation i stället för teknisk återställning.

### Återhämtning och teknisk spårbarhet

För mer kritiska flöden behövs stöd för återställningsordning, reservkapacitet, kontinuitetsövningar och samordning mellan beroende tjänster. Vissa lösningar behöver dessutom skyddade tekniska revisionsspår med särskilda krav på åtkomst, integritet och bevarande. Dessa ska inte blandas ihop med vanliga felsökningsloggar eller säkerhetsorganisationens hotdetektion. Alla tjänster behöver inte alla dessa funktioner, men deras tillgänglighet och villkor ska vara begripliga.

## Generation 3 – driftbarhet som en självbetjänad del av tjänstelivscykeln

I generation 2 kan den centrala driftorganisationen ha bra övervaknings- och backupverktyg men behöva konfigurera larm, samla loggar och genomföra återställning åt varje nytt applikationsteam. I generation 3 erbjuder plattformsteam förvaltade standardtjänster och profiler som kopplas till en ny tjänst med liten eller ingen manuell handpåläggning. Ett utvecklingsteam ska kunna se sin egen tjänsts tillstånd, undersöka fel, anpassa relevanta larm och initiera godkända återställningsmoment utan att få administratörsbehörighet till hela den gemensamma infrastrukturen.

Plattformsteamet ansvarar för att observability-, larm- och återställningstjänsterna fungerar, utvecklas och kan användas säkert. Produktteamet ansvarar för sin applikations instrumentering, tjänstekvalitetsmål och operativa åtgärder inom avtalade ramar. Vid störningar som sträcker sig över flera team behövs fortfarande gemensam samordning och tydligt ansvar för hela verksamhetsflödet. Självständiga team betyder alltså inte isolerade team eller avvecklad gemensam incidentförmåga.

## Generation 4 – driftbarhet utan krav på driftkompetens hos skaparen

När verksamheten själv skapar assistenter, automationer och mindre applikationer behöver driftbarhet ingå i godkända skapande- och publiceringsvägar. Den som skapar en lösning ska inte behöva konfigurera loggplattformar eller skriva egna återställningsskript. I stället behöver den gemensamma förmågan kunna ge behovs- och riskanpassade standardkontroller: insyn i om lösningen fungerar, begripliga felmeddelanden, användnings- och kostnadslarm, en ansvarig ägare och möjlighet att stoppa eller avveckla lösningen. Om exempelvis en egen automation slutar skicka påminnelser ska ägaren kunna se vilka körningar som misslyckats, pausa flödet och få vägledning om nästa steg. Ett nytt försök ska bara kunna göras direkt om det är säkert att upprepa åtgärden; annars behövs en väg till stöd eller incidenthantering.

En enkel personlig assistent kan tåla ett tillfälligt avbrott. En agent som får ändra uppgifter i ett verksamhetssystem kräver däremot tydligare händelsespårning, säkert stopp och väg för incidenteskalering. AI-tjänster kan ge tekniskt korrekta svarstider men ändå olämpliga resultat: själva utvärderingen av AI-beteendet erbjuds av *Analys, sökning och intelligent informationsbearbetning*, medan driftbarhetsförmågan ska kunna ta emot relevanta signaler och stödja hanteringen av upptäckta problem. All prompttext eller användarinformation ska inte samlas in slentrianmässigt.

Om en agent redan har utfört en åtgärd i ett annat system kan en återställd programversion inte automatiskt göra åtgärden ogjord. *Integration och informationsutbyte* behöver erbjuda spårbara anrop och stödjande integrationsmekanismer. Själva avstämningen eller kompensationen för en redan utförd verksamhetsåtgärd måste utformas och ägas av ansvariga för verksamhetsprocessen och IT-stödet. Kritiska lösningar kan behöva professionell drift och kontinuitetsplanering även om de ursprungligen skapades av verksamheten.

## Gräns mot övriga förmågor

Förmågan samlar driftssignaler, larm och återställningsstöd till en operativ helhet. Den samverkar med körmiljöer och datatjänster, men tjänstens ägare ansvarar för att verksamhetsflödet faktiskt fungerar.
