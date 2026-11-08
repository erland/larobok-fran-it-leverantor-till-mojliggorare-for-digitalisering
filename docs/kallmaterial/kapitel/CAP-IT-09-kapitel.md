# Driftbarhet och motståndskraft

*CAP-IT-09 · Faktaboksunderlag · version 3.0, 7 november 2026*

Många organisationer har delat upp stora system i mindre tjänster, men inte fullt ut anpassat driften till den nya arkitekturen. Det är i den situationen kapitlet tar sin början. Generation 2 beskriver här en **typ av arkitektur och arbetssätt**, inte ett intyg på att alla nödvändiga förmågor finns på plats.

## Vad förmågan handlar om

En digital tjänst kan vara välbyggd och ändå sluta fungera. En databas kan bli otillgänglig, ett certifikat gå ut, en kö börja växa eller en förändring få en oväntad följd. Det som avgör hur allvarlig händelsen blir är inte bara om något går sönder, utan om organisationen upptäcker problemet, förstår vad som påverkas och kan återställa en fungerande tjänst. **Driftbarhet och motståndskraft** är den samlade tekniska förmågan att göra detta möjligt.

Driftbarhet handlar om att kunna observera, felsöka och hantera ett IT-stöd när det används. Motståndskraft handlar om att begränsa störningars konsekvenser och återhämta sig när de inträffar. Hur väl systemet från början är byggt för att tåla fel påverkas också av andra förmågor, framför allt applikationsarkitektur, körmiljö och datahantering. Båda behöver relateras till verksamhetens behov. En tillfällig störning i en intern visningstjänst kan vara acceptabel; samma störning i ett tidskritiskt handläggningsflöde kan få stora konsekvenser.

Förmågan omfattar fem slags stöd: insamling och analys av tekniska signaler, övervakning och åtgärdbara larm, säkerhetskopiering och återställning, återhämtning efter större avbrott samt särskilda tekniska revisionsspår för händelser som måste kunna granskas i efterhand. Den sistnämnda funktionen är **inte samma sak som vanlig driftloggning** och behövs i den omfattning som risk, tillsyn och spårbarhetskrav motiverar. Dessa funktioner behöver inte alltid levereras från en gemensam plattform. Ett enskilt system kan ha väl fungerande backup, övervakning och manuell återställning utan en avancerad central driftplattform.

Förmågan ska däremot inte förväxlas med den körmiljö som faktiskt exekverar applikationen eller med utvecklingsverktygen som bygger och levererar den. Inte heller är vanlig felsökningsloggning, en skyddad teknisk revisionskedja och säkerhetsorganisationens hotdetektion samma sak. De kan använda närliggande data men har olika syften, åtkomstkrav och ansvar.

För att göra skillnaden mellan de fyra generationerna begriplig följer vi ett återkommande exempel: ett ärendehanteringsstöd där medborgare lämnar in ärenden, handläggare fattar beslut och verksamheten behöver kunna fortsätta arbeta även när delar av IT-miljön fallerar.

## Avgör först hur relevant förmågan är

Alla organisationer som använder digitala stöd har någon form av behov av driftbarhet, men behovet av avancerade tjänster varierar. Börja med **konsekvenserna av fel**, inte med vilka verktyg som råkar finnas. Hur länge kan ett ärendeflöde ligga nere innan det påverkar människor, rättssäkerhet, intäkter eller arbetsmiljö? Hur mycket inmatad information kan förloras? Behöver händelser kunna rekonstrueras flera år efteråt? Kan verksamheten fortsätta manuellt under ett längre avbrott?

För en liten, fristående lösning kan rimligt stöd vara en ansvarig person, dokumenterade återställningssteg, automatiska säkerhetskopior och enkla kontroller att tjänsten är tillgänglig. För en tjänst som många andra system är beroende av krävs normalt mer: mätning av användarupplevelse, beroendeöversikt, gemensam incidenthantering och återställningstest av hela tjänstekedjan. För en plattform som hundratals team använder behöver skydd och övervakning bli standardiserade erbjudanden.

