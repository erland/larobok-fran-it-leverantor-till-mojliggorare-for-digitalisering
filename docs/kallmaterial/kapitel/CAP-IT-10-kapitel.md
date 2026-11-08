# Utveckling och teknisk leverans

*CAP-IT-10 · Faktaboksunderlag · version 2.0 (kritiskt granskad) · 7 november 2026*

Ett team kan ändra och leverera en mindre tjänst på en dag. Ändå tar det veckor innan förändringen fungerar i produktion. En annan tjänst behöver uppgraderas, en integrationspartner måste testa ett nytt kontrakt och säkerhetskontrollerna görs sent. De enskilda teamens tempo har ökat, men den samlade leveransen är fortfarande långsam och riskfylld. I en organisation som gått från sammanhållna system till mindre tjänster är detta en välbekant motsättning.

Utveckling och teknisk leverans handlar om att göra förändringar **spårbara, testbara, reproducerbara och säkra** – inte bara om att skriva kod snabbt. Kapitlet utgår från generation 2: arkitekturen är distribuerad, men tidigare rutiner och organisatoriska gränser kan finnas kvar. Det beskriver dels vad som måste fungera redan där, dels när det blir motiverat att bygga gemensamma självbetjänade leveransvägar och i förlängningen stödja en bredare, AI-assisterad utveckling.

## Vad förmågan handlar om

Förmågan omfattar den tekniska kedjan från källkod och versionshanterade deklarationer till test, bygg, paketering och driftsättning. Den omfattar också verktyg och standardiserade utvecklingsgrunder som gör att en ändring kan upprepas, granskas och föras mellan miljöer. Versionshantering visar vad som ändrats och av vem. Kontinuerlig integration (CI) bygger och kontrollerar ändringar regelbundet. Kontinuerlig leverans eller driftsättning (CD) förbereder eller genomför säkra releaser. En *artefakt* är det versionsbestämda resultatet av en byggprocess, exempelvis ett programvarupaket eller en containerimage.

Teknisk leverans är inte detsamma som att organisationen har automatiserat varje verksamhetsbeslut kring en release. Säkerhetskrav, förändringsrisk och verksamhetsgodkännande kan fortfarande kräva mänskliga beslut. Förmågan ska heller inte överta själva körmiljön (CAP-IT-08), övervakning och återställning (CAP-IT-09), identitetsmekanismer (CAP-IT-07) eller säkerhetsstyrning (CAP-IT-12). Leveranskedjan behöver använda och integrera dessa, men ansvaren är skilda.

## När behövs förmågan?

Alla som ändrar egen programvara behöver någon form av kontrollerad teknisk leverans. Om ett litet system ändras sällan kan en enkel, dokumenterad och reproducerbar process räcka. För organisationer med många team, täta ändringar och delade beroenden blir konsekvensen av varierande leveransrutiner större. Relevansbedömningen bör utgå från ändringsfrekvens, beroenden, risk vid fel, krav på spårbarhet och hur mycket arbete som återkommer mellan team.

Det går att ha en kritisk leveransförmåga utan en central CI/CD-plattform: en verksamhetskritisk monolit behöver också verifierade releaser. Omvänt ger ett gemensamt verktyg för alla team ingen garanti för kvalitet. Det är hur förändringar hanteras som behöver bedömas, inte antalet inköpta verktyg.

## Tillbakablick: generation 1 och det som inte följde med

I en miljö med få sammanhållna system kunde en release planeras som en större samlad händelse. Teamen kände ofta miljöerna väl. Manuell sammanställning av paket, godkännande, driftsättning och återgång kunde fungera när ändringarna var få och beroendena överblickbara. Den modellen hade samtidigt svagheter: personberoende byggsteg, svåråterskapade produktionspaket och sena tester.

När systemen delades upp i mindre tjänster fick de olika delarna egna versioner och egna förändringstakter. Det skapade ett behov av automatiska tester, kontrakt mellan tjänster och kontroller av vilken kombination av versioner som fungerar. Men förändringen i arkitekturen genomfördes inte alltid samtidigt som leveransrutinerna moderniserades.

