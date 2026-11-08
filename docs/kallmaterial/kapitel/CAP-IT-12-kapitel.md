# Cybersäkerhet och tekniskt skydd

*CAP-IT-12 · Faktaboksunderlag · version 2.0 · 7 november 2026*

Ett ärendehanteringssystem fungerar väl, sett till varje enskild komponent. Ändå visar en incident hur svårt det är att skydda helheten. En sårbarhet finns i en tjänst som ingen har fört upp i den gemensamma inventeringen. Säkerhetsteamet ser ett larm men kan inte säkert knyta det till den berörda applikationen. Utvecklingsteamet känner till en möjlig uppdatering men vet inte vem som får godkänna ett driftstopp. Samtidigt kräver en annan tjänst ett nytt brandväggsundantag för att kunna fungera.

Detta är ett igenkännbart läge i **generation 2**. Tekniken har delats upp i många tjänster, men skydd, detektion och åtgärdsansvar fungerar inte alltid som en sammanhållen kedja. Frågan är sällan bara vilket säkerhetsverktyg som ska köpas. Den handlar om att veta vad som behöver skyddas, vilka skydd som faktiskt fungerar och hur organisationen kan göra det säkra arbetssättet lättare att följa.

## Vad förmågan handlar om

**Cybersäkerhet och tekniskt skydd** omfattar de tekniska mekanismer som förebygger, upptäcker, analyserar och begränsar cyberangrepp och oönskad exponering av digitala resurser. Det kan handla om skydd av klienter och körande applikationer, sårbarhets- och exponeringshantering, detektion av säkerhetshändelser, analys av incidenter, informationsskydd, kryptografiska skydd och automatiska säkerhetskontroller i utvecklings- och leveransflöden.

Det är inte liktydigt med hela organisationens informationssäkerhet. Verksamheten måste fortsatt avgöra vilka uppgifter som är skyddsvärda och vilka risker som kan accepteras. Identitetsförmågan (CAP-IT-07) tillhandahåller tekniska identiteter och tillitsrelationer; nätverksförmågan (CAP-IT-13) erbjuder konnektivitet och segmentering; utvecklings- och leveransförmågan (CAP-IT-10) äger själva leveransflödet; driftbarhet (CAP-IT-09) hanterar generell observerbarhet och återställning. Säkerhetstjänsterna samverkar med dessa, men övertar inte deras respektive ansvar.

En uppdaterad hotbild gör vissa skydd mer brådskande. Den upphäver inte den grundläggande principen: **kontrollerna ska dimensioneras efter verkliga risker och behöver kunna verifieras**. En dyr central säkerhetsplattform har begränsat värde om kritiska system inte är anslutna, åtgärder saknar ägare eller varningar drunknar i brus. Det finns inte heller någon enskild teknisk tjänst som kan ersätta hela förmågan. Säkerhetsdetektion, informationsskydd, identitet, applikationskontroller och incidentberedskap måste fungera tillsammans utan att deras ansvar blandas ihop.

## När är förmågan relevant?

Alla organisationer med digitala resurser behöver ett grundläggande tekniskt skydd. Däremot varierar behovet av specialiserade tjänster beroende på exponering mot internet, informationens skyddsvärde, antal tjänster, externa integrationer, leverantörskedjor, möjlighet till verksamhetsskada och hur snabbt miljön förändras. Kraven påverkas även av lagar, avtal och branschspecifika skyldigheter, som måste utredas separat för respektive organisation. En offentlig informationssida och en tjänst som fattar eller verkställer ekonomiska beslut kräver inte samma kontrollpaket.

Pröva därför behovet konkret. Vilka system är exponerade för obehöriga? Vilka uppgifter kan lämna organisationen? Vilka komponenter uppdateras ofta och av vem? Var finns administrativa privilegier och kritiska beroenden? Hur snabbt behöver skadlig aktivitet upptäckas och begränsas? Har skydden testats i de flöden där de förväntas fungera?

