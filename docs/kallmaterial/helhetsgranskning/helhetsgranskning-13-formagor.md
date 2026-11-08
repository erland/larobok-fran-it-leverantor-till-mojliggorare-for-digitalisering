# Redaktionell helhetsgranskning av 13 tekniska IT-förmågor

**Datum:** 7 november 2026  
**Status:** Kompletterad granskningsrapport, version 2 – inga kapitel eller YAML-modeller har ändrats  
**Syfte:** Beslutsunderlag inför en samlad bokredigering. Boken ska vara relevant för stora, komplexa och verksamhetskritiska organisationer, utan anknytning till någon namngiven organisation. Den sammanlagda texten ska helst inte bli längre.

## 1. Sammanfattande bedömning

**Rekommendation: Behåll grundmaterialet och de 13 förmågorna, men gör en tydlig strukturell och språklig harmonisering innan någon större innehållsproduktion.** Materialet innehåller redan de viktigaste tekniska nyanserna: teknikbyte är inte ett självändamål; olösta problem från G1→G2 ska inte förväxlas med G2→G3; grundläggande säkerhet, korrekthet och driftbarhet måste fungera redan i G2; specialiserade plattformstjänster är situationsberoende.

Huvudproblemet är **bokhelheten** snarare än enskilda faktabrister. Kapitlen har tillkommit och granskats var för sig. Resultatet är varierande dispositioner och repetitioner av gemensamma resonemang. Det finns samtidigt en möjlighet att bättre visa hur verksamhetskritiska processer, information, beslut, teknisk kontinuitet och organisatoriskt ansvar hänger ihop. Dessa aspekter bör stärkas genom omfördelning, inte generell utbyggnad.

### Faktisk omfattning i de granskade filerna

- **13 kapitel, totalt cirka 46 600 ord** räknat på Markdown-kapiteltexterna. Längd per kapitel: cirka 3 200–4 100 ord (med enstaka något kortare). Word count är en enkel blankstegsberäkning och inkluderar tabeller, källor och tekniska identifierare.
- **112 kapitel–plattformstjänst-kopplingar**, fördelade på **92 unika PLS-identiteter** i de granskade YAML-modellerna. Flera tjänster är avsiktligt delade mellan förmågor; de behöver **ett kanoniskt grunduppdrag** och kapitelvisa vinklar, inte konkurrerande definitioner.
- **Betydande schema- och dispositionsvariation:** YAML-modellerna använder bland annat `plattformstjanster`, `tjanster` respektive `platform_services`; generationsbedömningar har olika fältnamn. CAP-IT-12 har engelska nycklar, andra svenska. Det är inte automatiskt en saklig motsägelse, men en tydlig förvaltnings- och integrationsrisk.
- CAP-IT-09 har version 3, övriga granskade kapitel version 2. Granskningsunderlaget är alltså inte en enda samordnad release.

**Bedömning:** Det behövs en **måttlig till omfattande redaktionell bearbetning av struktur och språk**, men sannolikt **bara begränsade sakliga kompletteringar**. En prioriterad komplettering är att knyta analys och AI tydligare till operativa bedömningar, åtgärder och utfall i CAP-IT-05. Börja inte med att skriva om samtliga kapitel från grunden.

## 2. Prioriterade fynd för hela boken

### P0 – bör avgöras före kapitelredigering

**P0.1: Bokens gemensamma berättelse är utspridd.**  
Fynd: Nästan varje kapitel börjar med generationsarv och förklarar på nytt att återkommande behov kan bli en förvaltad självbetjänad plattformstjänst. Exempel finns tydligt i CAP-IT-08, 09, 10, 12 och 13. Dessutom återkommer två parallella förbättringsspår i flertalet kapitel.  
**Ändring:** Beskriv generationsmodellen och de två förbättringsspåren ordentligt i ett kort gemensamt inledningskapitel. Behåll i varje förmågekapitel en kort *specifik konsekvens*, inte en ny generell förklaring.  
**Avsedd effekt:** Mindre upprepning och skarpare fokus på förmågans unika problem.

