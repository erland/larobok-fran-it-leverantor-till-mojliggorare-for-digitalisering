# CAP-IT-03 – Regler och beslut

*Faktabokskapitel · version 2.0 · 7 november 2026 · Generation 2 som utgångspunkt*

## Vad handlar förmågan om?

En organisation fattar många beslut som delvis följer uttryckliga regler: om en ansökan är komplett, vilken avgift som ska tas ut, om en ersättning ska beräknas enligt en viss tabell eller vilka undantag som gäller. Ibland sker bedömningen av en människa med stöd av information. Ibland tillämpas en regel direkt av ett IT-stöd. I båda fallen behöver verksamheten kunna förklara **vilken regel som gällde, vilka uppgifter den tillämpades på och hur beslutet blev till**.

Förmågan **Regler och beslut** gäller främst regler och beslutsmodeller som är uttryckliga och har en egen betydelse och livscykel: de kan behöva ändras, testas, granskas, godkännas och användas av flera tjänster oberoende av de enskilda applikationernas kod. Den omfattar inte all `if/else`-logik eller varje domänberäkning. En enkel och stabil beräkning kan med fördel vara kvar i applikationen.

Källmodellen beskriver två direkt stödjande tjänster: **PLS-008 Besluts- och regelkörning** samt **PLS-009 Beslutsmodellering och simulering**, båda inom **PLT-002 Process- och beslutsplattform**. Detta är konceptuella tjänstetyper, inte en rekommendation att köpa två särskilda produkter eller skapa två tekniska system.

Ett genomgående exempel är en organisation som bedömer ansökningar om ett verksamhetsstöd. Samma regel ska användas i webbportalen, handläggarens stödsystem och en extern integration. Efter en regeländring får två sökande med samma förutsättningar olika preliminära besked beroende på vilken kanal de använder. Alla tre systemen är tillgängliga och deras tekniska anrop lyckas. **Problemet är inte att anslutningen saknas – problemet är att beslutets innebörd och version inte längre är sammanhållen.**

Kapitlet håller isär tre frågor: hur viktig en viss beslutsfunktion är, om den bör erbjudas som en **gemensam plattformstjänst**, och om upprepade moment bör **automatiseras**. Att ett beslut är avgörande för verksamheten innebär inte att en central regelmotor är avgörande. Det kan vara bättre med ett lokalt, vältestat beslut i ett ansvarigt domänteam.

## Kort tillbakablick: generation 1

I generation 1 låg regler ofta i ett sammanhållet verksamhetssystem: programkod, konfiguration, tabeller, dokument och instruktioner för handläggare. Ändringar kunde driftsättas tillsammans med systemet. Det fanns fördelar med denna samling: programmet och dess data hade en gemensam release och det gick ofta att undersöka beräkningen i ett avgränsat tekniskt sammanhang.

Nackdelen var att regler kunde vara svåra att upptäcka och pröva fristående. Ibland visste bara några utvecklare vilken kod som motsvarade ett visst verksamhetsvillkor. En äldre beräkning kunde inte alltid återskapas sedan kod eller tabellinnehåll bytts ut. Det fanns också organisationer med välordnade beslutstabeller och särskilda regelmotorer redan då. Generationerna beskriver därför **dominerande behov och arbetssätt**, inte en universell kronologi för teknikprodukter.

Vid uppdelningen i mindre tjänster flyttades problemet. Regler kopierades eller implementerades på nytt i flera tjänster, ibland med olika tidpunkter för ändring. Den gamla risken för dold logik finns kvar, men förstärks av flera konsumenter, versioner och informationskällor. Det är detta **generationsarv** som behöver förstås när generation 2 fungerar dåligt.

## Generation 2 – samma beslut måste betyda samma sak

### När blir förmågan viktig?

Behovet är störst när en regel påverkar verksamhetsutfall som måste vara likvärdiga, förklarbara eller juridiskt hållbara; när regelverket förändras ofta; eller när flera system tillämpar samma explicit definierade villkor. Ett regelverk kan vara kritiskt även om det används i bara ett system. Omvänt kan många enkla domänvillkor fungera utmärkt i vanlig kod.

