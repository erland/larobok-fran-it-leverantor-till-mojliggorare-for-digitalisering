# Applikationsexekvering och körmiljö

*CAP-IT-08 · Faktaboksunderlag · version 2.0 · 7 november 2026*

Ett utvecklingsteam har delat upp en tidigare sammanhållen applikation i ett antal tjänster. Ändå behöver varje ny tjänst en beställd server, en särskilt konfigurerad körmiljö, nätverksregler och upprepade möten om driftsättning. Några tjänster körs i virtuella maskiner, andra i containrar och ett äldre delsystem på en applikationsserver. Problemet är inte nödvändigtvis att någon av teknikerna är fel. Det är att miljön fortfarande behandlas som ett antal individuella installationer när organisationen behöver hantera många tjänster med olika livscykler.

Detta kapitel utgår från en sådan organisation: arkitekturen har redan förändrats mot **generation 2**, medan teknik, ansvar och leveransformer inte alltid har följt med. Kapitlet förklarar hur man bedömer vilket körmiljöstöd som behövs, vilka brister som bör åtgärdas redan i generation 2 och när en mer plattformsorienterad modell kan löna sig.

## Vad förmågan handlar om

**Applikationsexekvering och körmiljö** är förmågan att köra applikationer, tjänster, schemalagda jobb och andra arbetslaster under definierade tekniska och operativa villkor. En *arbetslast* (engelska *workload*) är det program eller jobb som faktiskt förbrukar beräkningsresurser. Körmiljön ger bland annat resurser, isolering, konfiguration och stöd för att starta, stoppa eller ändra en arbetslast. Behov av skalning och versionsbyten varierar; själva applikationens konstruktion avgör vad som går att göra utan avbrott.

Körmiljön kan bestå av virtuella maskiner, applikationsservermiljöer, containrar, en tjänst för batchkörning eller specialiserad beräkning med exempelvis grafikprocessorer (GPU). En organisation behöver inte alla alternativen. De ska väljas utifrån det som faktiskt ska köras, applikationernas tekniska beroenden, säkerhetskrav, kostnader och kompetens.

Förmågan ska inte förväxlas med **utveckling och teknisk leverans** (CAP-IT-10), som omfattar bygg, test och release, eller **driftbarhet och motståndskraft** (CAP-IT-09), som omfattar övervakning, incidentdetektion och återställning. Dessa måste fungera tillsammans, men ansvaren är inte identiska. Den tekniska säkerhetstjänsten *workloadskydd* hör primärt hemma i CAP-IT-12 och stödjer även denna förmåga. En välfungerande körmiljö kan inte ersätta dåligt konstruerad applikationslogik, och en container är inte i sig en garanti för säkerhet eller robusthet.

## Avgör först hur relevant förmågan är

Förmågan är relevant för varje organisation som kör egna applikationer eller arbetslaster. **Omfattningen** är däremot beroende av variationen och antalet system. En organisation som främst konsumerar färdiga molntjänster behöver färre egna körmiljöer än en organisation som utvecklar och driftar många verksamhetskritiska tjänster. En enda välförvaltad virtuell maskin kan vara fullt tillräcklig för ett stabilt specialsystem. En större organisation med hundratals självständigt levererade tjänster får andra behov av standardisering och automatisering.

Ställ därför frågor om hur många skilda arbetslaster som finns, hur ofta de förändras, hur olika deras krav är och vilka avbrott eller säkerhetsproblem som kan få allvarliga konsekvenser. Undersök också om flera team efterfrågar samma tekniska grund med små variationer. Det är inte antalet servrar ensamt som avgör om en gemensam plattform behövs, utan mängden återkommande arbete, riskerna med variation och värdet av en konsekvent leverans. Även köpta plattformstjänster och externa leverantörer behöver tydliga tjänstekontrakt, men behöver inte innebära att organisationen driver egen infrastruktur.

## Tillbakablick: generation 1 och vägen till mindre tjänster

När ett IT-stöd bestod av en större sammanhållen applikation var det naturligt att beställa en servermiljö, en applikationsserver och en databas som ett paket. Driftgruppen tog ansvar för den tekniska miljön och utvecklingsteamet för sin applikation. Versionsbyten var relativt få och planerade. En standardiserad server eller en beprövad applikationsserver kunde ge hög stabilitet under lång tid.