Det är också viktigt att skilja mellan **kritisk säkerhetsfunktion** och **kritisk gemensam plattformstjänst**. Sårbarheter behöver hanteras i alla generationer; det följer inte att varje organisation måste äga en stor, central exponeringsplattform. Extern anslutning, HSM och avancerad Data Loss Prevention (DLP) kan vara avgörande för vissa tillämpningar och helt irrelevanta för andra.

## Kort tillbakablick: generation 1 och arvet in i generation 2

Med ett mindre antal sammanhållna IT-stöd gick säkerhetsskyddet ofta att organisera kring servrar, klienter, nätverksgränser och tydligt utpekade systemägare. Specialister kunde härda maskiner, hantera antivirus, granska loggar och genomföra patchning via etablerade driftprocesser. Modellen kunde ge ett robust skydd för förhållandevis stabila miljöer, men förutsatte god ordning på tillgångar, uppdateringar och behörigheter. Säkerhet var inte något som först blev nödvändigt när monoliterna delades upp.

Vid övergången till flera tjänster ökar antalet exponerade gränssnitt, programvaruberoenden och möjliga vägar genom en miljö. En säkerhetsincident kan beröra applikationskod, containrar, API:er, integrationsflöden och identiteter samtidigt. Ett verktyg som tidigare visade att servrarna var patchade ger då inte hela bilden av de risker som finns i applikationskedjan.

**Kvarvarande generationsarv** kan yttra sig som oinventerade tjänster, gemensamma privilegierade konton, säkerhetsskanning endast före större releaser, larm utan ansvarig mottagare eller undantag som aldrig återprövas. Sådana brister behöver rättas för att generation 2 ska fungera väl. De utgör inte i sig ett argument för att först köpa en ny plattformsprodukt.

## Generation 2 – skydda en distribuerad tjänstekedja

### Vilket stöd behöver finnas?

Organisationen behöver veta vilka tillgångar och exponerade gränssnitt som faktiskt finns, inklusive programvaruberoenden och tjänster som bara används av andra tjänster. Sårbarheter behöver värderas med hänsyn till känd exploatering, faktisk exponering, verksamhetskonsekvenser och möjliga motåtgärder – inte enbart till ett tekniskt poängtal. Ett lågt tekniskt allvarlighetsvärde utesluter inte hög verksamhetsrisk, och ett högt värde på en oåtkomlig komponent behöver inte prioriteras före en aktivt utnyttjad exponering. Det måste gå att ange vem som ska åtgärda ett fynd och att kontrollera att åtgärden fick avsedd effekt.

Skyddet bör omfatta relevanta klienter, servrar, containrar, arbetslaster och applikationsgränssnitt. Intern trafik ska inte betraktas som automatiskt säker. Samtidigt är en kontroll inte nyttig bara för att den går att aktivera. Ett skydd som konsekvent bryter legitima integrationsflöden behöver justeras och utvärderas, inte bara göras strängare.

Säkerhetshändelser måste kunna knytas till en tjänst, ägare och faktisk användarpåverkan. Säkerhetsdetektion kräver egna analysregler, hotkontext och incidenthantering, men kan återanvända tekniska loggar och spårbarhetsdata från CAP-IT-09. Här finns en viktig avgränsning: ett operativt driftslarm och en misstänkt angriparaktivitet kan bygga på samma data men behöver olika analys och beslut.

Skydd i bygg- och leveransflöden behöver också fungera. Kod, beroenden, hemligheter, containerartefakter och infrastrukturdefinitioner kan undersökas automatiskt. Applikationsteamet måste förstå resultatet och kunna rätta problemet. Säkerhetsfunktionen behöver definiera trösklar, stödja riskbedömningar och hantera undantag, utan att varje rutinändring fastnar i en separat granskning.

### Ansvar och vanliga fallgropar