**Kvarvarande generationsarv** syns när enskilda team har olika byggscript utan gemensamma säkerhetskontroller, när integrationstester sker först inför en samlad produktionssättning, eller när den som ska godkänna en release saknar överblick över beroenden och risk. Problemen kan också bestå av oklara rättigheter för produktionsdriftsättning eller av att viktiga byggnycklar lagras i personliga konton. Detta är grundproblem som behöver åtgärdas även om en övergång till generation 3 inte planeras.

## Generation 2 – många leveranser, en beroende helhet

### Vilket stöd som behövs

I generation 2 behöver varje tjänst ha en identifierbar källa, version, ägare och en testbar väg till produktion. Byggen bör vara automatiserade och ge spårbara artefakter. Tester behöver täcka den egna tjänsten men också gränssnitt och kontrakt mot andra. Säkerhetskontroller bör upptäcka kända sårbarheter, läckta hemligheter och riskabla beroenden på ett sätt som ger möjlighet till åtgärd före driftsättning.

Det räcker inte att flera tjänster har varsin fungerande pipeline. En ändring kan vara korrekt i sitt team men fel i hela tjänstekedjan. Därför behövs versionshanterade API- och meddelandekontrakt, kompatibilitetsprov och en tydlig rutin när en producent eller konsument ändras. Där ett system använder databasändringar måste releaseplanen även hantera bakåtkompatibilitet och återgång. Att återställa en tidigare programversion ångrar inte automatiskt en redan genomförd datamigrering.

Leveranskedjan behöver också skyddas. Konton med produktionsrättigheter bör vara avgränsade, byggmiljöer behöver hanteras som en säkerhetskritisk del av infrastrukturen och artefakter ska gå att härleda till granskad kod och avtalade byggsteg. Programvarans ursprung – *proveniens* – kan dokumenteras så att man kan granska var, när och hur en artefakt skapades. En sådan uppgift är dock inte tillräcklig i sig: proveniensens tillförlitlighet beror också på hur byggmiljön skyddas och hur uppgifterna verifieras. SLSA erbjuder ett stegvis referensramverk för detta, inte ett generellt krav att varje lösning måste nå en viss nivå. Reproducerbarhet, proveniens och verifierad integritet är tre besläktade men olika egenskaper.

### Leveransansvar och vanliga fallgropar

Applikationsteamet ansvarar normalt för kodens funktion, tester, kända beroenden och risker med en ändring. Plattformsteamet kan tillhandahålla versionshantering, gemensamma byggtjänster och artefaktregister. Säkerhetsfunktionen formulerar principer och godtagbara undantag, men behöver inte manuellt genomföra varje kontroll. Ansvar för körning, övervakning och återställning måste vara samordnat med leveransansvaret.

En vanlig fallgrop är **lokal optimering**: varje team mäts på hur ofta det levererar, men ingen följer om verksamhetsflödet som helhet fungerar. En annan är alltför centraliserad förändringshantering, där varje låg-riskändring väntar på samma forum som komplexa högriskreleaser. En tredje är att automatisering byggs ovanpå osäkra eller oklara rutiner, så att brister kan upprepas snabbare. Ytterligare ett problem är att alla tester körs i samma långsamma steg: teamen kringgår då kontrollerna eller skjuter upp integrationen.

### Indikatorer på att förmågan fungerar

En granskare ska för en utvald produktionsversion kunna följa kedjan från ändringsförslag och kodgranskning till genomförda tester, byggartefakt, godkännande och driftsättning. En ny medarbetare ska kunna utföra ett dokumenterat bygge med avtalade verktyg utan hemliga manuella steg. Detta är inte samma sak som ett *bit-för-bit reproducerbart bygge*: ett sådant ger exakt samma utdata från samma definierade indata och kräver särskild kontroll av exempelvis tidsstämplar och beroenden. En avsiktlig inkompatibel kontraktsändring bör upptäckas före produktionssättning. För ett representativt fel ska teamet kunna visa vem som beslutar om stopp eller återgång och vilka databegränsningar som gäller.

