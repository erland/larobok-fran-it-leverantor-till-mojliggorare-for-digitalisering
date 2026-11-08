# CAP-IT-02 – Process, workflow och ärendehantering

*Faktabokskapitel · version 2.0, kritiskt reviderad 7 november 2026 · Generation 2 som utgångspunkt*

## Vad handlar förmågan om?

En verksamhetsprocess är mer än en följd av tekniska anrop. Ett tillstånd ska kunna följas, någon behöver veta vem som väntar på vem, ett beslut ska kunna motiveras och ett fel får inte lämna ett ärende i ett läge som ingen kan reda ut. Förmågan **Process, workflow och ärendehantering** handlar om tekniskt stöd för sådana uttryckliga, ofta långlivade förlopp – särskilt när människor, verksamhetsbeslut och flera IT-stöd deltar.

Föreställ dig en ansökan som tas emot, kompletteras, granskas av en handläggare, kontrolleras mot ett annat register och slutligen beslutas. Ett enskilt API kan svara på millisekunder medan hela ansökan pågår i veckor. Ett avbrutet nätverksanrop är då bara ett litet delproblem. Den viktigare frågan är: **vad vet vi om ansökans tillstånd, vem får göra nästa sak och hur fortsätter processen efter ett fel?**

Förmågan omfattar fyra direkt stödjande plattformstjänster i källmodellen: **PLS-005 Workfloworkestrering**, **PLS-006 Case management-plattformstjänst**, **PLS-007 Human task och arbetskö** samt **PLS-004 Notifikations- och meddelandeleverans**. De första tre hör till **PLT-002 Process- och beslutsplattform** och den sista till **PLT-024 Notifikations- och meddelandeplattform**. Formulär, beslutsregler, API-hantering och systemmeddelanden är viktiga angränsande tjänster, men ingår inte i denna förmågas direkta tjänstelista.

Det vore fel att dra slutsatsen att varje applikation behöver en workflowmotor. Ett enkelt steg i programkod, ett kort databasanrop eller en vanlig CRUD-funktion kan vara fullt tillräckliga. Det är de **bestående tillstånden, väntelägena, mänskliga överlämningarna, tidsvillkoren och behovet av kontrollerad återupptagning** som motiverar explicit processstöd.

Tre frågor måste hållas isär genom hela kapitlet: hur viktig funktionen är för en viss verksamhetsprocess, om den bör erbjudas som **gemensam plattformstjänst** och om återkommande handgrepp behöver **automatiseras**. Även en kritisk ärendeprocess kan vara bäst betjänt av en väldesignad lokal implementation om organisationen saknar återkommande, gemensamma behov.

## Tillbakablick: generation 1 och generationsarvet

I generation 1 var många verksamhetsflöden inbyggda i ett större sammanhållet system. Databasen, användargränssnittet, den interna logiken och de schemalagda jobben kunde ofta uppfattas som en enda leveransenhet. Handläggaren såg samma system som driftpersonalen felsökte. Ett ärende kunde byta status i en lokal transaktion. Detta gav inte automatiskt bra processöversikt, men den tekniska felgränsen var förhållandevis sammanhållen.

Arvet blev ofta lokalt anpassade statusfält, osynliga timerjobb, personberoende arbetslistor och regler som bara gick att förstå genom att läsa programkod. Vid en återstart kunde en automatisk kontroll behöva köras manuellt. Det fanns organisationer som redan använde avancerad workflowteknik; generation 1 är alltså ingen historisk garanti för avsaknad av automatisering.

När IT-stöden delades upp i flera tjänster förändrades situationen: en ansökan kunde ha sina uppgifter i en tjänst, sin bedömning i en annan och sin notifiering i en tredje. Delmomenten kunde vara välbyggda var för sig men ingen följde processens *sammanhängande* tillstånd. **Generation 2 kan därmed ärva problemet med dold processlogik och samtidigt lägga till nya distribuerade felmoder.** Detta är grunden för kapitlets huvudperspektiv.

## Generation 2 – få ett helt verksamhetsförlopp att fungera

### När blir processförmågan viktig?

Behovet ökar när ett flöde har flera organisatoriska ansvariga, väntar på mänskliga beslut, löper över lång tid eller påverkar externa system. En ärendeprocess med tre handläggningssteg kan behöva bättre processstöd än en tekniskt mer komplicerad men kort beräkning. Det avgörande är inte antalet mikrotjänster utan om processen behöver **beständig status, styrda övergångar och en klar ansvarig för helheten**.