Verksamhetsansvariga bedömer konsekvenser och accepterar kvarvarande verksamhetsrisk inom sitt mandat. Säkerhetsfunktionen utformar principer, följer riskbilden och samordnar säkerhetsincidenter. Plattformsteam tillhandahåller tekniska skydd med kända egenskaper. Applikations- och datateam ansvarar för hur skydden används, för egna sårbarheter och för resursnära behörighetskontroller. Utan denna ansvarskedja finns risken att alla ser samma larm men ingen tar hand om det.

En vanlig fallgrop är att likställa många verktyg med god säkerhet. En annan är att mäta mängden insamlad telemetri utan att kontrollera om detektionsregler, bemanning och incidentåtgärder faktiskt fungerar. En annan är att belöna antalet genomförda skanningar utan att veta om allvarliga exponeringar verkligen minskar. En tredje är att öka nätverksåtkomsten eller ge generella undantag för att få distribuerade tjänster att fungera, i stället för att lösa den bakomliggande tjänste- och identitetsarkitekturen. Säkerhetsarbete som enbart sker före driftsättning räcker inte när tjänster och hot förändras löpande.

### Indikatorer på tillräckligt stöd

- En representativ extern tjänst går att knyta till ägare, aktuell programvaruinventering, exponering och skyddskrav. Okända tillgångar upptäcks inom en fastställd tid.
- Ett simulerat allvarligt sårbarhetsfynd leder till riskbedömning, utsedd åtgärdsansvarig, spårbar åtgärd och omtest inom överenskommen tid.
- En kontrollerad misstänkt attack kan följas från detektionssignal till incidentbeslut, avgränsning och lärdomar; mätningen omfattar både missade signaler och falsklarm.
- Säkerhetskontroller i leveransflödet kan påvisa otillåtna hemligheter eller sårbara beroenden och ger begriplig återkoppling till rätt team.
- Skydd för flera samverkande tjänster kan prövas utan att legitim kommunikation generellt måste öppnas eller undantas.

### Indikatorer på olämplig teknik eller plattform

**Täckning:** Säkerhetsprodukten ser traditionella servrar men saknar stöd för aktuella containrar, API:er eller andra faktiska arbetslaster. Jämför täckningen mot verklig tillgångsinventering före produktbeslut.

**Interoperabilitet:** Händelser saknar gemensamma identiteter eller kan inte kopplas till tjänster och ägare. Undersök datakvalitet och integrationer före produktbyte.

**Automatiserbarhet:** Skydd och scanning kräver manuell installation vid varje release trots återkommande likartade behov. Pröva befintliga API:er och leveransintegration.

**Säkerhet och underhåll:** Själva säkerhetsprodukten saknar relevanta uppdateringar, säkra administrativa gränssnitt eller fungerande åtkomstkontroller. Detta kan motivera snabb åtgärd, inklusive utbyte.

**Kostnad och signalvärde:** Larmvolymen eller licenskostnaderna växer utan motsvarande upptäckt och riskreduktion. Mät faktiskt utfall, täckning och totalkostnad.

**Inlåsning och återställbarhet:** Det går inte att exportera regler, fynd eller revisionsunderlag på ett användbart sätt. Undersök konsekvensen för framtida migrering och incidenthantering.

En negativ indikator pekar på ett undersökningsbehov, inte automatiskt på ett produktfel. Problemet kan finnas i **produkt, konfiguration, integration, arkitektur, kompetens eller ansvar**.

### Diagnostik: var uppstår bristen?

När en säkerhetskontroll inte fungerar bör man först skilja mellan **produktbegränsning**, **felaktig konfiguration**, **bristande integration**, **otydligt ansvar** och **otillräcklig kompetens eller kapacitet**. Samma symptom kan ha olika orsaker. Att ett sårbarhetsfynd inte åtgärdas kan exempelvis bero på att verktyget missar tillgången, att fyndet aldrig kopplas till ansvarigt team eller att det saknas ett säkert sätt att uppgradera komponenten.