Följ upp ledtid från kodändring till produktion, leveransfrekvens, andel förändringar som kräver omedelbar rättning och tid att återställa tjänsten efter en misslyckad förändring. Komplettera med väntetider vid godkännanden, kontraktsfel, omarbete och återkommande orsaker till säkerhetsundantag. Bestäm vad som räknas som en förändring och ett fel och följ samma definition över tid. Måtten är beslutsunderlag, inte tävlingstal med universella gränser. En hög leveransfrekvens är ointressant om den uppnås genom att andra team får mer felsökning och avbrott.

### Indikatorer på olämplig teknik eller plattform

- **Funktion och interoperabilitet.** Byggtjänsten kan inte skapa spårbara eller reproducerbara artefakter och stöder inte de nödvändiga kontrakts- och integrationsproven. Undersök om det är en verklig produktbegränsning eller en brist i hur pipelines är byggda.
- **Säkerhet och livscykel.** Byggmiljöer eller plugins saknar uppdateringsväg; administratörsrättigheter och hemligheter är okontrollerade. Pröva rollseparering, uppdatering och kontrollerad återkallelse av en testcredential i en isolerad miljö.
- **Automation.** En process kan bara genomföras genom en manuell konsol trots upprepade standardfall. Pröva API:er, deklarativa konfigurationer eller kringliggande automation innan tjänsten döms ut.
- **Kostnad och skala.** Varje pipeline duplicerar stora mängder arbete eller köar under långa tider. Mät kötid, byggtid, total kostnad och nyttjande – avgör om orsaken är produktens kapacitet, felvald exekveringsprofil eller bristande arbetsfördelning.
- **Leverantörsberoende.** Det är svårt att exportera pipeline-definitioner, artefakter och körhistorik eller migrera en representativ applikation. Genomför ett begränsat migreringstest, inte enbart en licensjämförelse.

En leveransplattform som saknar en funktion kan ibland kompletteras. Om standarden är för stel, behörigheter otydliga eller tjänsten har otillgängligt supportansvar är det i första hand ett design- och organisationsproblem. En äldre teknik är inte automatiskt olämplig.

### Två förbättringsspår i generation 2

**Spår A – gör den distribuerade leveransen tillförlitlig.** Säkerställ versionshantering, automatiserade grundtester, kontrollerad artefakthantering, säker åtkomst, test av tjänstekontrakt samt tydliga beslut om release och återgång. Städa bort personberoende steg och felaktiga produktionsrättigheter. Detta ska göras även om organisationen behåller sina nuvarande utvecklingsverktyg.

**Spår B – förbered plattformsorienterad leverans.** Identifiera återkommande mönster: nya backendtjänster, standardiserade pipelines, infrastrukturbeställningar, säkerhetskontroller och artefaktpublicering. Om flera team har liknande behov kan dessa bli gemensamma versionerade tjänsteerbjudanden. Börja med ett mindre antal vanligt förekommande arbetssätt; behåll en tydlig undantagsväg för särskilda risker och tekniker.

De två spåren kan genomföras parallellt. Men en gemensam portal som tillåter självbetjäning av osäkra byggkedjor innebär inte att grundproblemen är lösta.

## Övergången från generation 2 till 3

Det är dags att överväga en plattformsorienterad modell när organisationen löser samma leveransproblem på nytt i många team. Den viktiga skillnaden är mellan en samling centralt installerade verktyg och **ett förvaltat erbjudande som utvecklingsteam faktiskt kan använda med liten väntan**.

### Förändringsindikatorer

När nya team bygger egna pipelines från grunden, kopierar osäkra mallar, väntar på repetitiva rättighetsbeställningar och får varierande utfall från samma sorts kontroller finns det ekonomiska och säkerhetsmässiga skäl att standardisera. Andra signaler är att centrala specialister fungerar som obligatoriska mellanhänder för varje release, att uppgraderingar av byggverktyg sker mycket olika och att incidenter beror på kända och redan lösta konfigurationsfel.

Mät hur många normalfall som återkommer, hur mycket tid de tar, var köer uppstår och hur stor den realistiska nyttan av ett gemensamt erbjudande är. Några enstaka komplexa undantag motiverar inte automatiskt en fullskalig utvecklarplattform.

### Vad som behöver förändras