En stor del av grundarbetet i generation 2 är att dokumentera processen på ett begripligt sätt: vilka tillstånd är tillåtna, vad avslutar ett steg, vad händer när en tidsgräns passeras och vem kan ingripa? Det går att göra med vanlig kod, en domänspecifik tillståndsmaskin eller en workflowmotor. Valet av teknik är sekundärt i förhållande till att dessa regler finns och kan verifieras.

### Orkestrering, koreografi och processägarskap

**Orkestrering** innebär att en explicit komponent eller processlogik samordnar stegen och håller reda på vad som ska göras härnäst. **Koreografi** innebär att deltagande tjänster reagerar på händelser utan en enda central exekverare. Båda kan fungera. Orkestrering kan göra långa förlopp lättare att följa; koreografi kan ge självständiga domäner färre direkta beroenden. Men en distribuerad kedja blir inte automatiskt begriplig för att den använder händelser, och en central motor blir inte automatiskt en bra verksamhetsägare.

Det måste finnas ett ansvar för **hela** processen även när varje tekniskt steg har sin egen ägare. Processägaren beslutar om verksamhetsmål, beslutspunkter, acceptabla väntetider och avvikelsehantering. Domänteamet beslutar hur dess tjänst säkert utför ett steg. Plattformsteamet, om ett sådant finns, ansvarar för sin runtime och dess tekniska livscykel. Ingen av dessa roller bör tyst överta de andra rollerna.

### Långvariga transaktioner kan inte alltid rullas tillbaka

I en lokal databas går det ibland att rulla tillbaka en ännu inte avslutad transaktion. Ett verksamhetsförlopp som redan har skickat ett beslut, bokat en tid eller genomfört en utbetalning fungerar annorlunda. Stegen kan ha **separata lokala transaktioner**, och det kan saknas ett gemensamt atomärt avslut.

Ett ofta använt mönster för sådana kedjor kallas *saga*: flera lokala steg samordnas och vissa fel leder till en ny, kompenserande åtgärd. Kompensation är dock **inte** detsamma som en verklig återställning av historien. En redan avsänd avisering kan inte göras osedd; en banköverföring kan kräva en ny transaktion och en juridiskt relevant rättelse. Även kompensationen kan misslyckas. Därför behöver processen ange vilka steg som kan upprepas, vilka som kan kompenseras, vilka som kräver mänskligt beslut och var en oåterkallelig gräns finns.

När ett tekniskt meddelande återförsöks måste systemet dessutom skilja mellan *samma begäran en gång till* och *ett nytt giltigt verksamhetsuppdrag*. Beständiga identifierare, idempotensvillkor och kvittenser är centrala. Ett lyckat HTTP-svar bevisar inte att ett ärende är färdigbehandlat, lika lite som en brokerkvittens bevisar att en extern verksamhetseffekt inträffat exakt en gång. Denna gräns är gemensam med CAP-IT-06 – Integration och informationsutbyte.

### Ärende, uppgift och notifiering är olika saker

En **case management-tjänst** hanterar en långlivad ärendekontext: identitet, status, historik och ofta aktiviteter som kan utföras i varierande ordning. Den är inte automatiskt själva verksamhetssystemet eller den auktoritativa källan för ärendets rättsliga och sakliga innehåll.

En **human task-tjänst** hanterar mänskliga arbetsmoment: vem får en uppgift, vem har tagit över den, när ska den eskaleras och vad händer om handläggaren slutar? En teknisk tilldelning i arbetskön ger inte automatiskt rätt att fatta ett visst beslut. Behörigheten måste kontrolleras av verksamhetsdomänen med stöd av identitetsförmågan CAP-IT-07.

En **notifikation** talar om för någon att något har hänt eller kräver uppmärksamhet. En sådan leverans kan behöva egen spårbarhet för avsändare, mottagare och utskicksversion, men är inte i sig en delgivning eller ett rättsligt bevis. Att e-postmeddelandet skickats betyder inte att mottagaren läst det, och ett läskvitto betyder inte att uppgiften utförts. För tidskritiska och rättsligt betydelsefulla moment måste organisationen skilja mellan skapad avisering, tekniskt överförd avisering, eventuell mottagarkvittens och faktiskt slutfört verksamhetsmoment.