I generation 2 är det avgörande att identifiera **regelns ägare**, dess beslutsindata och det utfall den kan ge. Verksamheten måste kunna ange vad begreppen betyder – exempelvis vilket datum som avgör vilken regel som gäller, hur saknade uppgifter behandlas och om en undantagsregel har företräde. Tekniken kan representera och verkställa dessa regler, men kan inte själv avgöra deras verksamhetsmässiga eller rättsliga innebörd.

**Beslutsansvar och beslutsutförande är olika saker.** Ett IT-stöd kan räkna fram ett förslag. En behörig handläggare kan behöva fatta själva beslutet. I andra fall får en automatiserad process fatta ett beslut inom ett tydligt tilldelat mandat. Här måste organisationen skilja mellan resultatet av en regelutvärdering, rekommendationen till beslutsfattaren och ett formellt verksamhetsbeslut. En körd beslutsmodell är inte automatiskt ett rättsligt giltigt beslut.

### Kontrakt, tid och regelversioner

När flera tjänster konsumerar beslutsfunktioner behövs tydliga kontrakt för indata, utdata och fel. Ett kontrakt beskriver inte bara dataformat utan även **semantik**: vilken innebörd har ett belopp, en giltighetsdag, ett statusvärde eller ett frånvarande fält? En tekniskt bakåtkompatibel JSON-ändring kan ändå ändra beslutets innebörd. Konsumenter kan också behöva stöd för äldre regelversioner under en övergång.

Det är särskilt viktigt att skilja mellan tre tidpunkter: **när en regel publicerades, när den enligt verksamheten ska gälla och när ett beslut fattades**. En regel kan beslutas i oktober men börja gälla vid årsskiftet; en ansökan kan vara inkommen före ikraftträdandet men beslutas senare. Vilken tidpunkt som ska styra är en verksamhets- eller rättsregel, inte en teknisk standard. Regeln måste uttrycka detta och lagra tillräckliga referenser för att ett beslut ska kunna förstås efteråt.

Det är inte alltid möjligt att få bitvis identiska resultat vid återspelning av äldre beslut. Indata kan ha kommit från externa källor, tidpunktsberoende register eller system som inte längre finns. Ett realistiskt reproducerbarhetskrav är därför att kunna **rekonstruera och förklara beslutets grund**, inklusive den data och de externa beroenden som faktiskt användes. Om ett historiskt omkörningsprov förutsätter sparad indata ska den lagras enligt relevant sekretess-, gallrings- och bevaranderegel – inte utan begränsning.

### Historiska beslut: vilket underlag ska kunna återskapas?

För att förstå ett gammalt beslut räcker det sällan att ha kvar namnet på en regelversion. Samma regel kan ge ett annat resultat om indata, uppslagsregister, växelkurser, tabeller, beräkningsbibliotek eller klockrelaterade värden har ändrats. Organisationen behöver därför skilja mellan **beslutsbevis** (vad som faktiskt användes), **reproduktion** (att kunna beräkna samma resultat i kontrollerad miljö) och **omprövning** (ett nytt verksamhetsbeslut enligt tillämpliga regler). Dessa är olika uppgifter.

En lämplig beslutsreferens kan knyta samman regelpaketets oföränderliga versionsidentitet, versionssatt indatakontrakt, relevanta indata eller skyddade referenser till dem, tidpunkt och vald giltighetsgrund, anropade externa uppgifter och deras kända versioner samt resultat och ansvarig beslutskedja. När datan inte får bevaras i sin helhet ska det framgå **vilken förklarbarhet som faktiskt kan garanteras**, inte påstås att ett fullständigt omkörningsprov alltid är möjligt. Fingeravtryck kan styrka att en bevarad artefakt inte har förändrats, men kan inte återskapa raderat innehåll.

Pröva detta med ett historiskt ärende vars externa registeruppgift nu har ändrats. Testet ska visa vad som kan rekonstrueras ur tillåtna bevarade uppgifter och vad som måste markeras som osäkert. För regler med hög påverkan bör beslutets proveniens och rätten att lagra dess underlag utformas tillsammans med informationsägare och jurist. Det är **inte** ett generellt argument för obegränsad lagring av personuppgifter.

### Ikraftträdande, övergångsbestämmelser och retroaktivitet