Pröva ett representativt fall från början till slut: välj en faktisk skyddsvärd tjänst, introducera ett godkänt testfynd i en isolerad testmiljö och följ upptäckt, riskvärdering, ansvarstilldelning, åtgärd och omtest. Dokumentera var kedjan bryts och pröva först rimliga korrigeringar i befintliga lösningar. Byt produkt när den saknar nödvändig funktion, support eller ekonomi – inte bara för att en process är långsam. Testerna ska vara godkända och utformade så att de inte innebär verklig skada eller spridning av känslig information.

### Två förbättringsspår i generation 2

**Spår A – Åtgärda den distribuerade miljöns säkerhetsbrister.** Etablera en relevant tillgångs- och exponeringsbild, ägare till skydd och åtgärder, meningsfull detektion, säkra identitets- och nätverksrelationer och fungerande incidentrutiner. Detta behöver fungera även om organisationen stannar kvar i generation 2.

**Spår B – Bygg kapacitet för återkommande självbetjäning.** När samma skydd måste beställas, installeras och anpassas för många team bör organisationen överväga standardprofiler, automatiserad anslutning, gemensamma kvalitetströsklar och tekniska guardrails. Målet är att minska repetitivt manuellt arbete utan att försvaga riskbedömningen.

### Ett diagnostiskt prov

Välj en ny, internetexponerad API-tjänst. Följ den från kodändring till driftsättning och en simulerad säkerhetshändelse. Vem klassar behovet? Hur får tjänsten sin skyddsprofil? Vilka fynd blockerar en leverans, och vilka hanteras som dokumenterade undantag? Kan man se tjänsten i säkerhetsövervakningen, begränsa ett pågående angrepp och avveckla behörigheter och skydd när tjänsten tas bort?

Om svaret är att organisationen saknar fungerande skydd, spårbarhet eller ansvar är huvudfrågan en **grundbrist i generation 2**. Om detta fungerar men kräver samma långa manuella kedja för varje ny tjänst finns ett mer konkret motiv att utveckla **generation 3**.

## Övergången 2 → 3 – från säkerhet som beställning till säkerhet som standard

Övergången innebär att säkerhetsfunktioner för återkommande behov utvecklas till förvaltade, konsumerbara tjänster. En applikationsprofil kan då medföra en definierad nivå av sårbarhetsanalys, körmiljöskydd, relevanta loggar, API-skydd och regler för hemligheter, utan att teamet måste beställa varje kontroll separat. De tekniska reglerna måste vara versionerade, möjliga att testa och anpassade till olika riskklasser.

Det räcker inte att installera en gemensam säkerhetsplattform. En plattform behöver ha produktansvar, dokumenterade gränssnitt, stöd för uppgradering och avveckling samt återkoppling till konsumenterna. Den måste hantera både standardfall och undantag. En policy som inte kan förstås eller felsökas riskerar att skapa kringgående beteende. En policy som bara finns på papper hjälper inte heller när teamen själva driftsätter nya tjänster.

**Beredskap för förflyttningen** märks när organisationen har tydliga tillgångs- och tjänsteägare, kan klassificera vanliga riskprofiler, mäter resultatet av befintliga kontroller och har team som kan förvalta tekniska säkerhetserbjudanden som produkter. Saknas dessa förutsättningar bör de byggas parallellt med de första automatiserade profilerna.

## Generation 3 – säkerhet inbyggd i plattformens erbjudanden

I generation 3 erbjuds skydd där de används. Ett utvecklingsteam kan välja en godkänd applikationsprofil där lämpliga säkerhetskontroller redan är aktiverade. Säkerhetsfunktionen definierar och följer principer; plattformsteamet förvaltar kontrollernas tekniska beteende; applikationsteamet rättar sina fynd och ansvarar för sina lokala risker.

**Vanliga fallgropar:** För många tvingande standardkontroller utan riskdifferentiering, falsklarm som ingen hinner utreda, undantag som aldrig löper ut och en plattform som automatiserar nya resurser men inte ändring eller avveckling. Det är också ett misstag att anta att en central säkerhetsprofil automatiskt skyddar applikationskod från logiska sårbarheter.