När applikationer delades upp i mindre tjänster ökade antalet versioner, installationer, beroenden och möjliga felkombinationer. Varje tjänst behövde kanske inte en egen server, men krävde en tydlig plats att köra på, definierade resursgränser och förutsägbara sätt att driftsättas. **Själva uppdelningen i mindre tjänster löste inte automatiskt detta.**

### Kvarvarande arv från övergången 1→2

Typiska igenkänningstecken är att varje tjänst fortfarande måste få en specialbeställd miljö; att samma operativsystem, Java-runtime eller konfiguration installeras lite olika mellan team; att test och produktion inte är jämförbara; och att ingen tydligt ansvarar för uppgraderingar av mellanliggande programvara. Även applikationsservrar som tidigare var en effektiv gemensam lösning kan nu bli flaskhalsar när många mindre tjänster måste uppgraderas eller driftsättas oberoende av varandra.

Det betyder inte att virtuella maskiner eller applikationsservrar är föråldrade. Det visar snarare att organisationens arbetssätt och driftprofiler behöver utvärderas mot en förändrad applikationsstruktur. Redan inom generation 2 går det att skapa repeterbara basbilder, definiera ägarskap och automatisera de vanligaste installationerna.

### När den äldre tekniken är olämplig

Ett faktiskt teknikproblem uppstår när en vald runtime saknar nödvändigt leverantörsstöd, inte längre kan uppdateras säkert, omöjliggör oberoende versionsbyten eller har orimliga kostnader för den arbetslast den kör. Ett annat exempel är att flera applikationer delar samma runtime på ett sätt som gör att en enda komponentuppgradering riskerar att slå ut dem alla. Däremot är långa beställningstider, inkonsekventa mallar och oklara ansvar ofta **implementations- eller organisationsproblem** som kan lösas utan produktbyte.

## Generation 2 – distribuerade tjänster, men inte alltid distribuerat ansvar

### När förmågan är relevant

När systemet delas upp i självständiga tjänster blir körmiljön ett direkt villkor för hur snabbt och säkert teamen kan förändra sina delar. Förmågan behövs särskilt när många applikationer ska köras på gemensam infrastruktur, när flera runtime-typer måste stödjas eller när snabba förändringar får konsekvenser för tillgänglighet och säkerhet.

Här är det lätt att blanda ihop applikationsarkitektur och driftsättningsmodell. En uppdelning i små tjänster kräver inte Kubernetes. Containrar kan göra paketering och resurshantering mer konsekvent, men tjänster kan också köras säkert på virtuella maskiner eller i förvaltade applikationsservrar. Valet bör följa arbetslastens behov, inte en föreställning om att en viss teknik definierar generationen.

### Vilket stöd som behöver finnas

Organisationen behöver **begripliga körmiljöprofiler**. För varje profil bör det framgå vilka versioner som stöds, vilka resursgränser som gäller, hur konfiguration och hemligheter lämnas till applikationen, hur tekniska identiteter används och vem som ansvarar för patchning. Det måste också gå att skilja på tillståndslösa tjänster, arbetslaster som kräver beständig information och jobb som bara behöver köras vid vissa tidpunkter. Beständig lagring och databastjänster tillhandahålls genom närliggande förmågor, men körmiljön behöver kunna ansluta till dem på ett förutsägbart sätt.

En viktig förändring är **repeterbarhet**. Samma applikationsversion ska kunna köras i motsvarande test- och produktionsprofil med kontrollerade skillnader. Det betyder inte identisk kapacitet, men att versions- och konfigurationsavvikelser ska vara kända. Resursbegränsningar och isolering behöver hindra en tjänst från att utan kontroll förbruka andra tjänsters kapacitet. I en containerplattform behövs exempelvis genomtänkta förfrågningar och gränser för beräkningsresurser samt kontroller av vilka privilegier arbetslaster får. Hur detta realiseras varierar mellan plattformar.

Dessutom måste organisationen kunna genomföra ordnade versionsbyten och återgångar. En körmiljö kan underlätta detta, men det är fortfarande applikationens ansvar att hantera ändringar i datamodeller, aktiva transaktioner och beroenden. Att starta en tidigare containerimage gör inte automatiskt en databasändring ogjord.

### Leverans, ansvar och vanliga fallgropar

Drift- eller plattformsteamet bör ansvara för de gemensamma runtime-profilerna och deras tekniska livscykel. Applikationsteamet ansvarar normalt för den egna kodens beteende, konfiguration inom avtalade gränser och tydliga krav på resurser. Gränsen måste vara uttrycklig, särskilt för operativsystem, applikationsserver, certifikat, patchning och biblioteksberoenden.