**P0.2: Gemensamma PLS-tjänster behöver entydig ägar- och rollbeskrivning.**  
Fynd: 16 PLS-identiteter förekommer i mer än ett kapitel. Exempel: PLS-079 Säker extern system- och myndighetsanslutning i CAP-IT-06/07/12/13; PLS-075 Mobil fältapplikationsgrund och offline-synkronisering i CAP-IT-01/04/06; PLS-019 Modellutvärdering och AI-regressionstest i CAP-IT-05/10; PLS-077 Endpointskydd i CAP-IT-11/12; PLS-078 Workloadskydd i CAP-IT-08/12.  
**Ändring:** Upprätta en liten kanonisk tjänstekatalog för begrepp och hemvist, och låt andra kapitel beskriva *beroende* och *samverkansansvar*. Dubbelt stöd i modellen ska inte tolkas som dubbelt ägarskap eller dubbel produktinstallation.  
**Avsedd effekt:** Färre ansvarsmotsägelser och bättre spårbarhet till YAML.

**P0.3: En gemensam beslutsmodell bör fastställas.**  
Fynd: Samtliga kapitel resonerar om när teknik ska behållas, kompletteras, användas annorlunda eller ersättas, men frågorna, namnen och indikatorernas detaljnivå varierar.  
**Ändring:** Fastställ fyra konsekventa bedömningsfrågor: (1) Fungerar den nödvändiga verksamhetsförmågan? (2) Är problemet ansvar/regler/arkitektur/implementation eller faktisk teknisk begränsning? (3) Är behovet tillräckligt återkommande och likartat för ett gemensamt erbjudande? (4) Vad är rimlig åtgärd: behåll, förbättra/komplettera, ändra ansvar eller byt? Separera *kritisk funktion*, *behov av gemensam tjänst* och *automationsbehov*.  
**Avsedd effekt:** Samma resonemang i alla kapitel utan att upprepa hela beslutsstödet.

**P0.4: Läsarmanus och spårbar teknikmodell behöver separeras.**  
Fynd: Några kapitel innehåller många PLS-rubriker och tekniska verifieringsprov (särskilt CAP-IT-05, 01 och 03), medan andra använder sammanfattande tabeller (CAP-IT-06, 12, 13). Uttryck som ”källmodellen”, ”faktaboksunderlag”, PLS-/PLT-koder och metodkommentarer förekommer i läsartexten.  
**Ändring:** Låt kapitlen fokusera på sammanhållet resonemang, praktiska exempel och få välvalda indikatorer. Behåll full PLS-matris, teknisk evidens, metodnoter och detaljerade verifieringsprov i YAML eller ett tekniskt appendix. Skilj sluttext från internt granskningsmaterial.  
**Avsedd effekt:** Mer lättläst bok utan att spårbarheten går förlorad.

### P1 – hög saklig och pedagogisk nytta

**P1.1: Långvarig förändring med parallella lösningar bör synliggöras.**  
Kapitlen innehåller enskilda stycken om versionssamexistens, processmigration, schemaändring, klientuppgradering och återställning, men saknar en tydlig tvärgående berättelse. För en stor verksamhetskritisk organisation är detta ofta ett viktigare problem än installation av nya plattformar.  
**Ändring:** Använd ett kort återkommande, fiktivt förändringsfall: äldre och ny handläggningslösning lever parallellt under flera år, med externa parter, regeländringar och krav på obruten drift. Fördela konsekvenserna: CAP-IT-02 processinstanser, 03 regelversioner, 04 datamigrering, 06 avtalsversioner, 09 kontinuitet, 10 kontrollerad leverans.  
**Obs:** Detta är en redaktionell/arkitektonisk komplettering, inte en slutsats från kapitelmodellerna om att alla organisationer måste använda en viss migrationsteknik.

**P1.2: Verksamhetsriktighet och spårbarhet bör få större genomslag än tekniknivå.**  
Fynd: Historisk beslutsförklaring är väl behandlad i CAP-IT-03, ärendetillstånd i 02, datakvalitet i 04/05 och teknisk audit trail i 09. Men sambandet mellan dem är underutvecklat. Sökordet ”rättssäker” förekommer mycket sällan i nuvarande kapiteltexter, vilket inte betyder att frågan saknas, utan att perspektivet är fragmenterat.  
**Ändring:** Ett genomgående fall med ett beslut som senare ska förklaras, rättas eller omprövas: identitet och behörighet, underlag, regelversion, utförd aktivitet, tidslinje och tekniskt bevisvärde måste bedömas tillsammans. Använd generiska ord som *korrekt beslut*, *spårbar åtgärd*, *tillämpade regler* och *ansvarig beslutsfunktion*, med rättsliga krav där de faktiskt är relevanta.  
**Obs:** Ingen generell utsaga om att alla sektorer omfattas av samma juridiska regler.