Det är avgörande att skilja på tre beslut: **(1)** vilken funktion som måste finnas, **(2)** om funktionen bör erbjudas gemensamt, och **(3)** hur automatiserat stödet behöver vara. Att möjligheten att återställa ett register är kritisk betyder inte automatiskt att organisationen behöver köpa en separat gemensam backupplattform. Och en organisation med avancerad observability behöver ändå veta vem som tar hand om ett larm och vem som avgör att ett ärende återigen är korrekt.

## Tillbakablick: generation 1 och steget mot distribuerade IT-stöd

När IT-stöden var relativt sammanhållna kunde driftorganisationen ofta följa applikationsserver, databas, jobb och några integrationer som ett avgränsat system. En tydlig systemförvaltning, systemnära loggar, serverövervakning, dokumenterade återstartssteg och verifierad backup kunde ge fullt tillräckligt stöd. Detta var inte i sig en sämre arkitektur: den var anpassad till färre tekniska beroenden. Systemkritikaliteten avgjorde hur långt man behövde gå med tillgänglighet och återställning.

När applikationerna delades upp i mindre tjänster ökade antalet anrop, köer, gränssnitt, team och felvägar. **Det som förändrades först var ofta applikationsarkitekturen, inte driftverktygen eller ansvarsfördelningen.** Traditionell komponentövervakning och manuella återstartsrutiner kunde därför leva kvar i den nya tekniska miljön. Att ett system består av små tjänster betyder inte att övergången till ett fungerande distribuerat driftsätt är genomförd.

### Arvet från övergången 1→2 – tecken att känna igen

- Varje server har övervakning, men ett ärende kan fastna utan att ett tydligt larm utlöses.
- Incidenter kräver möten mellan flera team för att avgöra vilket API, vilken kö eller datatjänst som orsakar problemet.
- Loggar finns, men gemensamma tidsuppgifter och korrelations-ID:n saknas.
- Backup fungerar per databas, men det är oklart hur en hel verksamhetskedja ska återställas konsistent.
- Nyckelpersoner kan lösa problem som inte är dokumenterade eller möjliga att reproducera.

Detta är **kvarvarande brister från 1→2**, inte automatiskt argument för att bygga en ny stor plattform. De behöver kunna åtgärdas även om organisationen väljer att fortsätta arbeta i generation 2.

### När den äldre tekniken är olämplig

Ett systemnära övervakningsverktyg behöver inte ersättas bara för att tjänsterna blivit fler. Men om det saknar möjligheter att exportera relevanta signaler, korrelera händelser eller uppfylla krav på dataskydd och support kan det ha blivit olämpligt för den nya miljön. På samma sätt är en säkerhetskopieringsprodukt som saknar stöd för samordnad återställning av kritiska beroenden en risk när flera datatillstånd måste återskapas tillsammans. Bedöm först om teknik, konfiguration eller arbetssätt är problemet.


## Generation 2 – många tjänster skapar gemensamma felkedjor

### När förmågan är relevant

När ärendehanteringen delas i ett webbgränssnitt, ett ärende-API, tjänster för dokument och beslut, köer och flera datalager kan delarna var för sig se friska ut medan ärendet ändå inte går igenom. En störning kan visa sig långt från sin ursprungliga orsak. Denna utveckling gör driftbarheten central även om varje enskild komponent är relativt enkel.

### Vilket stöd som behöver finnas

Organisationen behöver kunna följa en användaraktivitet genom flera tjänster. Det innebär bland annat gemensamma tidsreferenser och korrelationsidentifierare, loggar och mätvärden på flera nivåer samt möjlighet till distribuerad spårning där beroendena motiverar det. Övervakningen behöver mäta om det **viktiga verksamhetsflödet lyckas**, inte bara om servrar och processer är igång. En kö som tar emot meddelanden men inte levererar dem i tid måste kunna synas som ett verksamhetsproblem.