En vanlig fallgrop är att införa en containerplattform utan att först reda ut vem som förvaltar applikationernas grundbilder, runtime-versioner och säkerhetsuppdateringar. En annan är att alla arbetslaster pressas in i samma profil trots olika behov av tillstånd, nätverk och livscykel. En tredje är att organisationen samnyttjar så mycket att licens- eller driftkostnaderna blir lägre på pappret, men riskerna för störningar och beroenden mellan team ökar.

### Indikatorer på olämpliga teknik- och plattformsval

- **Funktion och kompatibilitet:** den valda runtime-profilen hindrar nödvändiga uppgraderingar, oberoende leveranser eller användning av stödda applikationsversioner. *Kontrollera först om hindret ligger i produkten, applikationens beroenden eller den valda driftsättningsmodellen.*
- **Säkerhet och livscykel:** operativsystem, applikationsservrar eller containerbasbilder är utanför support och kan inte uppdateras inom verksamhetens toleranser. *Granska beroendekedja och ägarskap innan ett produktbyte beslutas.*
- **Automation och interoperabilitet:** varje ny tjänst kräver unik, manuell konfigurering trots återkommande standardbehov. *Pröva deklarativa mallar och programmerbara gränssnitt innan plattformen döms ut.*
- **Skalbarhet och kostnad:** kapacitetsutnyttjandet är svårt att följa och en enda tjänst kan störa andra, eller licensmodellen gör många små installationer oproportionerligt dyra. *Jämför verklig totalkostnad och isoleringskrav per profil.*
- **Leverantörsberoende:** det saknas rimlig väg för versionering, migrering eller export av applikationspaket och konfiguration. *Pröva en faktisk flytt av en representativ arbetslast.*

Ingen indikator är ensam ett bevis på att ett visst teknikslag måste ersättas. De är signaler för undersökning.

### Två skilda förbättringsspår i generation 2

**Spår A – Få dagens distribuerade miljö att fungera.** Definiera runtime-profiler, ordna patch- och versionsansvar, gör installationer reproducerbara och kontrollera att resursisolering, hemlighetshantering och säkerhetsuppdateringar fungerar. Detta är grundläggande åtgärder som bör göras även om organisationen inte ska införa ett stort självbetjäningsprogram.

**Spår B – Förbered och utveckla generation 3.** Om många team återkommande behöver samma typer av körmiljöer, börja behandla profilerna som gemensamma interna tjänster. Standardisera begäran, skapa tydliga produktägare, automatisera provisionering och inför regler för kvoter, kostnad, livscykel och avveckling. Börja med ett par frekventa fall snarare än en katalog som påstår sig täcka allt.

Det går att arbeta i båda spåren samtidigt. Det vore däremot olyckligt att dölja brister i grundläggande patchning eller ägarskap bakom en ny självbetjäningsportal.

### Indikatorer på tillräckligt stöd

Ett team kan ta en definierad applikationsversion och placera den i en stödd körmiljö enligt dokumenterad rutin. Det går att identifiera vem som äger basbild, runtime och applikation samt vilka uppgraderingar som krävs. En reproducerbar installation ger förväntad konfiguration och rimliga resursgränser. Ett avsiktligt resurskrävande test kan köras utan okontrollerad påverkan på andra tjänster. En säkerhetsuppdatering kan föras igenom och verifieras, inklusive hur en misslyckad uppgradering hanteras. För arbetslaster med planerade körningar finns spårbarhet för start, resultat, timeout, fel och omkörning. Omtag får inte orsaka dubbla betalningar, meddelanden eller andra oönskade verksamhetseffekter; det måste hanteras i jobbets logik och dess omgivande system.

Pröva detta med en faktisk tjänst, inte bara genom att fråga om verktygen är installerade.

## Från generation 2 till 3 – när manuella normalfall börjar dominera

Den viktigaste frågan är inte om organisationen ska välja en ny orkestreringsprodukt. Den är om återkommande behov kan levereras säkert och förutsägbart **utan att ett specialistteam behöver utföra varje normalfall**.

### Förändringsindikatorer