**P1.3: Motståndskraft ska omfatta verksamhetens arbete vid störning.**  
CAP-IT-09 har god teknisk bredd, men verksamhetsmässigt reservförfarande, prioriterad återgång och datakorrekthet efter störning är inte lika samlat.  
**Ändring:** Komplettera ett befintligt driftfall med bortfall av en extern beroendetjänst eller en längre driftstörning. Visa hur verksamheten beslutar vad som får fortsätta, hur åtgärder dokumenteras, och hur information avstäms vid återstart. Koppla mot CAP-IT-02, 04, 06, 11 och 13.  
**Mål:** Byta ut överlappande tekniska förklaringar, inte lägga till ett stort nytt kapitel.

**P1.4: Ansvarsgränser mellan organisation och plattform är bokens bärande tema men inte sammanhållet.**  
Fynd: Enskilda kapitel gör rätt åtskillnad mellan teknikansvar, dataägarskap, processägarskap, beslut, säkerhet och leverans. Helheten saknar ett gemensamt enkelt sätt att förklara vilka beslut som kan delegeras till team och vilka som behöver samordnas.  
**Ändring:** Ett kort gemensamt ramavsnitt och en kompakt ansvarsmatris: verksamhetens resultat/regel/mandat, produktteamens lösning och livscykel, plattformsteamets erbjudande och säkerhets-/arkitekturfunktions krav/uppföljning. Var noga med att ansvar kan organiseras på fler än ett sätt.  
**Mål:** Läsaren ska förstå förflyttningen utan att förutsätta ett specifikt organisationsschema.

**P1.5: Generation 4 bör bli mer en prövbar framtidsbild och mindre en upprepning av ”AI-agenter”.**  
Fynd: Många kapitel säger att verksamhetsnära AI-lösningar behöver begränsade mandat och återkallelse. Detta är viktigt men repetitivt, och riskerar att göra G4 till en alltför homogen AI-arkitektur.  
**Ändring:** Gemensam G4-definition i inledningen: fler kan skapa lösningar, men regler för exekvering, information, kvalitet, ägarskap och avveckling anpassas till risk. I respektive kapitel endast *en specifik teknisk konsekvens* (t.ex. datatillgång i 04, test av AI-resultat i 05, agerande i 02/06, driftsättning i 10). Markera osäkerhet: detta är ett framtidsscenario, inte etablerad standard.  
**Mål:** Kortare och mer nyanserat.

**P1.6: Flytta CAP-IT-05:s tyngdpunkt från analys- och AI-teknik till faktisk operativ nytta.**  
**Fynd i kapitelunderlaget:** CAP-IT-05 behandlar måttdefinitioner, datapipelines, sökning, RAG-utvärdering, modellrisk och behörighetskontroll utförligt. Däremot är sambandet mellan analysens resultat och verksamhetens *prioritering, bedömning, åtgärd och uppföljning* mindre sammanhängande. Den ursprungliga helhetsgranskningen markerade kapitlet som högprioriterat, men uttryckte inte denna brist tillräckligt tydligt.  
**Redaktionell komplettering:** Visa en kort sammanhängande kedja: **källinformation → kvalitetssäkring och analys → riskbaserat urval eller rekommendation → ansvarig verksamhetsbedömning eller godkänd automation → genomförd åtgärd → mätbar återkoppling**. Håll isär att en modell har god statistisk träffsäkerhet, att ett resultat levereras i rätt tid och att åtgärden faktiskt förbättrar verksamhetens utfall. Beskriv även felprioriteringars konsekvenser, falskt positiva och falskt negativa resultat samt hur mänsklig kontroll dimensioneras efter risk.  
**Avgränsning:** Det handlar inte om att alla organisationer arbetar med operativt riskurval eller använder AI. Beskriv detta som ett särskilt relevant *exempel* för större, informationsintensiva och verksamhetskritiska organisationer. Ge aldrig intryck av att analysmodellens poäng ensamt utgör ett formellt beslut.  
**Genomförande utan längdökning:** Ersätt utvalda uppräkningar av de 16 plattformstjänsterna och generella AI-kontroller med ett sammanhängande operativt fall. Fördjupa endast de indikatorer som direkt visar användbarhet, exempelvis tid från signal till möjlig åtgärd, kvalitet i prioriteringen, andel åtgärder som kan följas upp, felkostnad och återföring av verifierade utfall. Övriga tjänstespecifika prov behålls i YAML.  
**Samverkan mellan kapitel:** CAP-IT-04 ansvarar för data, ursprung och tillåten användning; CAP-IT-05 för analysens kvalitet, presentation och uppföljning; CAP-IT-02/03 för process, bedömning och eventuellt formellt beslut; CAP-IT-07/12 för åtkomst och skydd. Undvik att flytta verksamhetens beslutsmandat till analysplattformen.  
**Avsedd effekt:** Läsaren förstår varför analysförmågan är viktig för verksamhetens resultat – inte enbart hur man organiserar en analysplattform. **Prioritet: hög, ingår som explicit acceptanskriterium i CAP-IT-05-piloten.**