Även gränsen mot data är viktig: arbetskön får inte utan vidare bli en alternativ källa för ett ärendes verkliga status; dubbla statusuppgifter skapar annars motsägelser. CAP-IT-04 behandlar informationens ägarskap och lagring; CAP-IT-09 den tekniska driftbarheten och återställningen.

### Samtidiga ändringar: vem får flytta ett ärende till nästa tillstånd?

En mer svårupptäckt feltyp uppstår när två handläggare eller två tjänster läser samma ärendeversion och sedan försöker ändra den. En handläggare lägger till ett kompletteringskrav medan en annan avslutar ärendet. Om den senare uppdateringen tyst skriver över den första kan verksamheten förlora både information och ett beslutsunderlag. Att båda tekniska anropen får lyckat svar betyder inte att resultatet är korrekt.

**Förlorad uppdatering** kan motverkas genom att en ändring villkoras av att ärendets versionsnummer fortfarande är det som lästes, exempelvis optimistisk samtidighetskontroll, eller genom en transaktionell låsning där sådan är lämplig. Det krävs dessutom verksamhetsregler: vilka tillståndsövergångar är giltiga, vilka ändringar får förenas, och vad händer när två helt giltiga men oförenliga beslut konkurrerar? Konflikten bör exponeras och hanteras, inte döljas med automatiskt sista-skrivningen-vinner.

När ändringen sker via händelser mellan tjänster behövs också hantering av fördröjning, omordning och dubbletter. En äldre händelse får inte utan en uttrycklig regel flytta tillbaka ett ärende från ett senare auktoritativt tillstånd. Därför behöver varje kritisk statusförändring kunna knytas till en förväntad tidigare version, ett beslut, en ansvarig aktör och en spårbar tidpunkt. Detta är en fråga om domän- och dataarkitektur i generation 2, inte i första hand om att köpa en motor.

### När lokal processlogik är rätt val

En enkel intern beställning består kanske av tre väldefinierade steg inom ett system, utan längre väntan, distribuerade åtgärder eller krav på gemensamma arbetslistor. En liten domänspecifik tillståndsmaskin med tydliga tester, en databastransaktion och en dokumenterad ansvarig kan då vara enklare, säkrare och billigare att förvalta än en separat workflowmotor. Beslutet bör omprövas först om exempelvis många team återupprepar samma timer-, eskalerings- och återupptagningslogik eller flödet får en verkligt långlivad, tvärsystembaserad karaktär.

### Diagnostiskt exempel: en ansökan som aldrig avslutas

En kommunal eller offentlig verksamhet tar emot en ansökan. System A registrerar ärendet, tjänst B kontrollerar uppgifter, en handläggare fattar beslut i system C och en notifiering skickas från D. Efter en tillfällig störning visar A statusen ”under handläggning”, B ”godkänd kontroll” och C har registrerat ett beslut. Sökanden får två aviseringar. En administratör upptäcker ärendet först när sökanden ringer.

Följ nu **ett verkligt ärende-ID** genom hela kedjan. Vilket tillstånd är auktoritativt? Finns en tydlig processägare och en ansvarig för varje övergång? Kan man skilja mellan ett tekniskt återförsök och en ny handläggningsaktivitet? Finns en återhämtningsväg för ärendet som fastnat efter beslutet? Kan man avgöra om dubbel avisering var ofarlig eller en rättsligt relevant händelse? Har handläggaren faktiskt rätt att slutföra ärendet efter en omfördelning?

Om dessa frågor inte kan besvaras finns **grundläggande generationsarv som måste rättas i generation 2**. Man bör inte börja med att köpa en processmotor. Rätta först kontrakt, tillstånd, ansvarsgränser, idempotens, synliga fel och operativ rutin. Därefter går det att avgöra om flera liknande processer skulle vinna på ett gemensamt plattformserbjudande.

### Indikatorer på fungerande stöd

- För ett utvalt kritiskt flöde går det att följa en processinstans från start till avslut med identifierbara ansvariga för övergångarna.
- Processinstanser har beständig status; efter en kontrollerad störning kan de återupptas eller föras till ett definierat manuellt avvikelseläge utan omedveten dubbel effekt.
- Tidsfrister är uttryckligen definierade och det är känt vem som blir ansvarig när de passeras; systemet skiljer mellan påminnelse och faktiskt beslut.
- Det finns en rutin för ändringar av processen medan äldre instanser fortfarande körs. Dessa instanser försvinner inte eller får ny betydelse utan en medveten migrerings- eller samexistensstrategi.
- Verksamhet och teknik kan gemensamt återskapa vad som hände i ett felaktigt ärende, inom relevanta dataskydds- och loggningsregler.
- Mått avser verksamhetens resultat: exempelvis andel ärenden som klarar beslutade tidsfrister, antal fastnade instanser och tiden att lösa dem. Antalet lyckade API-anrop ensamt räcker inte.