Tecken på ett verkligt generationsskifte är återkommande köer för likartade miljöbeställningar, stora konfigurationsskillnader mellan team, lång tid till första körbara miljö och en mängd manuella åtgärder för sådant som redan har en accepterad standard. Om specialister varje vecka gör samma sak för nya tjänster är det ofta bättre att förbättra det gemensamma erbjudandet än att anställa fler som utför samma beställningar.

Detta behöver beläggas med exempelvis volym, ledtid, väntetid, återkommande avvikelser och användarfeedback. Ett fåtal specialfall motiverar inte i sig en fullständig plattform.

### Beredskapsindikatorer

Det bör finnas en rimligt avgränsad mängd standardprofiler, utpekade ägare för plattformen, en säker väg för identitet och hemligheter, återanvändbar automationskod samt finansiering för både utveckling och löpande förvaltning. Det bör också finnas en överenskommen ordning för undantag och ett sätt att mäta om teamen faktiskt blir mer självständiga. Om dessa förutsättningar saknas kan en begränsad pilot eller förbättrade manuella tjänster vara mer ändamålsenliga än en stor plattformssatsning.

## Generation 3 – körmiljön som en användbar intern produkt

### När förmågan är relevant

Den plattformsorienterade modellen är särskilt relevant när många team har liknande exekveringsbehov och det finns en tydlig kostnad i att hantera varje installation separat. Plattformen behöver inte ersätta alla existerande miljöer. Det kan vara helt riktigt att erbjuda både container-, VM- och applikationsserverprofiler med olika livscykelkrav.

### Vilket stöd som behöver finnas

Utvecklingsteam bör kunna välja en godkänd profil och få en miljö genom ett dokumenterat, helst maskinläsbart kontrakt. Som exempel kan ett team deklarera den kapacitet, nätanslutning och tillgänglighetsklass som krävs, varefter plattformen automatiskt tillämpar tillåtna konfigurationsalternativ och kontroller. *Infrastructure as Code* (IaC) innebär att infrastruktur beskrivs i versionerade, körbara definitioner; det kan vara en del av lösningen men ger inte i sig självbetjäning om varje körning ändå kräver en manuell beställning.

Den gemensamma tjänsten behöver också omfatta tiden **efter** första driftsättningen: uppgraderingar, livscykel för runtimes, förändringar av resurser, kapacitet, kostnadssynlighet och avveckling. Ett utvecklingsteam ska veta vad plattformen garanterar och vad teamet självt ansvarar för. Det gäller även uppgraderingsfönster, stödda versioner, avisering om avveckling, kända begränsningar och hur avvikelser behandlas. Säkerhetsregler, identitet och grundläggande övervakningsintegration bör följa med standardprofilen, men realiseras i samverkan med respektive specialiserad förmåga.

### Ansvar och vanliga fallgropar

Plattformsteamet behöver arbeta som förvaltare av en intern produkt: förstå användarnas behov, hålla sina löften om versioner och stöd, ha en plan för förändringar samt följa upp hur tjänsten används. En driftgrupp som fortsätter utföra alla installationssteg manuellt bakom en portal levererar ännu inte verklig självbetjäning. Det är också en fallgrop att överstandardisera: en tung containerplattform kan vara en dålig lösning för ett fåtal stabila VM-beroende program, och en gemensam applikationsserver kan vara olämplig för tjänster som måste kunna levereras helt oberoende.

### Indikatorer på olämpliga teknik- och plattformsval

- **Gränssnitt:** standardfall kräver manuella privilegierade handgrepp eftersom plattformen saknar säkra automatiserbara gränssnitt.
- **Livscykel:** runtime-versioner och basbilder uppgraderas inte utan omfattande avbrott eller samordnade storprojekt.
- **Produktanpassning:** många team gör lokala speciallösningar därför att plattformens profiler inte motsvarar verkliga behov.
- **Ekonomi:** kapacitet, kvoter, support och licenser ger oförutsägbara kostnader utan tydlig kostnadsägare.
- **Portabilitet:** en applikation blir beroende av plattformsspecifika lösningar utan att fördelarna eller migrationskostnaden har bedömts.

Pröva med en verklig rutinbeställning från början till slut, inklusive uppgradering, incidentnära felsökning och avveckling. Dokumentera vad som sker om en begäran faller utanför standardprofilen: kan den avvisas begripligt, tillåtas genom kontrollerat undantag eller kräver den dold specialistkunskap? Om problemet är ett dåligt tjänstekontrakt eller oklart ansvar behöver produkten inte vara fel.