### P2 – efter P0 och P1

- Harmoniserad terminologi: ”generation 2”, ”generationsarv”, ”självbetjäning”, ”plattformsprodukt”, ”driftbarhet”, ”verksamhetsförmåga”, ”plattformstjänst”, ”informationsägare”, ”produktägare”, ”mandat”, ”återkallelse”, ”kompensation” och ”rollback”.
- Enhetlig kapitelrubrik och metadata. Dagens kapitel varierar mellan titel med CAP-ID och titel utan CAP-ID, mellan långa och korta underrubriksstrukturer.
- Konsekvent tilltalsform och språk: svenska huvudtermer, engelska tekniktermer vid behov och korta begreppsförklaringar första gången.
- Gemensam källpolicy: officiell normativ källa vs leverantörsexempel vs redaktionell analys; daterade källor och versioner; utkast skiljs från fastställda dokument.
- En slutkontroll för överlapp mellan **tillgänglighet** (CAP-IT-01), **klientmiljö** (11), **återställning och loggning** (09), **säkerhetsdetektion** (12), **identitet/auktorisation** (07) och **nätverkskontroller** (13).

## 3. Konkret granskningsmatris per kapitel

Rekommendationerna gäller **förändringsinriktning**, inte ännu färdiga textändringar. ”Bevara” anger särskilt värdefullt innehåll som inte bör tappas när vi förkortar.