Standardiserade utvecklingsgrunder – ibland kallade *paved roads* eller rekommenderade vägar – kan förena källkodshantering, pipeline, tester, paketregister, säkerhetskontroller och driftsättning med en avtalad körmiljö. Infrastructure as Code (IaC) innebär att tekniska resurser beskrivs som versionshanterad kod. GitOps använder versionshanterat deklarerat tillstånd som grund för att synkronisera system med önskat läge. Ingendera tekniken ersätter behovet av beslut om vem som får ändra vad och hur fel rättas.

Plattformsteamet behöver ta produktansvar för mallar, gränssnitt, support, säkerhet, versionering och avveckling. Teamen som använder plattformen behöver fortfarande kunna göra självständiga ändringar inom tydliga ramar. Plattformens kvalitet mäts inte i antal installerade verktyg utan i minskad kognitiv belastning, förutsägbara ledtider, säkerhet och faktisk användning.

### Beredskapsindikatorer

Organisationen bör ha identifierat en kärna av återkommande behov, ha medarbetare som kan utveckla och driva automatiserade tjänster, ha gemensamma säkerhetsprinciper och ha bestämt vem som äger tjänstens livscykel. Det bör finnas möjlighet att följa upp användning och kostnader och att förvalta även uppgraderingar och undantag. Om dessa förutsättningar saknas kan en begränsad automation av två eller tre standardflöden vara ett bättre första steg än ett stort plattformsprogram.

## Generation 3 – utvecklingsplattformen som intern produkt

### Behov, stöd och ansvar

När många team regelbundet utvecklar nya tjänster behöver en gemensam utvecklings- och leveransplattform erbjuda säker, begriplig självbetjäning. Ett team ska kunna starta en ny tjänst från en dokumenterad utvecklingsgrund, få relevanta tester och kontroller, publicera versionsbestämda artefakter och leverera till en lämplig körmiljö utan specialbeställningar för varje steg. Standarder ska följa med både vid skapande och vid senare förändring.

Självbetjäning betyder dock inte fri rätt att driftsätta vad som helst. Produktionsbehörigheter, riskbaserade godkännanden, revisionsspår och miljögränser ska vara inbyggda. Plattformsteamet äger gemensamma bygg- och leveransvägar och ansvarar för att de kan vidareutvecklas. Utvecklingsteamet äger applikationen och dess tester, medan säkerhets- och verksamhetsansvariga beslutar om principer och riskacceptans. En utvecklarportal kan göra tjänsterna lättare att hitta men ersätter inte automatisering bakom gränssnittet.

### Vanliga fallgropar och indikatorer

En plattform kan bli en ny flaskhals om varje undantag eller uppgradering måste godkännas centralt. En annan fallgrop är att mallarna endast används vid projektstart men sedan lämnas utan stöd för säker versionsuppdatering. Ett tredje problem är att plattformsteamet räknar skapade projekt i stället för att förstå om användarna faktiskt kan leverera säkert. Alltför stark standardisering kan också göra legitima specialbehov onödigt svåra.

En fungerande plattform kan demonstrera att en ny standardtjänst startas, testas och levereras utan manuell handpåläggning i normalfallet; att en uppgradering av utvecklingsgrunden kan spridas kontrollerat; att ett policybrott stoppas eller kräver ett dokumenterat undantag; och att samma tjänst kan avvecklas med spårbarhet för tillhörande resurser. Tjänsten ska kunna användas också av team som inte byggde plattformen.

Det bör också gå att visa hur plattformen hanterar ett *ovanligt men legitimt fall*: vem beslutar om undantaget, hur länge gäller det, hur uppdateras det och vad händer om undantagslösningen inte längre får säkerhetsstöd? En standardväg som bara fungerar vid nyprojektstart är inte en fullgod förvaltad produkt. Följ därför både andelen team som frivilligt väljer den, hur mycket manuell hjälp de behöver och om säkerhets- och leveranskvaliteten faktiskt förbättras.