### Indikatorer på tillräckligt stöd

En användare kan upptäcka en stödd körmiljöprofil, förstå dess egenskaper, skapa en resurs och göra en normaländring utan att behöva kontakta rätt specialistperson. Behörigheter, kvoter, livscykel, mätning och ansvar följer med. När en ny runtime-version introduceras finns en tydlig och provad uppgraderingsväg. Plattformsteamet kan visa minskad manuell handläggning och god faktisk användning, inte bara antalet publicerade mallar.

## Från generation 3 till 4 – fler skapar lösningar, men riskerna består

Generation 4 är här ett **framåtblickande scenario** där verksamhetsnära medarbetare, lågkodsmiljöer och AI-assisterad utveckling skapar fler digitala lösningar. Det betyder inte att varje medarbetare ska få skapa egna produktionsmiljöer eller att alla system måste ha AI-komponenter. Ju större handlingsutrymme som erbjuds, desto viktigare blir att körmiljön ger säkra standardvägar och tydliga begränsningar.

### Förändrings- och beredskapsindikatorer

Förändringstrycket ökar när godkända verksamhetslösningar behöver driftsättas i större antal och den vanliga utvecklingsorganisationen inte längre kan handlägga varje lösning individuellt. Beredskap finns först när roller, dataklassning, tillåtna arbetslastprofiler, maskinidentiteter, kostnadsgränser, avveckling och möjlighet att återkalla åtkomst faktiskt fungerar. Om detta saknas bör handlingsutrymmet begränsas till säkra utvecklings- och testmiljöer eller ett mindre antal förvaltningsbara lösningsmönster.

## Generation 4 – riskstyrda körmiljöer för verksamhetsnära lösningar

### När förmågan är relevant

Förmågan blir särskilt viktig när verksamheten får möjlighet att skapa lösningar som måste köras kontinuerligt, kommunicera med andra system eller utföra automatiserade åtgärder. Många enklare assistenter kan däremot konsumeras som färdiga tjänster utan att organisationen driver en egen applikationsruntime för dem.

### Vilket stöd som behöver finnas

Körmiljöerna bör erbjuda ett litet antal tydliga säkerhetsprofiler för exempelvis experiment, intern informationsbearbetning och verksamhetskritiska flöden. En riskklass är inte samma sak som en teknikprofil: två lösningar med samma körteknik kan behöva olika skydd och godkännande. Varje profil bör ha gränser för vilka resurser som får skapas, hur länge de får finnas, vilka identiteter och nätverksanslutningar de får använda och hur ändringar granskas. Automatiska nedstängnings- eller omprövningsdatum kan vara lämpliga för kortlivade experiment. Löpande tjänster behöver i stället tydligt ägarskap och ordnad förvaltning.

AI-baserade arbetslaster kan ibland behöva särskild GPU-kapacitet, men det är **situationsberoende**. En organisation som anropar en externt förvaltad modell behöver ofta ingen egen GPU-runtime alls. Agenters åtkomst till verktyg och data hör till identitets- och säkerhetsförmågor; exekveringsplattformen ska kunna verkställa begränsningar och avsluta arbetslaster, inte ensam avgöra vilka verksamhetshandlingar en agent får utföra.

### Ansvar och vanliga fallgropar

Verksamhetsansvariga måste äga syfte, konsekvens och godkänd användning av lösningen. Plattformsteamet förvaltar tillåtna runtime-profiler och tekniska begränsningar. Ett återkommande misstag vore att överlåta allt ansvar för AI-genererad kod till en central plattform, trots att den inte vet hur verksamhetsprocessen ska fungera. Ett annat vore att tillåta obegränsad provisionering genom agentverktyg, vilket kan skapa både kostnadsrisker och ett stort antal okända arbetslaster.

### Indikatorer på olämpliga teknik- och plattformsval

- **Policy:** runtime-plattformen kan inte skilja mellan experiment och produktionskritiska lösningar.
- **Identitet:** automatiserade arbetslaster tilldelas breda, långlivade rättigheter utan spårbar ägare eller återkallelseväg.
- **Kostnad:** resursförbrukning, särskilt accelererad beräkning, kan inte begränsas eller hänföras till en lösning.
- **Avveckling:** tillfälliga miljöer ligger kvar efter projektets eller medarbetarens avslut.
- **Flexibilitet:** godkända verksamhetslösningar tvingas till avancerade tekniska driftsättningsmodeller som bara specialister förstår.