| Kapitel | Bevara och förstärk | Korta / flytta / samordna | Bedömd redaktionell insats |
|---|---|---|---|
| **01 Interaktion och kanaler** | Användarresan över flera kanaler; tillgänglighet på webb/native; offline, delade och förlorade enheter | Flytta generella plattformsförklaringar och långa PLS-beskrivningar; samordna offline med 04/06/11 | Medel |
| **02 Process, workflow och ärenden** | Långlivade ärenden, parallella ändringar, versionssamexistens, lokal processlogik som giltigt alternativ | Minska generell självbetjäningsförklaring; gör processansvar kontra integration tydligt på ett ställe | Medel |
| **03 Regler och beslut** | Historiska beslut, giltighetsdatum, övergångsbestämmelser, förklaring/reproduktion/omprövning | Kortare generell regelmotorargumentation; skilj läsarfall från PLS-008/009-verifiering | Medel |
| **04 Data och lagring** | Informationsägarskap, konsistens, radering/kopior, schemaförändringar och datakällor | Avgränsa mot 05:s analytiska pipeline och 06:s integration; samordna tjänsteöverlapp | Medel–hög |
| **05 Analys, sökning och AI** | Måttdefinitioner, historik, sökbehörighet och RAG-utvärdering; **stärk kedjan från analys till operativ prioritering, bedömning, åtgärd och mätbart utfall**; redovisa följder av felaktiga urval | Ersätt delar av uppräkningen av 16 tjänster och generella AI-kontroller med ett kort sammanhängande verksamhetsfall; låt tekniska prov ligga i YAML | Hög |
| **06 Integration** | Dubbel skrivning, idempotens, felköer, externa avtal, kontroll av verksamhetseffekt | Avgränsa processbeslut till 02 och informationskonsistens till 04; korta generella plattformsstycken | Medel |
| **07 Identitet och tillit** | Token/sessioners återkallelse, teknisk identitet, behörighet kontra mandat | Samordna PLS-079 med 06/12/13; AI-agenter och skydd mot 12 utan dubbel förklaring | Medel |
| **08 Körmiljö** | VM/container/appserver som parallella val; batchens felmönster; livscykel och undantag | Korta återkommande G2→G3-formuleringar; workloadskyddsgräns mot 12 | Låg–medel |
| **09 Driftbarhet och motståndskraft** | SLO, observerbarhet, återställningsprov och skillnad mellan teknisk rollback och kompensation | Stärk verksamhetskontinuitet; korta generiska plattformsproduktavsnitt; tydlig gräns mot 12 | Medel–hög |
| **10 Utveckling och leverans** | Beroende helheter, byggproveniens, mobilrelease, riskstyrd AI-utveckling | Samordna modellutvärdering PLS-019 med 05; minska repetitiv plattformslivscykeltext | Medel |
| **11 Klientplattform** | BYOD, delad/specialiserad enhet, centrala policyfel, faktisk användbarhet | Klargör endpointskydd mot 12 och mobil/offline mot 01; komprimera bred generell G4-diskussion | Låg–medel |
| **12 Cybersäkerhet** | Riskbaserat skydd, ansvar för utförd kontroll, kontrollernas faktiska verkan | Samordna identitet med 07, endpoint/workload med 11/08, nät/API med 13; flytta generella AI-agentprinciper | Medel–hög |
| **13 Nätverk** | Grundsäkerhet före automation, trafikberoenden, ändring och avveckling, service mesh som val | Samordna extern anslutning med 06/07/12; reducera återkommande generisk självbetjäning | Medel |

**Redaktionell slutsats:** Behoven av djupare omskrivning är störst i **CAP-IT-05** (täta tjänstelistor, flera teknikområden och ett behov att koppla analys/AI närmare operativa beslut och åtgärder), i **CAP-IT-09/12** (verksamhetskontinuitet och säkerhetsgränser) samt i korsningarna **02/03/04/06** (sammanhängande verksamhetsförlopp). CAP-IT-08 och 11 kräver sannolikt mindre omfattande ändringar i löptexten.

## 4. Föreslagen bokstruktur

Detta är en pedagogisk **förslagshypotes**, inte en förutsättning för att genomföra språkrevisionen.

1. **Inledning – varför distribuerade IT-stöd förändrar kraven.** Kort om de fyra generationerna, att organisationer kan ha blandade generationer och varför G2 är utgångsläget.
2. **Att bedöma förändringsbehovet.** Kvarvarande G1→G2-brister vs G2→G3-tryck; verksamhetsriktighet; tre grader av behov (funktion/gemensam plattform/automation); fyra åtgärder.
3. **Verksamhetsförlopp och informationsansvar:** CAP-IT-01, 02, 03, 04, 05, 06.
4. **Förtroende, säkerhet och arbetsmiljö:** CAP-IT-07, 11, 12.
5. **Teknisk leverans och robust grund:** CAP-IT-10, 08, 13, 09.
6. **Avslutning – hur förändringen leds över tid.** En sammanfattning av införande, samexistens, investeringar, ansvar och stegvisa förbättringar, inte ett nytt omfattande arkitekturkapitel.

**Alternativ:** Behåll kapitelordning CAP-IT-01 till 13, men använd grupperingen ovan som delar i innehållsförteckningen. Den bästa ordningen bör testas mot ett kort provmanus innan beslut. Att lägga CAP-IT-10 före 08 och CAP-IT-09 sist ger en pedagogisk rörelse från utveckling till exekvering, nätberoenden och verksamhetskontinuitet, men det finns flera rimliga varianter.

## 5. Ett gemensamt fiktivt scenario – med sparsam användning