Det räcker inte att en regel har ett `valid_from`-fält. En ändringsbestämmelse kan ange att äldre ansökningar ska bedömas enligt föregående regler, även om beslut fattas efter ikraftträdandet. En annan bestämmelse kan tillåta tillämpning från en tidigare tidpunkt, men om och hur retroaktivitet är tillåten beror på den aktuella rättsliga och verksamhetsmässiga kontexten. Tekniken får inte själv dra sådana slutsatser.

**Exempel:** Regel A gäller normalt till och med den 31 december och regel B från den 1 januari. En ansökan kommer in den 20 december men avgörs den 15 januari. En uttrycklig övergångsregel kan säga att ansökningsdatum styr. Ett annat regelverk kan låta beslutsdatum styra. Båda fallen ska finnas som test, med separat kontroll av ett ärende inkommet exakt vid brytpunkten. En senare rättelse ska inte tyst skriva om det historiska beslutet, utan registreras som en ny spårbar åtgärd.

För mer komplexa miljöer kan man behöva skilja på **verksamhetsgiltig tid** (när regeln avser att gälla) och **registreringstid** (när organisationen faktiskt kände till eller registrerade versionen). Det kan exempelvis behövas för att förklara varför två beslut vid olika tidpunkter byggde på olika kända uppgifter. En sådan tvåtidsmodell är ett möjligt stöd, inte ett krav på en särskild databas eller regelmotor.

### Beslutstabeller, överlapp och undantag

Uttryckliga regler har ofta gränsvärden och undantag. Anta att en tabell anger normalbelopp för ansökningar upp till en viss summa och en annan regel ger undantag för särskilda grupper. Vad händer vid exakt gränsbelopp? Om både normalregel och undantag matchar, vilken ska vinna? Om ingen regel matchar, ska svaret vara avslag, manuell bedömning eller ett fel som behöver utredas?

Det räcker inte att tabellen är syntaktiskt giltig. Den behöver prövas för **luckor, överlapp, regelordning, konflikt och förväntade utfall**. I standarden Decision Model and Notation (DMN) beskrivs bland annat *hit policies* som anger hur flera matchande regler hanteras. Valet av sådan policy förändrar resultatet; det ska vara ett avsiktligt verksamhetsval och inte en omärklig standardinställning. DMN är ett användbart format för vissa typer av beslut, inte ett krav på produkt eller syntax i varje system.

En granskad modell bör kompletteras med testfall som inkluderar vanliga fall, gränsvärden, motstridiga villkor, ofullständiga uppgifter, giltighetsdatum och avsiktliga undantag. För särskilt betydelsefulla regler kan man jämföra en föreslagen version mot ett representativt urval historiska eller syntetiska fall och markera varje förändrat utfall för en ansvarig beslutsägare. En lyckad simulering är **underlag för godkännande**, inte ett bevis för att hela regelverket är rätt tolkat.

### Ett diagnostiskt exempel: tre kanaler och ett nytt ersättningsvillkor

I vårt exempel får webbportalen ett nytt regelpaket på måndagen. Handläggningssystemet uppdateras på tisdagen och en extern integration använder ännu föregående regelversion. En ansökan som skickas genom portalen får ett annat förslag än samma ansökan som registreras av en handläggare. Första reaktionen kan bli att införa en central regelmotor. Men en sådan åtgärd är för tidig innan man har undersökt grundorsaken.

Börja med att följa ett faktiskt beslut genom alla tre kanaler. Dokumentera de **verksamhetsmässigt relevanta indata**, beslutsbegrepp, effektivt datum, regelversion och utfall. Kontrollera sedan om skillnaden är avsiktlig – till exempel att ett äldre ärende faktiskt ska följa äldre regler – eller om den är en oplanerad skillnad i kod, data eller versionshantering.

Om samma regel är korrekt men publiceras vid olika tidpunkter behövs kanske en bättre versions- och releaseprocess. Om kanalerna tolkar samma begrepp på olika sätt behövs ett gemensamt semantiskt kontrakt. Om felaktig källdata leder till olika resultat behövs en förbättring i dataförmågan CAP-IT-04. Om däremot många team oberoende av varandra regelbundet bygger, testar och underhåller likvärdiga exekveringsmiljöer kan en gemensam plattformstjänst vara motiverad. **En central produkt löser inte oklar regelägare eller motstridigt verksamhetsmandat.**

### Vad ska fungera redan i generation 2?