**Tecken på olämpliga teknik- och plattformsval** är att produkten saknar användbara gränssnitt eller exportmöjlighet, att leveransvägarna inte kan uppdateras utan omfattande handpåläggning, att policykontroller bara finns som externa checklistor eller att kostnaden för varje nytt team stiger kraftigt. Pröva först konfiguration, automatisering och produktorganisation. Ett verktygsbyte kan vara motiverat när väsentliga tekniska hinder kvarstår efter rimliga ändringar och den förväntade nyttan överstiger migrationsrisken.

## Övergången från generation 3 till 4

När AI-assisterad kodproduktion och verksamhetsnära utveckling blir vanligare kan antalet förändringar och möjliga utvecklare öka snabbare än organisationens granskningskapacitet. Då blir det viktigare att kod, applikationskonfiguration och AI-beteenden omfattas av **maskinellt verifierbara kontrakt och riskstyrda leveransvägar**. DORA:s forskning från 2025 beskriver AI som en förstärkare av organisationens redan existerande styrkor och svagheter – inte som en ersättning för väl fungerande leveranssystem.

**Förändringsindikatorer** kan vara att AI-genererade ändringar ökar kraftigt men väntar på samma manuella granskare, att okända små applikationer dyker upp utanför godkända leveransvägar eller att agenternas rättigheter och leveransbeslut inte går att följa. **Beredskapsindikatorer** är bland annat fungerande test- och säkerhetsgrindar, tjänsteidentiteter, automatisk registrering av nya lösningar samt regler för vilka åtgärder en agent får utföra. Det behöver gå att kräva mänskligt beslut när risk eller irreversibilitet motiverar det.

## Generation 4 – fler kan skapa, men ansvaret består

I ett framväxande scenario kan utveckling ske närmare verksamheten och med stöd av AI-agenter. Den relevanta förmågan blir då att erbjuda godkända, proportionerliga leveransvägar även för lösningar som inte skapats av traditionella utvecklingsteam. Enkel intern automatisering kan få en snabbare väg, medan applikationer som behandlar känslig information eller fattar betydelsefulla beslut kräver starkare tester, godkännanden och förvaltning.

En *AI-applikationsutvecklingsgrund* kan ge återanvändbara mönster för modellåtkomst, prompt- och kontexthantering, verktygsanrop, spårbarhet och utvärdering. Det är viktigt att hålla isär AI som hjälper till att skriva vanlig programkod och AI som själv ingår i en applikations körning: det senare kräver också beteendetester, inte enbart traditionella kodtester. Modellutvärdering och AI-regressionstest kontrollerar om beteendet försämras mellan versioner, även när resultat inte alltid är deterministiska. Dessa tekniska tjänster är relevanta när organisationen faktiskt utvecklar sådana lösningar; det är ingen universell skyldighet att investera i en avancerad AI-plattform.

**Fallgropar** är att AI-genererad kod behandlas som automatiskt kvalitetssäkrad, att agenter får breda produktionsrättigheter eller att verksamhetslösningar saknar ägare och avvecklingsplan. Ett godtagbart stöd innebär att en lösnings ägare, tillåtna handlingar, testresultat, ändringshistorik och avvecklingsväg går att fastställa. Kritiska eller svåråterkalleliga åtgärder behöver proportionerliga kontrollpunkter. Ett teknikval bör omprövas om det inte går att skilja mänskliga från agentinitierade åtgärder, begränsa verktygsmandat eller granska versionsändringar med proportionerliga skydd – och bristerna inte kan lösas genom rimlig integration eller förändrat arbetssätt. Loggar räcker inte om det saknas möjlighet att begränsa farliga åtgärder innan de utförs.

### Indikatorer för generation 4 – tillräckligt stöd och olämpliga teknikval

En verksamhetsutvecklad lösning bör kunna registreras med ägare, informationsklassning, användningsområde, version och avvecklingsplan utan att någon behöver uppfinna ett nytt granskningsförfarande. Vid ändringar ska det gå att välja kontroller som är proportionerliga mot risken: grundläggande kod- och konfigurationstest för en låg-risklösning och mer omfattande utvärdering, behörighetsprövning och mänsklig attest när lösningen påverkar betydelsefulla beslut eller kan vidta svåråterkalleliga handlingar.