Föreslagen röd tråd: **En stor organisation tillhandahåller digitala tjänster till interna användare och externa parter. Ett centralt ärendeflöde styrs av regelversioner, behöver uppgifter från flera aktörer och måste fungera även under störningar. Organisationen byter successivt ut delar av en äldre lösning medan verksamheten fortsätter.**

Använd scenariot som korta återknytningar, inte en ny berättelse i varje kapitel:

- **01–03:** användarresa, processstatus och beslut vid regeländring.
- **04–06:** vilken information som är auktoritativ, analyserad och utbytt; i **05** ett kort exempel där analysen leder till prioritering, ansvarig bedömning, åtgärd och uppföljning; i **06** ett felaktigt återförsök eller versionsglapp.
- **07/11/12:** mänsklig/teknisk identitet, enhetsskydd och säkerhet över tjänstegränser.
- **10/08/13/09:** leverans, körmiljö, kommunikation, kontinuitet och återställning.

Använd inte en namngiven myndighet, sektor eller faktisk organisation. Scenariot ska vara neutralt och fiktivt. Undvik att lägga in specifika juridiska skyldigheter som påstås gälla generellt. **Rekommendation:** testa scenariot i två–tre kapitel först; om det känns konstlat ska det inte drivas igenom överallt.

## 6. Ord- och omfattningsbudget

**Nuläge:** cirka 46 600 ord för de 13 kapiteltexterna, inklusive källavsnitt och tekniska listor. Den siffran är inte bokens slutliga tryckta löptext.

**Mål:** högst ungefär samma totala omfattning efter redigering inklusive en kort inledning och avslutning. Detta kräver omfördelning, inte att varje enskilt kapitel blir kortare.

Föreslagen redaktionell *planeringsram* (inte ett löfte om exakt utfall):

| Åtgärd | Ungefärlig effekt |
|---|---:|
| Flytta/reducera repetitiva generations-, plattforms- och beslutsförklaringar | −3 000 till −5 000 ord |
| Flytta detaljförteckningar och tekniska prov från huvudtext till appendix/YAML | −1 000 till −2 500 ord |
| Gemensam inledning, beslutsmodell och avslutning | +1 500 till +2 500 ord |
| Målmedveten fördjupning av tvärgående förändring, beslut/spårbarhet och kontinuitet | +1 000 till +2 500 ord |
| **Förväntad nettoeffekt vid målstyrd redigering** | **oförändrad eller kortare bok** |

Talen ovan är **redaktionella uppskattningar**, inte uppmätt mängd exakt duplicerad text. Efter ett första provkapitel kan planen kalibreras mot faktisk uppmätt besparing.

## 7. Rekommenderad genomförandeordning efter beslut

**Arbetspaket A – gemensam redaktionell kärna.** Fastställ läsarmål, disposition, gemensamma begrepp, källpolicy, beslutsmodell och gräns för hur mycket PLS/PLT som ska synas i löptext. Leverans: kort redaktionell stilguide och kapitelmall. Inga ändringar av sakmodeller.

**Arbetspaket B – pilot på tre kontrasterande kapitel.** Föreslaget urval: CAP-IT-05 (**operativ effekt av analys och AI**, många tjänster), CAP-IT-09 (drift och kontinuitet), CAP-IT-02 (process, regler och långlivade förlopp). För **CAP-IT-05** ska pilotmanuset visa minst ett komplett exempel från källsignal och analys till ansvarig bedömning, åtgärd och återkoppling; indikatorerna ska omfatta såväl analyskvalitet som verksamhetsnytta, tid och risk för felprioritering. Dessa inslag ska huvudsakligen **ersätta** generiska teknikbeskrivningar och inte öka kapitlets längd. Mät ordmängd, begriplighet, konsekvens och förlorat/nytillkommet sakstoff mot ursprung. Leverans: pilotmanus, diff och kvalitetstest; behåll endast fungerande principer.

**Arbetspaket C – resterande tio kapitel.** Redigera i tematiska grupper så att angränsande förmågor granskas tillsammans; uppdatera YAML endast där semantiken ändras eller där en separat schemaharmonisering beslutats. Varje kapitel får konkret före/efter-jämförelse och gränsdragningskontroll.