### När är tekniken olämplig – och när används den fel?

Ett produkthinder kan föreligga om exekveringsmotorn **saknar en nödvändig egenskap**: exempelvis uthållig status, dokumenterat stöd för långlivade instanser, säkra versionsbyten, revisionsspår eller rimlig driftsupport. En sådan brist behöver dock verifieras mot faktisk produktversion och avtalade krav.

Många andra problem ligger utanför själva produkten. Felaktiga återförsök är oftast en fråga om design eller konfiguration. Oklara ärendetillstånd kan vara en data- och domänfråga. Fastnade uppgifter kan bero på att verksamheten saknar en beslutad eskaleringsrutin. Och en motor som påstås vara långsam kan i själva verket vänta på ett externt beroende.

Undersök därför först **vad som händer med processen**, sedan **var och varför felet uppstår**, och sist **vilken förändring som faktiskt tar bort orsaken**. Möjliga åtgärder är att behålla och förbättra befintlig teknik, komplettera den, ändra arkitektur eller ansvar eller – om en verifierad begränsning kvarstår – ersätta produkten.

## Övergången från generation 2 till generation 3 – när processstöd bör bli en produkt

### Ett annat problem än generationsarvet

Generation 3 ska inte användas som ursäkt för att skjuta upp grundläggande processansvar. Behovet uppstår när **fungerande, säkra processmönster återkommer i så många lösningar att lokala implementationer och manuella specialistärenden blir ett hinder**. Kanske bygger fem team varsin timerlogik, egna arbetsköer och separata notifieringsvägar. Kanske tar nya ärendeflöden månader, inte därför att verksamhetsreglerna är svåra utan därför att de tekniska tjänsterna alltid måste uppfinnas på nytt.

Detta är ett mätbart motiv för en gemensam tjänst: återanvändningen är konkret, inte en idé om att allt ska centraliseras. Ett litet antal specialiserade arbetsflöden kan fortfarande hanteras lokalt på ett bättre sätt. Flera tjänster kan också erbjudas var för sig utan en enda stor processprodukt.

### Vad bör självbetjäningen omfatta?

Ett moget erbjudande kan ge teamen godkända sätt att starta och följa långlivade processinstanser, definiera eller integrera arbetsköer, skicka mottagaranpassade notifieringar och koppla ihop dessa med besluts- och integrationsförmågor. Gränssnitt och mallar behöver vara dokumenterade, säkert konfigurerade och möjliga att prova utan lång specialistkö.

**Självbetjäning är inte enbart skapande.** Organisationen måste även kunna ändra en processdefinition, följa pågående instanser, hantera undantag, uppgradera motorn och avsluta en processprodukt utan att lämna kvar oöverskådliga uppdrag eller åtkomster. Speciellt viktigt är versionshanteringen: en ny definition kan inte automatiskt antas vara tillämplig på instanser som redan har väntat i månader. Vissa behöver gå klart enligt äldre modell, andra kan migreras med särskild verifiering.

Plattformen bör erbjuda mätetal för användbara utfall – tid till ett första fungerande flöde, andel standardändringar utan manuell specialistkontakt, tid att hantera incidenter, avvikelser per process och kostnad att förvalta en konsument. Men den ska inte mäta ”självbetjäning” enbart utifrån antalet klick i en portal. Om varje knapptryck skapar ett manuellt ärende är beroendet bara dolt.

### När processdefinitionen ändras medan ärenden fortfarande pågår

En processdefinition kan vara version 1 när ett ärende skapas och version 3 när det avslutas. Det ger flera praktiska alternativ: låt pågående instanser slutföras enligt den tidigare definitionen, flytta vissa instanser med en kontrollerad migrering eller rätta enstaka felaktiga instanser utan att flytta alla. Vilket alternativ som fungerar beror på processens aktuella steg, aktiva timers och uppgifter, dataformat, externa kontrakt och motorns faktiska garantier.