Detta är scenariobaserade bedömningspunkter, inte ett påstående om att alla organisationer redan behöver en särskild agentplattform.

### Indikatorer på tillräckligt stöd

En godkänd låg-risklösning kan få en lämplig körmiljö utan att användaren behöver förstå underliggande infrastruktur. Ett försök att skapa en arbetslast som bryter mot fastställda resurs- eller behörighetsgränser stoppas automatiskt eller skickas till en förutbestämd granskningsväg. Plattformen kan identifiera ägare, version, resursförbrukning och livslängd. En lösning går att stoppa och dess tekniska åtkomst återkallas. Detta innebär däremot inte att externa verksamhetshandlingar som redan utförts kan ångras genom att stoppa arbetslasten.

## Beslutsstöd: vad behöver åtgärdas?

| Observation | Trolig problemtyp | Första praktiska kontroll |
|---|---|---|
| En ny mikrotjänst kräver en specialbeställd VM | Möjligt generationsarv eller bristande automation | Pröva reproducerbar standardprofil utan produktbyte |
| Säkerhetsuppdatering av runtime saknar ägare | Grundläggande G2-brist | Fördela ansvar och verifiera ett riktigt versionsbyte |
| Många team beställer likartade miljöer manuellt | Drivkraft för G2→G3 | Mät beställningsvolym, ledtid och återkommande standardfall |
| En VM eller applikationsserver kan inte uppgraderas säkert | Möjlig produkt-/kompatibilitetsrisk | Kartlägg stöd, applikationsberoenden och rimliga alternativ |
| En självbetjäningsportal skapar bara ett ärende | Implementations- eller organisationsbrist i G3 | Följ hela kedjan fram till fungerande runtime och avveckling |
| En AI-agent kan skapa obegränsade produktionsresurser | Otillräckliga tekniska skydd i G4-scenariot | Testa mandat, kvoter, spärrar och livslängd |

Fyra rimliga teknikbeslut är **behåll**, **komplettera**, **förändra användning eller ansvar** och **ersätt**. Börja med det minst ingripande alternativ som faktiskt möter kraven. Ersätt när produktens grundbegränsningar, säkerhet, supportläge eller samlade kostnad gör det oförsvarligt att fortsätta. Räkna då även in migreringsrisk, utbildning, specialistkompetens och den driftorganisation som ska förvalta ersättaren.

## Exempel: ett ärendehanteringsstöd med tre olika arbetslaster

Ett ärendehanteringsstöd använder en stabil, äldre Java-applikation som behöver en särskild applikationsserver, ett nyare API som ändras varje vecka och ett nattligt importjobb. Inget säger att alla tre bör flyttas till samma exekveringsteknik. Den äldre applikationen kan vara rimlig att fortsätta köra i en välförvaltad VM eller applikationsserver, så länge versioner, support och uppdateringar fungerar. API:t kan gynnas av en containerprofil med repeterbara driftsättningar. Importjobbet behöver framför allt schemaläggning, spårbarhet, resursspärrar och säker omkörning.

**Först stabiliseras generation 2:** ägarskap för uppdateringar bestäms, varje arbetslast får dokumenterad profil och test av uppgradering respektive omkörning genomförs. **Sedan prövas generation 3:** om många andra team behöver samma API- och jobbprofiler kan just dessa bli självbetjänade erbjudanden. Det äldre delsystemet behöver inte flyttas enbart för att de andra två får en ny leveransmodell. Exemplet är illustrativt, inte en rekommendation om en viss teknikstack.

## Tre frågor före beslut om nästa steg

1. Kan våra befintliga arbetslaster köras säkert, förutsägbart och uppgraderas utan beroende av enstaka personer?
2. Är det samma återkommande arbete som skapar väntetider för många team, eller handlar det om ett fåtal specialfall?
3. Har vi förmåga att **förvalta** en gemensam tjänst som produkt, inklusive säkerhet, uppgraderingar, support, undantag och avveckling?

Om första svaret är nej bör generation 2 stabiliseras. Om första svaret är ja och det andra visar stor återkommande friktion kan en stegvis förflyttning mot generation 3 vara väl motiverad. Om det tredje svaret är nej är en begränsad, mätbar plattformspilot normalt mer ansvarsfull än ett storskaligt införande.

## Vilka plattformstjänster ligger bakom förmågan?