Återställning blir också svårare. En backup av databasen räcker inte alltid om meddelandekön eller andra skrivande tjänster har fortsatt arbeta utifrån ett senare informationsläge. Team behöver identifiera konsistensgränser, auktoritativa datakällor och rätt återstartsordning. Ett sökindex kan ofta byggas upp igen, medan ett redan genomfört externt meddelande kan kräva avstämning eller kompensation; allt går inte att återställa med en gemensam tidpunkt. Vid viktiga flöden behöver flera team öva tillsammans. Gemensamma verktyg blir ofta värdefulla, men kan inte ersätta tydliga tjänsteavtal, ansvar och relevanta signaler i applikationskoden.

### Ansvar och vanliga fallgropar

Varje tjänsteteam kan ansvara för sin del, men någon måste också ansvara för att användarens hela ärendeflöde fungerar. En klassisk fallgrop är den **gröna instrumentpanelen**: fem team visar friska tjänster men inget team ser att den samlade tjänsten har slutat fungera. En annan är att central logginsamling införs utan genomtänkt dataskydd, retention eller förmåga att koppla ihop händelserna.

### Indikatorer på olämpliga teknik- och plattformsval

Varningssignalerna gäller **ändamålsenlighet i en distribuerad miljö**, inte hur ny en produkt är:

- **Funktion och interoperabilitet:** logg- och övervakningsverktyg visar enskilda servrar men kan inte koppla samman ärenden, anrop och köer över flera tjänster.
- **Återställningsstöd:** backuplösningen kan återläsa databasinstanser men saknar en prövad metod för beroenden, händelser och konsistens mellan delsystem.
- **Integration och säkerhet:** central insamling kräver osäkra undantag, ger ohanterliga datakopior eller gör åtkomst och retention svåra att styra.
- **Kostnad och skalbarhet:** licens-, lagrings- och driftkostnader växer oproportionerligt med antal tjänster eller insamlade signaler.
- **Leverantörsberoende:** data kan inte exporteras i användbara format eller leverantörens livscykel gör framtida utveckling riskfylld.

**Diagnos:** Är problemet att den distribuerade lösningen inte kan observeras och återställas – eller att det är dyrt och långsamt att ge samma stöd till nästa team? Det första är oftast ett kvarvarande G1→G2-gap; det andra kan tala för G2→G3. Båda kan finnas samtidigt.

### Två skilda förbättringsspår i generation 2

**Spår A – färdigställ den distribuerade förmågan.** Utse ansvar för sammanhängande flöden, inför korrelations-ID:n, skapa relevanta användarflödesmått och genomför gemensamma återställningsövningar. Dessa förbättringar behövs även utan ny central plattform.

**Spår B – minska upprepad manuell hantering.** När många team begär samma instrumentering, larm och skydd kan organisationen standardisera profiler, automatisera provisionering och bygga självbetjäning. Det är en genuin förflyttning mot generation 3.

Börja inte med ett stort plattformsbyte innan det är klart vilket spår som skapar störst nytta. Åtgärder i spår A kan ofta byggas in i spår B, så att organisationen undviker att investera två gånger.

### Indikatorer på tillräckligt stöd

Vid en övning går det att följa ett ärende som fastnar genom flera anrop och avgöra var felet uppstod. Ett larm om verklig användarpåverkan når en namngiven mottagare som kan samordna rätt team. Återställningsprov visar att information och processläge hänger ihop efter återstart. Organisationen följer utvecklingen av upptäckts- och återställningstid **för jämförbara incidenter**, snarare än att enbart räkna antal larm. Ett enstaka lyckat prov räcker inte: kontrollera att arbetssättet också fungerar vid personalbyte och återkommande förändringar.

## Från nuläge till nästa utvecklingssteg

### Åtgärda kvarvarande G1→G2-brister – utan att invänta generation 3