**Indikatorer på fungerande stöd:** en granskare kan hitta den ansvariga ägaren; upptäcka vilka verktyg och datakällor en agent får använda; jämföra testutfall mellan versioner; återkalla rättigheter; och avveckla lösningen utan att lämna kvar onödig åtkomst. **Teknikvarningar:** modell- eller agentverktyget döljer användningen av externa tjänster, saknar begränsning av verktygsanrop eller gör det omöjligt att dokumentera förändringar i prompt, modell och kontext. Undersök först arkitektur, tjänstekontrakt och kompletterande kontroller innan ett produktbyte rekommenderas.

En observation av förbättrad kodproduktivitet är i sig inte ett tecken på att organisationen är redo för generation 4. Behovet av denna leveransform beror på att verksamheten faktiskt ska skapa och förvalta egna lösningar, inom beslutade ansvars- och riskgränser.

## Ett sammanhängande exempel: ett ärendehanteringsstöd förändras

Ett ärendehanteringssystem har delats upp i ett webbgränssnitt, ett handläggnings-API och en separat tjänst för dokumentgenerering. De tre teamen har egna pipelines. Ändå går releaser ofta fel: dokumenttjänstens kontrakt ändras utan förvarning, testmiljön innehåller andra beroenden än produktion och den som ska bedöma risken ser bara en lista över färdiga komponenter.

**Första åtgärden i generation 2** är inte att köpa en ny leveransplattform. Teamen inför versionerade kontrakt, automatiserade integrationsprov, gemensamma minimikrav för artefakter och en tydlig rutin för vilka kombinationer som får driftsättas. De dokumenterar också ansvaret vid fel och hur datamigreringar hanteras. När detta fungerar kan teamen fortfarande använda olika byggverktyg om behovet motiverar det.

**Nästa steg mot generation 3** blir relevant om många liknande tjänster tillkommer. Då kan organisationen publicera en standardväg för backendtjänster som innehåller etablerade tester, säkerhetskontroller, artefaktpublicering och driftsättning. Plattformsteamet förvaltar erbjudandet och tar ansvar för uppgraderingar; de tre applikationsteamen ansvarar för sina kontrakt och sin kod.

**I ett möjligt generation 4-scenario** kan verksamheten skapa en assistent som sammanfattar ärenden. Den nya lösningen ska dock inte kunna ta sig förbi leveranskraven. AI-beteendet behöver granskas med representativa testfall, datatillgång och verktygsrättigheter begränsas, och en person eller funktion behöver vara ansvarig för när lösningen får användas. En godkänd kodbyggprocess räcker inte för att garantera ett godtagbart AI-beteende.

## Beslutsstöd: vilken förändring behövs egentligen?

| Observerad signal | Trolig huvudfråga | Första lämpliga undersökning |
|---|---|---|
| Releaser fallerar vid tjänstegränser | Ofullbordat G1→G2-arv | Testa kontrakt och samordnad versionshantering |
| Många team skapar nästan likadana pipelines | Drivkraft G2→G3 | Mät återkommande arbete och självbetjäningspotential |
| CI/CD-verktyg stöder inte spårbara artefakter | Möjlig produktbegränsning | Pröva uppgradering, integrering och alternativ |
| Gemensamma mallar används inte | Produkt-/användbarhetsproblem | Följ upp teamens hinder och ändra tjänsteerbjudandet |
| AI-kod införs utan spårbara tester | Risk vid G3→G4 | Förstärk kvalitetsgrindar och ansvar innan fler får leverera |

Åtgärder behöver inte alltid vara stora: **behåll** när lösningen fungerar, **komplettera** när gränssnitt eller kontroller saknas, **ändra användning och ansvar** när plattformens leveransmodell brister, och **ersätt** när väsentliga begränsningar inte rimligen kan lösas. Pröva åtgärden med ett faktiskt leveransflöde och följ konsekvenserna för både ledtid, kvalitet och säkerhet.

## Plattformstjänster i förmågan

I den konceptuella modellen stöds CAP-IT-10 av tio plattformstjänster. Nio hör till utvecklings- och leveransplattformen (PLT-009), och modellutvärdering/AI-regressionstest hör till AI- och ML-plattformen (PLT-004):