Källmodellens sex tjänster är inte sex obligatoriska installationer. Fem hör till den konceptuella **applikations- och körmiljöplattformen (PLT-007)**, medan workloadskydd tillhandahålls genom **Security Operations- och skyddsplattformen (PLT-011)**:

| Plattformstjänst | När den är relevant |
|---|---|
| **PLS-032 – Virtual Machine Runtime** | Arbetslaster med operativsystemsnära krav, specialberoenden eller behov av särskild isolering. |
| **PLS-091 – Förvaltad applikationsserverruntime** | Program som kräver applikationsserver eller särskild middleware-livscykel. |
| **PLS-031 – Container Application Runtime** | Program som vinner på konsekvent paketering, isolering och ofta mer självständig leverans. |
| **PLS-033 – Batch- och jobbkörning** | Schemalagda, kortlivade eller händelsestyrda arbetslaster, exempelvis importer och beräkningar. |
| **PLS-034 – Specialiserad och accelererad compute-runtime** | Beräkningar som faktiskt behöver GPU eller andra särskilda acceleratorer. |
| **PLS-078 – Workloadskydd** | Riskanpassat tekniskt skydd av virtuella maskiner, containrar och andra exekverande arbetslaster. |

En säker baskörmiljö är viktig för den arbetslast som behöver den, men alla organisationer behöver inte erbjuda alla fem körmiljöprofiler centralt. Workloadskyddets teknik och ambitionsnivå beror på hotbild och risk; ansvaret för övergripande cybersäkerhet ligger inte hos runtime-plattformen ensam.

## Så kan förmågan bedömas i praktiken

Prövningen bör skilja mellan **bevis på fungerande grunddrift**, **bevis på skalfördelar med en gemensam tjänst** och **bevis på att en vald produkt är otillräcklig**. En väntetid kan exempelvis bero på godkännandeflödet, inte på virtualiseringstekniken. Samma sak gäller om ett team behöver hjälp med en uppgradering: det kan saknas avtalat ansvar snarare än rätt funktion i produkten.

Välj tre representativa arbetslaster: en stabil VM- eller middleware-baserad applikation, en ofta förändrad tjänst och ett schemalagt jobb. Pröva hur de skapas, konfigureras, uppdateras, isoleras och avvecklas. Anteckna vilka steg som kräver manuellt specialistarbete, var versioner eller ansvar är oklara och vilka faktiska beroenden som försvårar leveranser. Mät gärna ledtid till körbar miljö, andelen återkommande standardfall, uppgraderingsfrekvens, misslyckade ändringar, resursavvikelser och faktisk supportbelastning. Följ utvecklingen över tid i stället för att sätta generella tröskelvärden. Pröva också ett avsiktligt otillåtet resurs- eller behörighetsval i en kontrollerad testmiljö, samt hur ett misslyckat jobb eller en misslyckad versionsändring hanteras. Då kan organisationen skilja mellan en befintlig teknik som fungerar väl, en teknik som behöver kompletteras och ett återkommande leveransproblem som motiverar en gemensam plattformstjänst.

## Källor och kunskapsgrund

**Primärkällor för definitioner och tjänstekopplingar:** *Förmågeöversikt – tekniska IT-förmågor* (baseline v1.1, CAP-IT-08); *Plattformsöversikt – konceptuella plattformar* (PLT-007, PLT-011 och de sex PLS-tjänsterna); *Från systemdrift till digital självständighet* (generationerna och övergångarnas organisatoriska logik).

**Kompletterande, externa referenser:** [CNCF Platform Engineering Maturity Model](https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/) (plattform som produkt och grad av självbetjäning); [Kubernetes dokumentation](https://kubernetes.io/docs/concepts/workloads/) (arbetslaster och orkestrering); [NIST SP 800-190, Application Container Security Guide](https://csrc.nist.gov/pubs/sp/800/190/final) (risker och skydd vid containeranvändning). NIST-publikationen från 2017 används för bestående principer för containerrisker, inte som belägg för nyaste plattformsegenskaper. CNCF:s mognadsmodell gäller plattformsarbete och är inte identisk med bokens fyra generationer. Referenserna fastställer inte generationsmodellen som extern standard.

**Analytisk avgränsning:** Kritikalitet, indikatorer, åtgärdstrappa och generationsspecifika mål är författarens arkitekturbedömningar. Generation 4 beskrivs som ett scenario, och inget påstående görs om en specifik organisations faktiska mognad.