Den tekniska uppdelningen i tjänster kan redan vara genomförd trots att gemensam incidenthantering, spårning, beroendekartläggning och återställning inte fungerar. Dessa brister behöver identifieras öppet. Vid ett kritiskt verksamhetsflöde bör man kunna visa: vilken tjänst bröt kedjan, vem samordnar incidenten och hur återställs ett konsekvent informationsläge? Om svaret saknas är det en **grundläggande åtgärd i dagens arkitektur**, inte ett argument för att nästa plattform automatiskt ska lösa problemet.

Det är möjligt att kombinera detta med framtida standardisering, men själva problembilden måste vara tydlig: en ny central övervakningstjänst kommer inte att skapa meningsfulla applikationssignaler eller ansvar för helheten av sig själv.

### Från generation 2 till 3 – när den manuella modellen inte längre skalar

**Förändringsindikatorer.** Många likartade larm- och backupupplägg byggs om i varje projekt, onboarding tar lång tid, och samma manuella uppgifter återkommer vid varje driftsättning. Specialbeställningar gör att kvaliteten varierar mellan teamen. Det är en annan drivkraft än att själva tjänstekedjan ännu inte är begriplig.

**Vad som behöver förändras.** Gör de återkommande behoven till dokumenterade, versionerade och förvaltade tjänster. Ett normalfall ska kunna få rätt instrumentering, skyddsprofil och larmväg genom ett automatiserat flöde. Plattformsteamet ansvarar för mekanismen och dess livscykel; applikationsteamen ansvarar för domänspecifika signaler, beroenden och verksamhetsnära återställning.

**Beredskapsindikatorer.** Det finns tillräckligt många liknande behov, ett tydligt produktansvar för tjänsten, tekniska möjligheter att automatisera normalfallen och en avtalad fördelning av ansvar och support. Om de saknas bör man börja med gemensamma mallar, begränsade piloter och förbättrade gränssnitt i befintlig teknik.

**Beslutsregel.** Åtgärda akuta säkerhets- och återställningsbrister direkt. Etablera gemensam självbetjäning där återkommande användning och faktisk minskning av ledtid motiverar investeringen. Gör båda samordnat när samma lösning kan ge båda effekterna.



## Generation 3 – driftbarhet erbjuds som en plattformsprodukt

### När förmågan är relevant

När organisationen har många utvecklingsteam blir det ohållbart om varje nytt IT-stöd kräver en egen serie beställningar om loggning, larm, backup, behörigheter och återställningsrutiner. En gemensam teknisk plattform blir då värdefull först när den också levererar **användbara tjänster** med kända egenskaper, inte bara installerad teknik.

### Vilket stöd som behöver finnas

Nya applikationer ska i normalfallet få grundläggande loggar, mätvärden, spårning och larmprofiler automatiskt via godkända utvecklingsgrunder och körmiljöer. Teamet ska kunna välja en backup- och återställningsprofil utifrån verksamhetens tolerans för dataförlust (**RPO**) och återställningstid (**RTO**), tillsammans med informations- och riskklass. RPO och RTO måste sättas med verksamheten och verifieras i prov; de bestäms inte av teknikleverantören ensam. För viktiga verksamhetsflöden används definierade **SLI** (mätetal för tjänstens kvalitet, exempelvis andelen lyckade ärendeinlämningar) och **SLO** (målsatt nivå för mätetalet under en viss period). Larm bör fokusera på betydande och åtgärdbara avvikelser, inte varje teknisk förändring.

Plattformen behöver erbjuda dokumenterade gränssnitt, livscykel, kapacitetsgränser, åtkomststyrning och stöd för återställningsprov. Självbetjäning förutsätter att den bakomliggande leveransen faktiskt är automatiserad. En portal som bara skickar vidare manuella ärenden är inte samma sak.

### Ansvar och vanliga fallgropar