**Indikatorer på fungerande stöd:** En ny standardtjänst får rätt grundskydd direkt; policyändringar kan testas och rullas ut stegvis; säkerhetsfynd når ansvarigt team med åtgärdsförslag; undantag har motivering, ägare och slutdatum; avslutade tjänster lämnar inte kvar överflödiga behörigheter, insamlingsflöden eller skyddsregler.

**Indikatorer på olämplig teknik eller plattform:** Skyddsprodukten saknar API:er för policy och livscykel, klarar inte tjänsternas förändringstakt, orsakar frekventa falska blockeringar utan möjlighet till säkra undantag, kan inte exportera mätresultat eller kräver ett centralt specialistteam för varje normalt beslut. Men även här måste organisationen undersöka om hinder beror på produkten eller hur den har organiserats.

Förflyttningen ska mätas i färre oskyddade tjänster, kortare tid till kontrollerad åtgärd och mindre onödig väntan – inte i antalet installerade säkerhetsverktyg.

## Övergången 3 → 4 – flera kan skapa lösningar, men riskansvaret består

När verksamhetsnära medarbetare kan ta fram lösningar med AI förändras hastigheten och spridningen. Nya applikationer, automatiseringar och agentflöden kan skapas snabbare än traditionella granskningsprocesser hinner hantera dem. Då behöver godkända utvecklings- och körvägar inkludera säkerhetskontroller från början, samtidigt som riskfyllda ändringar fortfarande kan kräva mänsklig granskning.

En AI-agent som läser ett dokument, väljer verktyg och utför en åtgärd innebär risker som inte kan lösas med nätverksfilter eller DLP ensamt. Otillförlitligt innehåll kan försöka påverka agentens instruktioner; en överprivilegierad verktygskoppling kan ge alltför stort handlingsutrymme; utdata kan innehålla information som inte ska lämnas vidare. Därför krävs samverkan med identitet, datahantering, processansvar, utvecklingsplattform och de system som verkställer åtgärderna.

Det är inte säkert att varje organisation behöver egna AI-säkerhetsprodukter. Att upptäcka en risk genom testning eller detektion är dessutom något annat än att tekniskt kunna förhindra handlingen. Auktorisation måste verkställas av den skyddade tjänsten eller dess betrodda kontrollpunkt, inte antas följa av en säkerhetsanalys. Men när agentbaserade lösningar används för viktiga verksamhetsuppgifter behövs ändamålsbegränsade mandat, prövning av verktyg och indata, löpande utvärdering, handlingsbar loggning och effektiva sätt att stoppa fortsatt aktivitet. Ett stopp gör inte redan skickade meddelanden eller genomförda beslut ogjorda.

## Generation 4 – riskstyrt tekniskt skydd även för verksamhetsnära lösningar

I generation 4 används plattformens skydd också av personer som inte är specialister på säkerhet eller systemutveckling. Standardvägen behöver därför vara säker och begriplig utan att användarna måste konfigurera varje teknisk kontroll. Riskklassade mallar bör kunna avgränsa dataåtkomst, externa anrop, verktygsrättigheter, resursåtgång och livslängd. Högriskåtgärder kan behöva uttryckligt godkännande eller begränsas till särskilt förvaltade system.

**Vanliga fallgropar:** Att förlita sig på en AI-instruktion som enda säkerhetskontroll; att ge agenten alltför breda rättigheter; att registrera för lite för att kunna utreda en incident eller så mycket känsligt innehåll att loggningen blir en ny exponeringsrisk; samt att använda samma kontrollprofil för en intern prototyp och ett verksamhetskritiskt beslutsflöde.