| Tjänst | När den främst behövs |
|---|---|
| PLS-039 Source Code Management | När tekniska ändringar behöver versionshanteras och granskas |
| PLS-040 CI/CD Pipeline | När bygg, test och leverans ska kunna upprepas och följas upp |
| PLS-041 Artefakt- och paketregister | När godkända versionsbestämda paket behöver lagras och distribueras |
| PLS-042 IaC och GitOps-leverans | När miljö- och leveransändringar behöver styras deklarativt |
| PLS-092 Backend- och tjänsteutvecklingsgrund | När många team utvecklar likartade backendtjänster |
| PLS-093 Mobil applikationsutvecklingsgrund | När organisationen utvecklar egna mobilappar, med signerade byggen och styrd distribution |
| PLS-086 Programvarusäkerhetsanalys | När kod, beroenden, artefakter och IaC behöver automatiskt granskas |
| PLS-094 AI-assisterad programvaruutveckling | När kodskapande med AI behöver tillhandahållas och styras |
| PLS-095 AI-applikationsutvecklingsgrund | När organisationen bygger egna generativa AI-/agentapplikationer |
| PLS-019 Modellutvärdering och AI-regressionstest | När AI-modellers och agenters beteende behöver kvalitetssäkras över tid |

En tjänst är inte obligatorisk bara för att den finns i modellen. **Webbutvecklingsgrund (PLS-002)** stödjer formellt CAP-IT-01, och **tekniska säkerhetsguardrails (PLS-053)** stödjer CAP-IT-12; de är nära beroenden men inte ytterligare CAP-IT-10-tjänster. Detsamma gäller modellåtkomst via PLS-017, som hör till CAP-IT-05.

## Konkreta prov för en organisation

1. **Spårbarhet:** Välj en produktionsversion och återskapa sambandet till källkod, granskning, tester och byggartefakt. Notera luckor.
2. **Kontraktsändring:** Introducera en oförenlig gränssnittsändring i testmiljö. Bedöm om rätt team upptäcker den innan release.
3. **Säkerhetskontroll:** Använd en syntetisk testhemlighet eller godkänd testindikator i en isolerad testmiljö och verifiera att rätt kontroll stoppar eller lyfter den för åtgärd enligt policy. Använd aldrig riktiga credentials som testdata.
4. **Självbetjäning:** Låt ett team som inte utvecklat plattformen skapa, uppdatera och avveckla en standardtjänst. Mät mänsklig handpåläggning och väntetid.
5. **Mobil distribution (om relevant):** Verifiera hur en felaktig mobilversion begränsas och hur en korrigerad version kan distribueras. En publicerad appversion kan normalt inte förutsättas kunna återkallas omedelbart från alla enheter.
6. **AI-kvalitet:** För en AI-lösning, kör representativa evalfall före och efter ändring, inklusive otillåtna verktygsanrop och informationsåtkomst. Notera vem som beslutar om driftsättning.

Proven bör anpassas till vilken typ av IT-stöd som undersöks. De är inte en certifiering eller en generell uppmaning att införa alla tio tjänster.

## Källor och läsanvisning

**Grundmaterial:** *Från systemdrift till digital självständighet*, särskilt kapitel 2, 5–6 och 8–11; *Förmågeöversikt – tekniska IT-förmågor*, CAP-IT-10; *Plattformsöversikt – konceptuella plattformar*, PLT-009 och PLT-004. Generationsprofilerna är synteser och arkitekturbedömningar, inte direkta påbud i modellen.

**Fördjupande referenser:** [NIST Secure Software Development Framework (SP 800-218)](https://csrc.nist.gov/pubs/sp/800/218/final) om säker utvecklingslivscykel (en reviderad version finns som utkast); [SLSA version 1.2](https://slsa.dev/spec/v1.2/) om skydd och proveniens i byggkedjor; [DORA:s forskning 2025](https://dora.dev/research/2025/dora-report/) om AI-assisterad programvaruutveckling; [OpenSSF Scorecard](https://openssf.org/projects/scorecard/) om indikatorer på risker i programvaruprojekt. Dessa källor är stöd för avgränsade principer, inte belägg för att fyra generationer skulle vara en universell standard.