Plattformsteamet ansvarar för den gemensamma mekanismen och dess kvalitet: att loggar samlas in, larm kan routas och backup-profiler fungerar. Produktteamet ansvarar för applikationens meningsfulla mätvärden, sina kvalitetsmål och att verksamhetsinformationen kan användas efter återställning. Verksamhetsägaren ansvarar för konsekvensnivå och prioriteringar. Risker uppstår när plattformen blir en flaskhals, när alla tjänster får samma överdimensionerade skyddsprofil eller när ingen har ansvar för återställningen av helheten.

### Indikatorer på olämpliga teknik- och plattformsval

- **Automatiserbarhet:** plattformen saknar fungerande API:er, deklarativ konfiguration eller säkra integrationspunkter för standardiserad provisionering.
- **Självbetjäning:** en portal ser modern ut men bakom varje knapp väntar samma manuella beställning och specialhantering som tidigare.
- **Produktens användbarhet:** team måste lära sig många plattformsspecifika detaljer innan de kan få grundläggande loggning, larm eller backup.
- **Gemensam risk:** plattformen skapar ett centralt felområde utan prövad återhämtningsplan, rimlig isolering eller kapacitetsstyrning.
- **Livscykel och kostnad:** standardprofiler kan inte versionshanteras, migreras eller följas upp per konsument, och kostnaderna kan inte relateras till nyttan.

Sådana tecken behöver inte alltid leda till produktbyte. De kan bero på hur produkten införts, om standardprofiler saknas eller om organisationen behandlar plattformen som en installation i stället för en förvaltad intern produkt.

### Indikatorer på tillräckligt stöd

Ett nytt utvecklingsteam kan skapa en normal tjänst och få relevant instrumentering och skydd utan specialbeställning. Det går att se tjänstens överenskomna kvalitet och vem som äger den. Återställningsprov är regelbundna och visar faktisk återhämtning, inte enbart lyckade backupjobb. Plattformens eget bortfall och kapacitetsbegränsningar har testats eftersom gemensam teknik också innebär gemensamma beroenden.

## När generation 3 behöver kunna stödja fler lösningsskapare

### Från generation 3 till 4 – när fler än IT:s utvecklingsteam skapar lösningar

**Förändringsindikatorer.** Verksamheten börjar skapa arbetsflöden, mindre appar och AI-lösningar i sådan omfattning att de ordinarie plattformstjänsterna inte längre ger tillräckligt stöd för ägarskap, skydd, återställning eller säkert stopp. En tekniskt tillgänglig AI-tjänst kan samtidigt ge felaktiga eller otillåtna verksamhetsutfall.

**Vad som behöver förändras.** Riskklass, spårbarhet, stoppmöjligheter och livscykel behöver följa med godkända utvecklingsvägar automatiskt. Låg-riskutveckling ska vara enkel; högriskfall ska möta starkare skydd och tydligare ansvar.

**Beredskapsindikatorer.** Det går att registrera ägare och version, begränsa tjänste- och agentbehörigheter, tillämpa skydd och eskalera incidenter. Börja med väl avgränsade användningsfall; håll annars tillbaka högriskfunktioner tills skydden fungerar.


## Generation 4 – även verksamhetsutvecklade lösningar behöver kunna förvaltas

### När förmågan är relevant

I ett framväxande fjärde generationsmönster kan verksamhetsmedarbetare skapa fler digitala lösningar med hjälp av lågkod, AI-stödda verktyg eller agenter som använder andra system. En liten lösning kan vara okomplicerad i början men bli verksamhetskritisk när många börjar förlita sig på den. Det går därför inte att utgå från att endast centrala IT-projekt behöver övervakning och återställning.

### Vilket stöd som behöver finnas

Tillåtna utvecklingsvägar behöver ge lösningar riskanpassade standardkontroller automatiskt: identifierbar ägare, versionsinformation, relevant loggning, användnings- och kostnadsgränser, lämpligt dataskydd, möjlighet till återställning och säker avveckling. För AI-baserade flöden kan driftbarhet även behöva omfatta modell-/verktygsberoenden, antal och kostnad för anrop, avvikande beteende samt möjlighet att stoppa eller begränsa handlingar. Det innebär **inte** att all prompttext eller användardata ska loggas. Tvärtom måste spårbarhet balanseras med sekretess, dataminimering och behörighet.