**Indikatorer på fungerande stöd:** Det går att identifiera ägare, risknivå och tekniska rättigheter för verksamhetsutvecklade lösningar; riskfyllda verktygsanrop kan nekas vid den skyddade resursen genom samverkan mellan identitet, applikation och säkerhetskontroll; en genomförd kontrollövning visar att misstänkt agentaktivitet upptäcks och att fortsatt åtkomst kan spärras; kostnads- och trafikbegränsningar fungerar även vid missbruk.

**Indikatorer på olämpliga teknikval:** Plattformen kan inte tillämpa begränsningar på verktygsanrop, kontrollera relevanta dataflöden eller spåra agentkörningar på ett integritetssäkert sätt. Säkerhetskontrollerna kan inte skilja låg- från högrisklösningar, saknar utvärderingsmöjligheter eller går endast att använda genom manuella specialistinsatser. Dessa tecken bör undersökas mot faktiska användningsfall; tekniken kan fortfarande vara lämplig för andra arbetslaster.

**Beredskap:** Det finns riskklassning, tydligt verksamhetsansvar, säkra utvecklings- och körvägar, tekniskt begränsade mandat och rutiner för att utreda incidenter. Saknas detta bör organisationen begränsa självständigt handlingsutrymme snarare än förutsätta att AI-tekniken kompenserar för bristerna.

## Ett genomgående exempel – den nya ärendetjänsten

En myndighet har flera tjänster för att ta emot, bereda och besluta om ärenden. I generation 2 upptäcks en sårbar komponent i API:t för dokumentuppladdning. Det visar sig att säkerhetsskanning täcker delar av koden, men inte alla beroenden. Teamet kan rätta felet, men det tar tid att samordna test, driftsättning och säkerhetsuppföljning. Först behöver organisationen se till att tillgångar, ansvar och åtgärdskedja är begripliga.

När många team återkommande behöver samma säkerhetskontroller införs i generation 3 en standardprofil för internetexponerade API:er. Den omfattar bland annat kontroller i leveransflödet, relevant API-skydd, sårbarhetsuppföljning och säkerhetshändelser som kopplas till rätt tjänst. Undantag är möjliga men tidsbundna och spårbara. Då blir säkerhet ett återanvändbart erbjudande snarare än ett separat projekt i varje release.

I ett tänkbart generation 4-scenario skapar verksamheten en assistent som sammanställer ärendeunderlag. Den får läsa avgränsade uppgifter men får inte själv godkänna beslut. Säkerhets- och identitetskontrollerna behöver kunna hålla isär dokumentinnehåll, modellförslag och behöriga åtgärder. Ett manipulerat dokument ska inte kunna ge assistenten rätt att skicka information till en extern mottagare. Kontroll måste ske där verktygsanrop och dataåtkomst verkställs, inte enbart genom en textinstruktion till modellen.

## Praktisk bedömning – vilka åtgärder är rimliga?

Börja med ett faktiskt tjänsteflöde, ett verkligt skyddsbehov och ett konkret test. Går det att se tillgången, upptäcka en misstänkt händelse, utse en ansvarig, begränsa exponeringen och verifiera effekten? Om svaret är nej handlar första åtgärden om att få grundskyddet att fungera. Om skyddet fungerar men varje standardtjänst behöver återkommande handpåläggning bör gemensamma erbjudanden prövas.

Pröva teknikbeslut i fyra steg: **behåll** när den befintliga lösningen fungerar med acceptabel risk och kostnad; **komplettera** när en avgränsad brist kan åtgärdas; **förändra användning och ansvar** när tekniken räcker men organisationen inte gör det; **ersätt** när grundläggande produktbegränsningar, supportbrister eller ekonomi hindrar en rimlig lösning. Beslutet bör bygga på uppmätt täckning, tid till åtgärd, faktisk incidentförmåga, användbarhet och livscykelkostnad.

Inget generationssteg behöver genomföras samtidigt för alla IT-stöd. Ett kritiskt legacy-system kan behöva en noggrant styrd skyddsprofil, medan en återkommande standardtjänst passar för självbetjäning. Nyare är inte alltid bättre; bättre är det stöd som tillför tillräcklig säkerhet med begripliga kostnader och tydligt ansvar.