För ett relevant regelverk ska organisationen kunna visa vem som ansvarar för innebörden, vilken version som användes, hur testerna utfördes och hur ett felaktigt beslut hanteras. Beslutsutfallet måste vara spårbart utan att känsliga beslutsdata sprids i vanliga tekniska loggar. Ansvariga måste kunna identifiera vilka konsumenter som påverkas av en regeländring och undvika att en ny version överraskar dem.

Väl fungerande generation 2 kräver inte en plattform. Det kräver att en regel kan ändras kontrollerat, att den nya innebörden är begriplig och att utfallet är granskningsbart. Om organisationen inte kan göra detta behöver den åtgärda **grundförmågan** innan den söker mer avancerad plattformisering.

### Två skilda förbättringsspår

**Spår A – rätta generationsarvet:** inventera beslutsregler och utpekade regelägare, reda ut semantiska skillnader mellan kanaler, versionera beslutskontrakt, komplettera regressionsfallen och säkerställ spårbarhet samt rutiner för rättelse av redan fattade beslut. Detta behövs även om varje domänteam fortsätter att köra regler lokalt.

**Spår B – förbered generation 3:** mät hur ofta flera team skapar samma typ av beslutstabeller, modelleringsverktyg, testmiljöer, revisionsspår och driftslösningar. Undersök ledtid och specialistberoende. Det är först när dessa **återkommande behov** är tydliga som ett standardiserat och självbetjänat tekniskt erbjudande sannolikt ger tillräcklig nytta.

## Generation 3 – förvaltade tjänster för regler och beslut

En plattformsorienterad organisation kan erbjuda återanvändbara tekniska tjänster för modellering, test, versionshantering och exekvering. Det innebär inte att en central instans ska bestämma vad verksamhetens alla regler betyder. Plattformsteamet ansvarar för **teknisk runtime, verktyg, drift och livscykel**. Regelägare och domänteam ansvarar för begrepp, giltighet, godkännande och konsekvenser.

Ett välavgränsat plattformserbjudande kan innehålla en standardiserad metod att publicera en beslutsmodell, en katalog över godkända modellversioner, automatiska kontraktstester, konsekvenssimulering, åtskilda utvecklings- och produktionsmiljöer samt möjlighet att förvalta flera giltiga versioner parallellt. Även loggning och åtkomst behöver styras så att endast behöriga kan granska känsliga beslutsunderlag. **Självbetjäning är inte att vem som helst får publicera bindande regler**; det är att rätt person kan utföra ett godkänt moment utan ovidkommande manuell administration.

### Bygg för hela regelns livscykel

En ny regelmodell ska kunna skapas och testas, men den behöver även kunna korrigeras, ersättas, tillfälligt spärras och avvecklas. Plattformen måste hantera hur äldre konsumenter påverkas och hur redan fattade beslut kan förklaras med äldre versioner. En teknisk rollback betyder att **framtida** körningar kan styras till en tidigare godkänd modell. Den gör inte ett redan meddelat beslut eller en verkställd betalning ogjord. I sådana fall krävs en verksamhetsmässig rättelse- eller omprövningsprocess.

Den praktiska kontrollen är att ett nytt team kan ta fram en modell för ett återkommande, lämpligt beslutsbehov utan separat teknisk specialbeställning. Teamet ska kunna köra fördefinierade tester, genomföra godkännandesteg, publicera med granskningsbar historik och därefter uppgradera eller avveckla modellen. Ett internt formulär som skapar ett ärende hos en specialist är inte nödvändigtvis självbetjäning.

### Riskerna med en central beslutsplattform

En gemensam regelmotor kan bli ett **koncentrerat felställe**: ett felaktigt bibliotek, en uppgradering eller ett tillgänglighetsproblem påverkar flera verksamheter. Den kan även bli organisatorisk flaskhals om varje domänändring kräver centrala specialister. Det går att minska risken med isolerade regelpaket, tydliga konsumtionskontrakt, kompatibilitetstester, kontrollerad utrullning och teknisk möjlighet att separera kritiska domäner.

En annan risk är att all möjlig affärslogik flyttas till generiska regelverktyg trots att den är mer begriplig i domänens egen kod. Då sprids domänansvaret och det blir svårare att förstå en applikation som helhet. Bedöm därför regelbeståndets **förändringstakt, självständiga förvaltningsbehov, antal konsumenter och krav på förklarbarhet** – inte om programvaran stödjer ett visst modelleringsformat.