För kritiska arbetsflöden behövs också en prövad reservväg när en extern AI- eller API-leverantör blir otillgänglig. För en icke-kritisk assistent kan det i stället vara acceptabelt att tillfälligt avstå funktionen. En AI-assistent som föreslår ett beslut är inte samma risk som en agent som faktiskt ändrar ett verksamhetsregister. Kontrollnivån bör stå i proportion till vad lösningen får göra.

### Ansvar och vanliga fallgropar

Verksamheten måste veta vilken nytta lösningen ger, vilka konsekvenser fel får och vem som fattar beslut om fortsatt drift. IT ska tillhandahålla säkra standardvägar och kunna ingripa vid allvarliga händelser. Det vore en fallgrop att låta alla medarbetare skapa skugg-IT utan livscykel; en annan att införa så tunga centrala kontrollprocesser att legitim låg-riskutveckling blockeras. En tredje är att övervaka endast teknisk tillgänglighet när AI-lösningen levererar felaktiga resultat med full svarsfrekvens.

### Indikatorer på olämpliga teknik- och plattformsval

- **Täckning:** stödet omfattar traditionella driftsatta applikationer men inte godkända verksamhetsbyggda arbetsflöden eller AI-agenters aktivitet.
- **Styrning:** plattformen kan inte tillämpa riskanpassade begränsningar, säkert stopp eller återkallelse av åtkomst för en automatiserad lösning.
- **Spårbarhet och integritet:** verksamheten kan inte förstå avvikande agentbeteende utan att okontrollerat samla in känslig information.
- **Livscykel:** ägare, version, kostnad, återställning och avveckling kan inte följas när många små lösningar skapas.
- **Externa beroenden:** modell- eller API-leverantörer blir kritiska för processen utan fungerande reservväg eller insyn i tjänstekvalitet.

Detta är **framtidsinriktade bedömningskriterier**, inte ett påstående att samtliga organisationer redan behöver en specialiserad AI-observability-plattform. Välj skydd efter konsekvens och risk.

### Indikatorer på tillräckligt stöd

Det går att identifiera aktiva verksamhetslösningar och ansvariga ägare. Viktiga AI-baserade flöden kan följas på en nivå som gör fel, kostnadsavvikelser och otillåtna handlingar upptäckbara utan att känsliga uppgifter exponeras. En felaktig programversion kan stoppas eller rullas tillbaka. Åtgärder som redan har utförts i externa system kan däremot kräva särskild avstämning, kompensation eller mänskligt beslut; de kan inte förutsättas gå att ångra tekniskt. Lösningar som inte längre behövs kan avvecklas inklusive behörigheter, data och integrationsåtkomst. Dessa ambitioner är en **framåtblickande arkitekturbedömning**, inte en etablerad generell kravlista för alla organisationer.

## Beslutsstöd: vilket problem har vi egentligen?

| Observation | Trolig problemtyp | Första praktiska kontroll |
|---|---|---|
| Driftlarm är gröna men ärendeflödet fungerar inte | Kvarvarande G1→G2-brist | Spåra ett riktigt användarflöde och namnge helhetsansvarig |
| Återläsning fungerar per databas men inte för hela flödet | Kvarvarande G1→G2-brist | Öva beroendeordnad återställning och verifiera konsistens |
| Samma larm- och backupupplägg beställs manuellt av många team | G2→G3-drivkraft | Mät ledtid, variation och antal återkommande normalfall |
| Övervakningsverktyget saknar export av signaler eller support | Möjlig teknik-/produktrisk | Kontrollera API, format, supportlivscykel och alternativa kopplingar |
| Självbetjäningsportalen kräver fortfarande handläggning | Implementations-/arbetssättsbrist i G3 | Följ ett normalfall genom hela leveranskedjan |
| Verksamhetsbyggda AI-flöden saknar ansvar och säkert stopp | Möjlig G3→G4-drivkraft | Kartlägg ägare, mandat, riskklass och stoppväg |