## Teknisk orientering – plattformstjänster som stöder förmågan

Källmodellen knyter **elva tjänster** till CAP-IT-12. De är inte elva obligatoriska produkter eller projekt:

| Tjänst | Huvudsaklig uppgift | När är den särskilt relevant? |
|---|---|---|
| PLS-048 Sårbarhets- och exponeringshantering | Upptäcka, prioritera och följa exponeringar | Många system, beroenden och externa angreppsytor |
| PLS-050 Säkerhetsdetektion och analys | Identifiera misstänkt aktivitet | Skyddsvärda tjänster och relevanta hot |
| PLS-051 Säkerhetsforensik och teknisk incidentanalys | Förstå händelseförlopp och bevis | Incidentberedskap och utredningskrav |
| PLS-077 Endpointskydd | Skydda användarenheter | Förvaltade eller utsatta klienter |
| PLS-078 Workloadskydd | Skydda server-, VM- och containerarbetslaster | Körmiljöer med relevanta angriparytor |
| PLS-086 Programvarusäkerhetsanalys | Analysera kod, beroenden, hemligheter och artefakter | Egenutvecklad eller ändrad programvara |
| PLS-053 Tekniska säkerhetsguardrails och policy enforcement | Verkställa tekniska regler automatiskt | Återkommande standardleveranser och självbetjäning |
| PLS-087 Webb- och API-skydd | Skydda exponerade webbtjänster och API:er | Internetexponerade applikationer |
| PLS-069 Informationsskydd och Data Loss Prevention | Minska oavsiktligt eller otillåtet informationsutflöde | Känsliga uppgifter och relevanta delningsvägar; särskild DLP-teknik är inte alltid nödvändig |
| PLS-052 Kryptografisk nyckel- och HSM-tjänst | Skydda nycklars livscykel och vid behov använda HSM | Hantering av skyddsvärda kryptografiska nycklar; HSM vid särskilda krav |
| PLS-079 Säker extern system- och myndighetsanslutning | Säkra externa anslutningsprofiler | Återkommande partner- eller myndighetsutbyte |

En del av tjänsterna stöder även andra förmågor. Det ska inte tolkas som dubbla investeringar. Workloadskydd samverkar exempelvis med körmiljöförmågan, och programvarusäkerhetsanalys med utvecklings- och leveransförmågan.

## Källor och avgränsningar

**Primära underlag:** *Från systemdrift till digital självständighet*, *Förmågeöversikt – tekniska IT-förmågor* (modellbaseline v1.1) och *Plattformsöversikt – konceptuella plattformar* (modellbaseline v1.1). Tjänsternas ID, namn och principiella avgränsningar är hämtade därifrån. Den föreslagna generationsindelningen för varje skyddstjänst och indikatorerna är författarens arkitekturbedömningar.

**Extern referensram:** NIST Cybersecurity Framework 2.0 (2024) för sambandet mellan att styra, identifiera, skydda, upptäcka, reagera och återhämta; NIST SP 800-218 SSDF (2022) för säker utveckling; CISA *Secure by Demand* för anskaffning av säkra teknikprodukter; OWASP GenAI Security Project och *OWASP GenAI LLM Top 10 2026* (publicerad augusti 2026) för risker i AI- och agentapplikationer. OWASP:s risklista är en vägledning, inte en fullständig kontrollkatalog. Officiella källadresser återfinns i YAML-modellen. Dessa referenser är vägledning och innebär inte att en särskild plattformstjänst blir obligatorisk i en viss generation.

**Begränsning:** Materialet är inte en revision av en viss organisations faktiska skydd, inte en fullständig rättslig eller regulatorisk analys och inte en bindande kravkatalog. Generation 4 beskriver ett framtidsinriktat tillämpningsmönster med större osäkerhet än etablerade driftsätt.