En versionsändring är därmed **inte** jämförbar med en vanlig kodutrullning. Att den nya modellen kan publiceras betyder inte att gamla instanser kan flyttas. Och även om en produkt har stöd för migrering behöver man pröva vad som händer med exempelvis redan reserverade uppgifter, väntande meddelanden, tidsfrister, revisionshistorik och tillhörande verksamhetsregler. Vid större förändringar kan stegvis migrering eller ett kontrollerat avslut med ny instans vara bättre än en automatisk massflytt, men då måste sambandet och historiken bevaras.

Ett verifieringsprov är att starta en instans enligt version 1, lämna den i ett vänteläge, publicera version 2 och därefter pröva både fortsatt körning och en planerad migrering. Kontrollera att ingen uppgift försvinner, ingen åtgärd utförs två gånger, tidigare beslut inte omtolkas utan mandat och att en misslyckad migrering lämnar ett hanterbart tillstånd. Produktspecifika begränsningar måste undersökas i dokumentation och praktiskt test; de kan inte härledas av att ett modellformat stöds.

### Organisation och ansvar

**Plattformsteamet** ansvarar för teknisk tillförlitlighet, gemensamma kontrakt, behörighetsintegration, livscykel, onboarding och stöd. **Domän-/applikationsteamet** ansvarar för sina processdefinitioner, integrationer, beslut och verksamhetsmässiga fel. **Verksamhetens processägare** ansvarar för vilka steg som ska finnas, vilka som får besluta, tidsfrister och hur rättelser ska ske. En gemensam motor får alltså inte bli en plats där alla förvaltningars verksamhetsregler och informationsmodeller hamnar utan tydligt ägarskap.

Standarder som **BPMN** kan ge ett gemensamt språk för strukturerade processer och **CMMN** för mer flexibla ärenden. De är möjliga uttrycksmedel, inte bevis för att en motor är lämplig eller att ett visst modellformat måste användas. Det viktiga är att modellen överensstämmer med den exekverade verkligheten och kan förvaltas av dem som äger den.

### Indikatorer på fungerande respektive olämplig plattformsstrategi

En väl fungerande plattform gör det enkelt att starta ett standardfall, testa avbrott, se processstatus, ändra under kontrollerade former och avsluta både definition och instanser. Den skapar tydliga gränser mellan verksamhetsregler och teknisk drift. Konsumenter kan förstå vilka garantier som erbjuds och vad de själva måste implementera, exempelvis idempotenta åtgärder.

Varningssignaler är en gemensam motor som blir kö för varje liten verksamhetsändring, ett omfattande specialskriptlager som ingen förstår, versioner som inte kan samexistera, eller säkerhetskontroller som kan kringgås av direktanrop. Detta kan motivera förändrad plattformsstrategi men inte alltid ett produktbyte. Börja med att visa vilken avgränsad tjänst som inte möter kravet och om felet beror på processarkitektur, implementation, driftsättning, avtal eller produktförmåga.

## Generation 4 – verksamhetsnära automation under kontrollerat ansvar

I ett framtida läge kan verksamheter bygga och justera fler arbetsflöden själva, ibland med hjälp av AI. En AI-assistent kan sammanställa underlag, föreslå nästa steg eller automatisera uppgifter med låg risk. Förmågan att snabbt skapa sådana flöden innebär dock inte att AI:n ska vara verksamhetsansvarig. Även när genererade processteg verkar rimliga måste den som har ansvar för processen godkänna beslutspunkter, informationsanvändning och den risk automationen får ta.

Ett agentmandat behöver knytas till en identifierbar uppdragsgivare, en specifik processinstans och tillåtna handlingar. När ett mandat återkallas måste nya åtgärder nekas vid en betrodd kontrollpunkt. För en redan köad åtgärd behöver mandat och risk normalt prövas på nytt när åtgärden faktiskt ska verkställas, om inte en uttryckligen godkänd regel anger något annat. **Redan köade anrop, redan påbörjade externa åtgärder och redan genomförda beslut kan kräva separata stopp-, avstämnings- eller rättelsemekanismer.** Att stoppa en agent eller återkalla en token gör inte ett genomfört verksamhetsbeslut ogjort.

Praktiskt bör en verksamhet kunna simulera ett förändrat processflöde, prova negativa behörighetsfall och visa hur mänskligt godkännande krävs för utpekade beslut. Process- och agentloggar måste möjliggöra efterhandsgranskning utan att onödigt samla känslig information. En agent som föreslår en disposition är mindre riskfylld än en som självständigt avslutar ett rättsligt bindande ärende eller genomför en betalning. Skydden behöver därför vara riskanpassade; varje AI-stött flöde behöver inte en ny specialplattform, men varje flöde behöver ansvar och verifierbara gränser.