### Fyra möjliga åtgärder för teknik och plattform

1. **Behåll:** funktion, säkerhet, livscykel och kostnad är tillräckliga för behovet.
2. **Komplettera:** tillför exempelvis korrelation, integrationsadapter, automation eller prövade återställningsrutiner.
3. **Förändra användning och ansvar:** samma produkt kan bli tillräcklig med bättre konfiguration, tjänsteprofiler, plattformsproduktansvar och gemensam incidenthantering.
4. **Ersätt:** produktens grundbegränsningar, supportläge, säkerhet eller totalkostnad hindrar rimliga lösningar.

Avgör mellan dessa alternativ med prövad funktion, rimlig totalkostnad inklusive migrering, säkerhetskonsekvens, leverantörsrisk och möjlighet att stegvis förändra. **Indikatorer är hypoteser som behöver verifieras**, inte automatiska produktdomar. Pröva alltid om det verkliga hindret ligger i produkten, konfigurationen, integrationen, kompetensen eller ansvarsfördelningen.


## Tre frågor före beslut om nästa steg

Det är lätt att tolka återkommande driftproblem som ett behov av en ny plattform. Börja i stället med tre frågor. **Fungerar det viktigaste verksamhetsflödet med acceptabel risk?** Om inte behöver grundläggande felupptäckt, ansvar och återställning prioriteras, oberoende av generationsmål. **Är samma tekniska stöd dyrt eller långsamt att upprepa för nästa team?** Då kan standardisering och självbetjäning vara motiverad. **Är det verkligen produkten som begränsar oss?** En bristande integration eller oklar ansvarsfördelning kan ge samma symtom som en olämplig produkt.

Tillämpa frågorna på ett konkret flöde och samla underlag om påverkan, ledtid, totalkostnad, risk och praktiskt utförda prov. På så sätt blir nästa generationsförflyttning ett medvetet val och inte en följd av att dagens miljö har problem.

## Vilka tekniska tjänster ligger bakom förmågan?

Det ursprungliga förmågeunderlaget identifierar fem direkt stödjande plattformstjänster, organiserade i två konceptuella plattformar. Namnen är tekniska och viktiga för spårbarhet men huvudfrågan är vilka behov de löser.

| Tjänst | Huvuduppgift | När gemensamt erbjudande ger särskild nytta |
|---|---|---|
| PLS-035 – Central observability | Samla och korrelera loggar, mätvärden och spårningar | Flera team behöver felsöka samma tjänstekedja; G3-standardinstrumentering |
| PLS-036 – Övervakning och larm | Mäta tillstånd, följa kvalitetsmål och kalla till åtgärd | Många tjänster behöver enhetliga, åtgärdbara larm |
| PLS-037 – Backup och återställning | Skyddskopior och verifierad återläsning | Många datatjänster behöver styrda och återanvändbara skyddsprofiler |
| PLS-038 – Disaster Recovery och återställningsorkestrering | Återställa större tjänstekedjor efter omfattande bortfall | Många beroende IT-stöd har strikta kontinuitetskrav |
| PLS-070 – Central teknisk audit trail | Skyddad teknisk händelsekedja för särskild granskning | Flera system behöver samma integritets- och åtkomstkrav på tekniska revisionsspår |

PLS-035, PLS-036 och PLS-070 hör i källmodellen till **PLT-008 – Observability- och teknisk spårbarhetsplattform**. PLS-037 och PLS-038 hör till **PLT-029 – Backup- och återställningsplattform**. Den tekniska revisionskedjan ersätter varken verksamhetens formella arkiv eller säkerhetsorganisationens särskilda incidentanalys. Att tjänster finns i referensmodellen betyder inte att varje organisation måste etablera var och en centralt.

## Så kan förmågan bedömas i praktiken