**Arbetspaket D – bokslut och läsarprov.** Läs som obruten bok, kontrollera att ord och exempel fungerar över kapitelgränser, att referenser och faktapåståenden är spårbara och att inget är beroende av ett separat källdokument. Extern faktagranskning är fortfarande ett särskilt steg före publicering.

**Viktigt vägval:** Jag rekommenderar att *inte* migrera YAML-schemana samtidigt som första pilotkapitlen språkrevideras. Schemaharmoniseringen är en verklig separat uppgift och bör få egen regressionskontroll; annars blir det svårt att skilja redaktionella ändringar från modelländringar.

## 8. Kvalitetskriterier för att godkänna framtida ändringar

En redaktionell ändring ska godkännas bara om:

1. Den löser ett identifierat läsarproblem eller en verklig saklig lucka.
2. Den är spårbar till befintligt underlag eller uttryckligen märkt som författarens kompletterande analys.
3. Den inte förvandlar ett situationsberoende teknikval till ett universellt generationskrav.
4. Den håller isär funktionens kritikalitet, behovet av gemensam tjänst och graden av automation.
5. Den beskriver kontrollansvar vid betrodd teknisk punkt, utan att tillskriva en plattform funktioner den inte kan utföra.
6. Den bibehåller generation 2 som huvudperspektiv och markerar generation 4 som framtidsorienterad.
7. Den inte ökar den totala ordmängden utan motiverad omfördelning.
8. Den kontrolleras mot angränsande kapitel och YAML när slutsatser ändras.
9. För CAP-IT-05: den visar en trovärdig koppling från analysresultat till operativ användning och uppföljt utfall, utan att förväxla modellens prediktion med verksamhetens beslut eller låta textomfånget växa omotiverat.

## 9. Vad granskningen inte omfattar

- Ingen omskrivning av kapiteltexterna har genomförts.
- Ingen förändring av YAML-prioriteringar, identiteter, plattformskopplingar eller tjänstebeskrivningar har genomförts.
- Ingen extern teknisk, juridisk eller sektorspecifik faktagranskning ingår i denna redaktionella genomgång. Tidigare kapitelvisa kritiska granskningar ersätts inte.
- Den föreslagna strukturen och ordmängdsbudgeten är redaktionella bedömningar som behöver provas i pilot.

## 10. Underlag för denna granskning

Samtliga **13 lokalt tillgängliga faktabokskapitel i senast kritiskt granskad version** har lästs och jämförts tillsammans med deras YAML-modeller: CAP-IT-01–08, CAP-IT-10–13 i respektive version 2, samt CAP-IT-09 i version 3. Kapiteltext, rubriker, återkommande formuleringar, PLS-identiteter, tjänsteförekomster och YAML-strukturer har inventerats. Befintliga kapitelvisa granskningar är bakgrund men huvudbedömningen bygger på de faktiska reviderade kapitlen.

**Källtolkning:** Fynden om hur materialet faktiskt ser ut är observerade i dessa filer. Förslag till ny bokstruktur, budget och pedagogiskt scenario är redaktionella rekommendationer, inte direkta påståenden ur källmaterialet.

## 11. Komplettering i version 2 – analys och AI nära operativ verksamhet

Denna komplettering tydliggör ett perspektiv som i version 1 enbart framgick indirekt. Den **ändrar inte** den samlade bedömningen om kapitelstruktur eller behovet av ett begränsat pilotarbete. Den skärper prioriteringen och godkännandekriterierna för **CAP-IT-05**.

**Spårbarhetsstatus:** Att CAP-IT-05 redan innehåller omfattande resonemang om analys- och AI-teknik är en observation i det granskade kapitelmaterialet. Att operativ nytta bör fungera som en röd tråd är en **redaktionell rekommendation**, inspirerad av verksamhetsbehoven i stora informationsintensiva och samhällsviktiga organisationer – inte ett påstående om någon namngiven organisations interna arkitektur eller mognad.

**Prövningsfråga för piloten:** Kan en läsare efter kapitlet förstå när en analysförmåga verkligen hjälper verksamheten att fatta bättre prioriterings- och åtgärdsbeslut, vem som har mandat att agera, vad som händer när analysen blir fel och hur nyttan följs upp? Om svaret är nej behöver kapitlets disponering förbättras även om beskrivningen av plattformstjänsterna är tekniskt korrekt.
