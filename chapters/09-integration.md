# Integration och informationsutbyte

När IT-stöd består av flera tjänster och behöver samverka med andra organisationer blir informationsutbytet en del av tjänstens funktion och tillförlitlighet. Förmågan *Integration och informationsutbyte* ska erbjuda gemensamma sätt att exponera funktioner, överföra information och hantera förändringar och fel mellan självständiga system. Den ska inte äga verksamhetssystemens innehåll eller samla deras affärsregler i en central integrationsmotor.

## Vad det gemensamma erbjudandet behöver omfatta

### API:er och tjänsteanrop

För synkrona anrop behövs stöd för att publicera, upptäcka och konsumera API:er. Det kan omfatta API-katalog, gateway, teknisk kontroll av anrop, trafikbegränsning, kontraktsbeskrivningar, versionshantering och uppföljning. Gatewayens kontroller kan avvisa otillåtna klienter eller anrop men ersätter inte mottagarens prövning av verksamhetsbehörighet. En gateway ska användas där den ger värde; varje internt anrop behöver inte passera en central produkt. Tjänsten behöver också stöd för testning av kompatibilitet när ett gränssnitt ändras. Ett tekniskt korrekt schema garanterar inte att ett fält har oförändrad verksamhetsbetydelse.

### Meddelanden och händelser

För asynkront utbyte behövs förvaltade köer, publicering och konsumtion av händelser samt, där användningskraven motiverar det, händelseströmmar med återspelning och flera oberoende konsumenter. Tjänsterna ska erbjuda tydliga regler för leverans, ordning, retention, felköer, återförsök, kvittens och spårbarhet. Återförsök kan skapa dubbletter. Plattformen behöver därför ge stöd för idempotent behandling och felutredning, medan mottagande tjänst måste hindra otillåtna dubbla verksamhetseffekter. Om meddelandet är del av ett långlivat flöde behöver processförmågan dessutom avgöra vilket steg svaret hör till och hur ett uteblivet eller sent svar ska hanteras.

När en applikation både ändrar sin databas och publicerar ett meddelande kan den ena operationen lyckas och den andra misslyckas. Integrations- och utvecklingstjänsterna behöver ge stöd för tillförlitliga publiceringsmönster, exempelvis transaktionell utkorg där det är lämpligt. Ett löfte om exakt en gång i en meddelandetjänst innebär inte automatiskt exakt en verksamhetseffekt i hela kedjan.

### Filutbyte, externa parter och särskilda anslutningar

För utbyte med externa organisationer kan förvaltad filöverföring, kvittenser, validering av filformat, kryptering, autentisering och övervakade leveransflöden vara fortsatt rätt lösning. Gemensamma adaptrar och protokollstöd kan minska behovet av speciallösningar. Det behövs också stöd för externa anslutningsvillkor och, där arbetet kräver det, synkronisering för mobila eller frånkopplade klienter. Vid offline-synkronisering måste motstridiga ändringar hanteras enligt verksamhetens regler; tekniken kan inte på egen hand avgöra vilket innehåll som är korrekt.

### Kontrakt och driftbarhet genom hela kedjan

En användbar integrationstjänst omfattar mer än transport. Den behöver kunna visa gränssnittets ägare, avsikt, version, kända konsumenter, tillgänglighetsvillkor och hur förändringar meddelas. Loggar, korrelations-ID:n och gemensamma felsökningsvyer ska hjälpa team att följa en händelse över flera system utan att känsliga nyttolaster eller åtkomstbevis behöver exponeras i loggarna. Tjänsten måste stödja kontrollerad åtkomst till felköer, säkert återspelande och avveckling av integrationer som inte längre används. Plattformen kan inte garantera att alla okända konsumenter upptäcks eller att redan genomförda externa åtgärder kan ångras.

## Gränsen mot datahantering och andra förmågor