Välj ett representativt verksamhetsflöde, exempelvis ”skicka in, behandla och avsluta ett ärende”. Beskriv konsekvenserna av ett avbrott, hur beroendena ser ut och vem som har helhetsansvar. Genomför därefter minst två praktiska prov: ett där en beroendetjänst blir otillgänglig och ett där viktig information behöver återställas. Följ hela kedjan från upptäckt till fungerande verksamhetsresultat. Dokumentera faktisk tid till upptäckt och återhämtning, informationens konsistens, vilka manuella moment som krävdes och om rätt personer kunde agera. Jämför därefter med verksamhetens överenskomna toleranser för avbrott och dataförlust. Bedöm även om händelseinformationen räckte för att skilja en driftstörning från en möjlig säkerhetsincident, utan att blanda ihop de båda ansvaren.

Bedöm därefter inte endast om provet lyckades, utan **om arbetsmodellen skalar**. Om samma övning skulle behöva göras för trettio nya tjänster, kan organisationen då använda gemensamma profiler och automatisering? Om lösningarna även skapas av verksamheten, får de rätt skydd utan manuell specialhantering? Svaret säger mer om behovet av en generationsförflyttning än namnet på övervakningsverktyget.

Det finns inget skäl att pressa varje IT-stöd till generation 4. För ett stabilt och tydligt avgränsat system kan generation 1 eller 2 vara fullt ändamålsenlig, under förutsättning att verksamhetens krav faktiskt uppfylls. Förmågan är tillräckligt utvecklad när den ger **rätt stöd med rimlig kostnad, tydligt ansvar och kontrollerbar risk**.

## Källor och kunskapsgrund

**Primära interna källor**

1. *Från systemdrift till digital självständighet*, framför allt kapitlen om de fyra generationsmönstren, ansvar och beslutsgrindar.
2. *Förmågeöversikt – tekniska IT-förmågor*, modellbaseline v1.1, CAP-IT-09.
3. *Plattformsöversikt – konceptuella plattformar*, modellbaseline v1.1, PLT-008 och PLT-029.
4. *CAP-IT-09 – Driftbarhet och motståndskraft*, tidigare teknisk fördjupningsanalys v1.0. Denna är ett analytiskt mellanunderlag, inte en oberoende extern källa.

**Extern vägledning**

- Google SRE, *Monitoring Distributed Systems*: https://sre.google/sre-book/monitoring-distributed-systems/ — användarpåverkan och de fyra grundsignalerna för tjänsteövervakning.
- Google SRE Workbook, *Alerting on SLOs*: https://sre.google/workbook/alerting-on-slos/ — handlingsbara larm kopplade till tjänstekvalitetsmål.
- DORA, *Monitoring and observability*: https://dora.dev/capabilities/monitoring-and-observability/ — skillnaden mellan övervakning och felsökande observerbarhet samt sambandet med leveransförmåga.
- OpenTelemetry, *Semantic Conventions*: https://opentelemetry.io/docs/concepts/semantic-conventions/ — gemensamma begrepp för mätvärden, loggar och distribuerade spår.
- NIST SP 800-34 Rev. 1, *Contingency Planning Guide*: https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final — konsekvensbaserad kontinuitetsplanering och återställningsövning.
- NIST SP 800-61 Rev. 3, *Incident Response Recommendations*: https://csrc.nist.gov/pubs/sp/800/61/r3/final — samspel mellan förberedelse, incidentrespons och återhämtning; gäller specifikt cybersäkerhetsincidenter och ersätter inte generell driftledning.

**Källtolkning:** Förmågedefinitionen, avgränsningen samt PLS-/PLT-relationerna kommer från referensdokumenten. Generationsspecifika krav, exempel, indikatorer och prioriteringar är en syntes/arkitekturbedömning, med extern principförankring där detta anges. Generation 4 är ett scenario, inte en etablerad universell standard. Texten är inte en nulägesbedömning av en viss organisation.