## Hur avgör man om tekniken faktiskt är olämplig?

Återkommande problem räcker inte ensamt som bevis för att produkten är fel. Gör fyra prövningar: **(1) Innebörd och ansvar:** är det klart vem som äger regeln och vilken tolkning som gäller? **(2) Arkitektur:** kan flera konsumenter följa samma semantiska kontrakt och versionsstrategi? **(3) Implementation och integration:** är tester, dataåtkomst, konfiguration och publicering rätt utformade? **(4) Produktens faktiska begränsningar:** kan den versionera, exekvera och isolera regelmodeller med den spårbarhet, kapacitet och support som behövs?

En produkt kan vara olämplig om den efter korrekt konfiguration fortfarande inte kan bevara gamla regelversioner, inte stöder nödvändig säker isolering, inte håller avtalad svarstid och last vid relevant beslutsvolym eller saknar praktiskt stöd för styrd automatisering utan orimlig specialutveckling. Pröva också möjligheten att exportera modeller och tester samt om samma godkända regelpaket ger jämförbara resultat efter byte av runtime; en DMN-etikett i produktbladet garanterar inte identisk funktionalitet mellan motorer. Men om två team ger olika beslut för att de utgått från skilda verksamhetsdefinitioner blir inte resultatet korrekt genom att köpa en ny motor. Organisationen bör väga fyra åtgärdsvägar: **behålla**, **komplettera**, **ändra användning eller ägarskap**, respektive **ersätta** tekniken. Ett produktbyte bör vara en följd av verifierade begränsningar, inte ett antagande om vilken teknik som hör till generation 3.

## Generation 4 – verksamhetsnära och AI-assisterad regelförvaltning

I en mer verksamhetsnära utvecklingsmiljö kan medarbetare beskriva ett regelbehov och få hjälp av AI att föreslå beslutstabeller, formuleringar, testfall eller konsekvensanalyser. Det kan göra regeländringar snabbare. Men en genererad regel kan vara fel på ett övertygande sätt: den kan missa ett undantag, ge oväntad effekt för en viss grupp eller tolka ett juridiskt begrepp fel.

Det betyder att AI-stöd för att **skapa** en regel måste hållas isär från den godkända regelns **exekvering**. En språkmodell är inte automatiskt lämplig som enda mekanism för ett beslut som enligt verksamhetens krav ska vara deterministiskt och reproducerbart. Samtidigt kan beslut som kräver mänsklig bedömning eller statistiska förutsägelser ha andra lämpliga komponenter. Det viktiga är att organisationen redovisar **vilken typ av beslut som utförs** och vilka kontroller som motsvarar risken.

En AI-agent kan få mandat att föreslå ändringar men inte att aktivera dem. För högpåverkande beslut kan verksamheten kräva granskning av behörig person, oberoende testfall och en särskild publiceringsgrind. Mandatet behöver verkställas där publiceringen sker – inte enbart uttryckas som en instruktion till språkmodellen. Agentens förslag och använd data bör kunna granskas, med nödvändiga sekretessbegränsningar.

Även simulering har begränsningar. Historiska fall kan vara snedfördelade och syntetiska fall kan missa verkliga undantag. En jämförelse mellan versioner visar vilka utfall som **skulle** ha förändrats för testmängden, inte vad alla verkliga framtida konsekvenser blir. Organisationen behöver därför kombinera testning med sakgranskning, riskbedömning och kontrollerad uppföljning efter införandet.

### Tre beslutstyper kräver olika kontroller

Ett **deterministiskt regelresultat** följer av definierade regler och indata. Det ska kunna testas mot randvärden, versionsskillnader och förväntade utfall. En **mänsklig bedömning** kan däremot innehålla en avvägning som måste dokumenteras med beslutsfattare, skäl och överprövningsväg; att en handläggare klickar ”godkänn” gör inte bedömningen deterministisk. En **statistisk eller generativ AI-rekommendation** är ytterligare en kategori: sannolikheter eller genererat innehåll måste bedömas utifrån tillförlitlighet, datakvalitet, bias, förklarbarhet och hur rekommendationen används.