Förmågan *Datahantering och informationslagring* erbjuder ETL/ELT, datapipelines och tjänster för att skapa, kvalitetssäkra, historisera och publicera förvaltade datamängder, exempelvis i warehouse och lakehouse. Integrationsförmågan erbjuder i stället systemgränssnitt och transportmekanismer – API:er, meddelanden, händelser och filöverföring – som sådana flöden kan använda. Enkel protokoll- eller formatöversättning för ett operativt utbyte hör ofta hit; analytisk transformation och datamodellering hör till datahanteringen. Samma tekniska verktyg kan stödja båda uppgifterna.

*Process, workflow och ärendehantering* erbjuder tekniskt stöd för processinstanser, väntelägen och beslutspunkter; verksamheten äger processens utformning och beslut. Integrationsplattformen ska inte ta över denna orkestrering. *Identitet och tillit* och *Cybersäkerhet och tekniskt skydd* tillhandahåller grundläggande identitets- och skyddstjänster som integrationsförmågan måste tillämpa. Ett API-kontrakts verksamhetsbetydelse ägs av den tjänst som erbjuder funktionen, även när själva publiceringen sker via en gemensam plattform. En dataanslutning till ett lakehouse är inte samma sak som ett verktyg som får ändra ärendestatus.

## Generation 3 – från integrationsbeställningar till teamens egen livscykel

I en organisation i generation 2 kan ett centralt integrationsteam behöva bygga och ändra varje API-koppling, kö, filflöde och adapter. Det ger specialiststöd men kan också göra teamens förändringar beroende av en central leveranskö. I generation 3 erbjuder plattformsteamet i stället säkra standardtjänster, API- och händelsekataloger, utvecklingsmallar, testmiljöer och automatiserad etablering. Behöriga utvecklingsteam kan själva skapa, driftsätta, övervaka, felsöka, förändra och avveckla sina normala integrationer.

Det centrala teamet övergår därmed från obligatorisk utförare till produktansvarig för integrationsförmågan: kvaliteten på tjänsterna, säkerhetsramarna, uppgraderingar och stöd till konsumenterna. Det tar inte över ägandet av verksamhetens gränssnitt. Självbetjäningen måste omfatta mer än att beställa en ny kö – också versionering, felhantering, åtkomständringar och avveckling behöver fungera utan att varje steg blir ett specialistärende. Komplexa externa utbyten kan fortfarande kräva gemensamt specialistarbete.

## Generation 4 – anslutningar utifrån verksamhetens avsikt

När verksamhetsmedarbetare skapar egna assistenter, automationer och mindre applikationer bör de kunna välja godkända verksamhetsfunktioner utifrån avsikt, inte API-protokoll eller kötyp. Integrationsförmågan erbjuder därför en katalog med exempelvis ”hämta ärende”, ”visa aktuellt beslut” och ”skapa utkast”. Bakom funktionerna finns förvaltade API:er, adaptrar och andra tekniska anslutningar. Varje funktion behöver beskriva sitt syfte, sina in- och utdata, sin ägare och vilka behörigheter och användningsbegränsningar som gäller.

Skillnaden är viktig mellan att läsa information och att ändra verksamhetens tillstånd. En assistent kan exempelvis tillåtas söka efter ett ärende och sammanställa ett svar, medan ett verktyg som verkställer ett beslut eller betalar ut pengar kräver särskilt mandat, prövning och ibland mänskligt godkännande. Behörighet och ändamål måste kontrolleras i betrodda system, inte enbart genom instruktioner till AI-modellen. Även fördröjda eller köade åtgärder behöver kunna kopplas till sitt uppdrag och kontrolleras vid verkställighet när risken motiverar det.

Godkända verksamhetsfunktioner ska vara valbara i skapandemiljön utan att användaren hanterar API-nycklar. Integrationsförmågan svarar för kontrakt, anropskontroller och spårbarhet; den mottagande tjänsten prövar åtgärdens tillåtlighet. När en funktion ändras eller återkallas behöver berörda lösningar kunna identifieras. Den generella publiceringen av dessa lösningar beskrivs i *Utveckling och teknisk leverans*.