Indikatorer på fungerande stöd är spårbar godkännandekedja, kontrollerbar åtkomst, tydliga stoppvillkor, uppföljningsbara avvikelser och bevarad möjlighet för människor att överpröva där verksamheten kräver det. Varningssignaler är AI-genererade processändringar utan test, direkt tillgång till breda verksamhetskonton eller påståenden om att en logg i sig bevisar att ett beslut var korrekt.

## De fyra stödjande plattformstjänsterna

| Tjänst | Bidrag och gräns |
|---|---|
| **PLS-005 Workfloworkestrering** (PLT-002) | Beständig exekvering av explicita flöden, tidsvillkor och återupptagning. Inte verksamhetsregelverk eller generell integrationstransport. |
| **PLS-006 Case management-plattformstjänst** (PLT-002) | Teknisk kontext och livscykel för långlivade ärenden. Inte ett komplett verksamhetsspecifikt ärendesystem eller en ensam auktoritativ informationskälla. |
| **PLS-007 Human task och arbetskö** (PLT-002) | Tilldelning, arbetslistor, eskalering och slutförandestatus. Tilldelning ersätter inte behörighetskontroll eller beslutsmandat. |
| **PLS-004 Notifikations- och meddelandeleverans** (PLT-024) | Kanalstyrd avisering till människor eller mottagare med fel- och leveransuppföljning. Inte CAP-IT-06:s tekniska meddelandetransport och inte bevis på att ärendet har avgjorts. |

De direkta PLS-relationerna och plattformskopplingarna är hämtade från källmodellens baseline v1.1. Prioriteringar och rekommenderade kontroller är däremot analytiska tillägg. Ingen av de fyra tjänsterna är automatiskt ett krav på **egen** eller **gemensam** plattform i alla organisationer och generationer.

## En praktisk beslutsordning

Börja med att välja ett representativt verksamhetsflöde. Följ en instans genom verkliga väntelägen, överlämningar och fel; fråga vem som äger utfallet och hur avvikelser hanteras. Rätta först brister som skulle vara problem även i en helt lokal implementation. Undersök därefter om flera team återupprepar samma fungerande teknikmönster och om en gemensam tjänst kan minska denna friktion.

Bedöm sedan **funktionens kritikalitet**, **behovet av en gemensam produkt** och **värdet av automation** separat. Välj åtgärd genom att jämföra att behålla och förbättra, komplettera, ändra ansvar eller tillämpningsmönster och ersätta teknik vid verifierad begränsning. Dokumentera vad man ska kunna observera efter förändringen, inte bara vilken produkt som införs.

Den önskade förflyttningen är inte ”från kod till workflowmotor” utan **från oklara och svårhanterliga verksamhetsförlopp till spårbara, återupptagbara och ansvarsatta processer – och där behovet finns, till återanvändbara plattformstjänster som gör detta enklare för fler**.

## Källor och tolkningsram

**Källbas:** *Förmågeöversikt – tekniska IT-förmågor*, baseline v1.1; *Plattformsöversikt – konceptuella plattformar*, baseline v1.1; *Från systemdrift till digital självständighet*. Dessa källor fastställer förmåge- och tjänstekopplingar och bokens generationsram. Textens exempel, prioriteringar och rekommenderade verifieringsprov är redaktionell/teknisk analys, inte belagda nulägesobservationer.

**Kompletterande tekniska referenser:** Camunda, *Process instance migration* (https://docs.camunda.io/docs/components/concepts/process-instance-migration/) och *Versioning process definitions* (https://docs.camunda.io/docs/components/best-practices/operations/versioning-process-definitions/) är produktspecifika exempel på verkliga migrationsbegränsningar, inte generella garantier. Object Management Group, *BPMN 2.0.2* (https://www.omg.org/spec/BPMN/2.0.2); Object Management Group, *CMMN 1.1* (https://www.omg.org/spec/CMMN/1.1); Microsoft, *Saga distributed transactions pattern* (https://learn.microsoft.com/en-us/azure/architecture/patterns/saga); NIST, *AI Risk Management Framework* (https://www.nist.gov/itl/ai-risk-management-framework). De belyser möjliga modeller, tekniska begränsningar och riskhantering och innebär ingen rekommendation att välja en viss produkt.