Kontrollbehovet bestäms av konsekvens och tillämpliga regler. Det är inte generellt förbjudet att använda AI som en komponent i beslutsstöd, men en språkmodells svar ska inte felaktigt beskrivas som ett reproducerbart uttryckligt regelutfall. Vid prövning av högriskfall behövs ett test som visar att en AI-rekommendation **inte kan kringgå verksamhetens behöriga besluts- och publiceringsgrind**. För automatiska beslut kan dessutom särskilda rättsliga krav gälla; dessa måste analyseras i respektive tillämpning.

### Vad måste fungera i generation 4?

En regeländring som AI föreslår ska vara spårbar till förslag, ändringar, tester, granskare och godkänd publiceringsversion. En agent utan korrekt mandat ska nekas att publicera, även om agenten uttrycker hög säkerhet i att ändringen behövs. Organisationen ska också kunna avbryta **framtida** regelkörningar för en felaktig version och identifiera redan påverkade beslut. Det senare kan kräva rättelse, manuell granskning eller återkoppling; teknisk tokenåterkallelse löser inte historiska verksamhetseffekter.

Här är det mer korrekt att tala om en **framåtblickande möjlig utvecklingsriktning** än om en generell egenskap hos alla framtida organisationer. Förmågan ska utvecklas proportionerligt till regelverkets betydelse och den faktiska mängden verksamhetsnära automation.

## De två plattformstjänsterna – uppgifter och verifiering

### PLS-008 – Besluts- och regelkörning

Denna tjänst exekverar explicita regler och beslut med stöd för versionsreferenser och spårbarhet. Den blir särskilt motiverad när reglerna har egen ändringstakt, flera konsumenter eller hårda krav på eftergranskning. Den är inte en generell ersättning för vanlig domänkod eller för CAP-IT-02:s processorkestrering.

I **G1** räcker lokal kod eller kontrollerade tabeller ofta, förutsatt att regelversion, ägare och beslutsgrund går att dokumentera. I **G2** behöver tjänsten – även om den är domänlokal – kunna hantera explicita datakontrakt, versionsväxling och konsumentkompatibilitet. I **G3** kan standardiserad exekvering erbjudas som en förvaltad självbetjänad tjänst med isolerade modellversioner, testgrindar och teknisk livscykel. I **G4** behöver AI-initierade ändringar stoppas vid publicering om korrekt attest saknas.

Ett konkret prov är att skicka samma beslutsscenario mot två definierade modellversioner och kontrollera att båda ger förväntade utfall, att besluten kan särskiljas i revisionen och att en felaktig version kan spärras **utan att avslutade beslut försvinner från historiken**.

### PLS-009 – Beslutsmodellering och simulering

Denna tjänst hjälper verksamhets- och domänexperter att uttrycka beslut, undersöka reglernas konsekvenser och skapa testbara modeller. Den får inte förväxlas med beslutsmandatet, generell AI-prediktion eller processorkestrering.

I **G1** kan ett kontrollerat kalkylark och dokumenterade testfall vara tillräckliga för begränsade regelverk. I **G2** ökar behovet av gemensamma begrepp, regressionskorpus och synliga skillnader mellan regelversioner. I **G3** kan modelleringsstöd, konsekvenssimulering och godkännande erbjudas som återanvändbara tjänster. I **G4** kan AI föreslå tabeller och tester, men de ska valideras och attesteras innan publicering när risken motiverar det.

Ett konkret prov är att införa avsiktliga överlapp, luckor och undantag i en testmodell. Verktyget och granskningsrutinen ska upptäcka eller synliggöra problemen så att ansvarig kan pröva konsekvenserna. Ett modelleringsverktyg som visar en grön teststatus utan att konfliktfall prövats ger falsk trygghet.

## Förflyttningarna mellan generationerna

**G1 → G2, kort historisk förflyttning:** Från lokalt sammanhållen regelimplementation till tydligt regelägarskap, gemensamma begrepp, versionssatta beslutsgränssnitt och kontroll av påverkan på flera system. Detta är en grundförmåga som behöver fungera även om organisationen fortsätter att använda lokal programkod.

**G2 → G3, den centrala förflyttningen:** Utgå från återkommande behov, inte en beslutad teknikprodukt. Identifiera de domäner där modellering, test, godkännande och driftsättning upprepas. Utforma ett begränsat, säkert tekniskt erbjudande; mät om teamen faktiskt kan använda det självständigt och om ledtider, regressioner eller specialistberoenden minskar. Tydliggör ansvar för regelns verksamhetsbetydelse respektive plattformens drift.

**G3 → G4, möjlig framtida utveckling:** När verksamheten får mer utvecklingsstöd kan regelförslag och testgenerering delegeras i begränsad omfattning. Godkännande, teknisk publicering och uppföljning behöver förbli spårbara och riskanpassade. AI kan ge förslag men får inte automatiskt upphöjas till regelägare.

## Diagnostiska tester och indikatorer

| Prov | Vad bör kunna visas? | Vad kan resultatet betyda? |
|---|---|---|
| Historiskt beslut | Regel- och indataversion, giltighetsgrund, tillåtna indata-/källreferenser, ansvarig beslutsväg och uttryckliga begränsningar i möjlig reproduktion | Saknas de är G2-förmågan bristfällig även med modern motor |
| Övergångsregel vid årsskifte | Äldre och nya ansökningar, beslut efter brytpunkt och avsiktlig tillämpning av övergångsbestämmelse | Visar om giltighet styrs av beslutad verksamhetsregel eller oavsiktlig serverklocka |
| Förändrad extern källa | Separera historiskt registrerat underlag från dagens registeruppgift; dokumentera vad som inte längre går att återskapa | Avslöjar falska löften om exakt historisk reproduktion |
| Belastning och modellbyte | Mät latens och felsvar vid realistisk last; jämför exporterad modell i målmiljö med godkända referensfall | Synliggör verkliga produktbegränsningar respektive brister i implementering |
| Samma fall, flera kanaler | Förväntat överensstämmande utfall och förklaring av avsiktliga skillnader | Skillnader kan bero på semantik, data, versioner eller felaktig kod |
| Ny och gammal version | Simulerade resultat, gränsfall och identifierade konsumenter | Visar om versionshantering och regression är tillräckliga |
| Regelöverlapp och lucka | Förväntat konfliktbeteende respektive explicit hantering av saknade träffar | Blottlägger oavsiktlig regelordning eller otillräckliga tester |
| Självbetjänad ändring | Modell går att testa, attestera, publicera, ändra och avveckla utan specialbeställning | Testar G3-erbjudandets verkliga mognad |
| AI-förslag utan mandat | Nekad publicering och komplett granskningsspår | Prövar att G4-kontrollen sitter i betrodd tjänst |

Exempel på mätetal är andelen beslut med tillförlitlig versionsreferens, andelen ändringar med granskad konsekvensjämförelse, antalet oavsiktliga beslutsavvikelser mellan kanaler och ledtid från godkänd ändring till kontrollerad användning. Målvärden måste sättas efter verksamhetens risk och beslutens betydelse.

## Avgränsningar och källor

CAP-IT-03 ansvarar för att uttryckliga regler kan modelleras, tillämpas och granskas. **CAP-IT-02** ansvarar för processens ordning och tillstånd; **CAP-IT-04** för datatjänster och informationshantering; **CAP-IT-06** för integrationsmekanismer; **CAP-IT-07** för identitet och tekniskt stöd för auktorisation; **CAP-IT-10** för utvecklings- och leveranskedjan och **CAP-IT-09** för driftbarhet. Regler för verksamhetsmandat och rättslig giltighet måste ägas av verksamheten även när tekniskt stöd tillhandahålls centralt.

Källmodellens definition och kopplingarna till PLS-008/PLS-009 och PLT-002 är hämtade från *Förmågeöversikt – tekniska IT-förmågor* respektive *Plattformsöversikt – konceptuella plattformar*, baseline v1.1. Generationsramen bygger på *Från systemdrift till digital självständighet*. Tekniska resonemang om beslutstabeller kompletteras av [OMG DMN 1.6](https://www.omg.org/spec/DMN/1.6/) (formell version; 1.7 finns i beta) och [Camundas dokumentation om DMN:s hit policies](https://docs.camunda.io/docs/components/best-practices/modeling/choosing-the-dmn-hit-policy/). AI-delarna kompletteras med [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) och [NIST:s profil för generativ AI](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence). **Prioriteringar, diagnoser och val mellan central och lokal implementation är analytiska rekommendationer**, inte uppgifter om en faktiskt undersökt organisation.

