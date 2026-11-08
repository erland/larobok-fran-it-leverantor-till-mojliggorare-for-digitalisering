# Bokplan – Från IT-leverantör till möjliggörare för digitalisering

**Status:** Förslag för godkännande, version 1.0  
**Datum:** 7 november 2026  
**Arbetsform:** Lärobokskaparen, bokprofil `factbook`. Detta är en bokplan – inte ett bokprojekt och inte ett färdigskrivet manus.

## 1. Bokidé och löfte till läsaren

**Arbetstitel:** *Från IT-leverantör till möjliggörare för digitalisering*  
**Föreslagen undertitel:** *Fyra generationer av IT – gemensamma plattformar, digital självständighet och ett nytt ansvar*.

**Bokens kärnpåstående:** När antalet digitala tjänster och beroenden ökar räcker det inte att organisera IT som beställning och leverans av system och infrastruktur. En organisation behöver först förmågan att erbjuda fungerande, förvaltade och säkra gemensamma tjänster (generation 3). Då blir det möjligt att ge många fler i verksamheten faktisk digital handlingskraft – från AI-assistenter och automatisering till egna applikationer med AI-stödd utveckling (generation 4). IT upphör inte att behövas: uppdraget förskjuts mot att **möjliggöra, sätta ramar, förenkla, säkra och bära långsiktig livscykel**.

**Avsedd läsarförflyttning:**
1. *Jag känner igen varför dagens sätt att bedriva IT blir svårt att skala.*
2. *Jag förstår varför standardisering och självbetjäning behöver byggas som interna produkter – inte som ännu fler centrala beställningsköer.*
3. *Jag ser konkret vad det gör möjligt för verksamheten: att själv använda, skapa, förbättra och ibland förvalta digitala lösningar.*
4. *Jag förstår vad som måste förändras i ansvar, arbetssätt och kompetens för att detta ska bli robust och säkert.*

Boken ska **inte** vara en produktjämförelse, en checklista för att införa Kubernetes, en framstegsberättelse där alla system måste bli generation 4, eller en bok om en viss myndighet.

## 2. Profil, målgrupp och läsnivå

| Fält | Beslut/förslag |
|---|---|
| Profil | `factbook` (förklarande, resonerande fackbok; inga obligatoriska övningar eller quiz) |
| Underdtyp (`book_type`) | Fackbok om IT-transformation, organisation och digitalisering |
| Språk | Svenska; tekniska engelska termer förklaras första gången |
| Primär målgrupp | IT-chefer, arkitekter, plattformsansvariga, utvecklings-/driftansvariga, digitaliserings- och verksamhetsledare |
| Sekundär målgrupp | Produktägare, säkerhetsansvariga, förändringsledare och erfarna verksamhetsspecialister |
| Förkunskaper | Allmän förståelse för större organisationers IT och digitala tjänster; läsaren ska inte behöva känna till CAP-IT, PLS eller PLT |
| Ton | Saklig, framåtblickande, lätt att relatera till; teknisk precis när nödvändigt, annars verksamhetsorienterad |
| Berättarform | Argumenterande faktabok med fiktiva korta exempel, inte lärobok/utbildningsmaterial |
| Tidshorisont | G1–G3 beskrivs som observerbara mönster; G4 som möjlig, framväxande riktning med uttrycklig osäkerhet |
| Författare | Fastställs före EPUB/PDF-export; ska inte gissas |
| Omslag | Form och bild beslutas senare, efter godkänd bokplan |
| Inre illustrationer | Föreslås få, ändamålsenliga diagram; inga genereras i detta steg och kräver uttryckligt godkännande |

Boken riktar sig särskilt väl till stora, informationsintensiva, reglerade och verksamhetskritiska organisationer. Det ska märkas i **valet av problem**, till exempel långvarig migrering, spårbara beslut, kritiska informationsflöden och drift vid störning, **inte genom sektors- eller organisationsspecifika hänvisningar**.

## 3. Generationsberättelsen: ojämnt men medvetet fördelat djup

Generationerna är **analytiska idealtyper**, inte fyra obligatoriska nivåer som hela organisationen måste passera samtidigt. En portfölj kan innehålla många generationer parallellt. För varje teknik och verksamhetsprocess är den rimliga lösningen situationsberoende.

| Generation | Funktion i berättelsen | Utrymme i generationskapitlet, riktvärde |
|---|---|---:|
| **G1: sammanhållna IT-stöd och traditionell leverans** | Historisk igenkänning; varför monoliter ibland var relativt enkla att skydda och drifta | ca 10 % |
| **G2: distribuerade tjänster och ökat samordningsbehov** | Läsaren känner igen nulägesfriktion, manuella beställningar, beroenden och kvarvarande generationsarv | ca 20 % |
| **G3: gemensamma plattformar som produkter** | Bokens närmaste, praktiska förflyttning: standardiserade erbjudanden, självbetjäning, inbyggda skydd, automatiserad livscykel, delat ansvar | ca 35 % |
| **G4: verksamhetsdriven digitalisering** | Lika konkret som G3: nya former av skapande, användning, automatisering och fördelat ansvar | ca 35 % |

**G3 konkret:** Visa skillnaden mellan att beställa komponenter och att konsumera en dokumenterad plattformstjänst. Beskriv interna plattformsprodukter, användargränssnitt/API, automatiserade standardfall, säkra grundprofiler, kostnads-/kapacitetsgränser, uppgradering, incidenthantering och avveckling. Plattformen har ett tydligt produktansvar; verksamhets- och produktteam behåller andra ansvar.

**G4 konkret och i tre användningsformer:**

1. **AI-assistenter för medarbetare:** kunskapssökning, analys, utkast, sammanfattning, förklaringar och stöd i arbetsuppgifter. Förutsätter tillåten datatillgång, källkontroll, användningsregler och mänsklig bedömning där så behövs.
2. **AI-agenter och verksamhetsautomation:** avgränsade arbetsflöden med verktygsanrop, integrationer och uppgifter som kan få effekter i andra system. Förutsätter kontrollerad delegering, behörighetsprövning vid betrodda kontrollpunkter, spårbarhet, återkallelse och hantering av redan utförda eller köade handlingar.
3. **Verksamhetsskapade applikationer med AI-stödd utveckling ('vibe programming'):** från prototyper och lokala hjälpmedel till förvaltade verksamhetslösningar där risk och konsekvens medger det. Förutsätter godkända utvecklings-/körmiljöer, kvalitets- och säkerhetskontroller, informationsägarskap, leveransvägar, support och avveckling.

**Riskanpassad tredelning:** (a) personligt hjälpmedel/prototyp; (b) delad team- eller avdelningslösning; (c) verksamhetskritisk eller rättsligt betydelsefull lösning. Kraven på granskning, ansvar, testning och förvaltning ökar med faktisk konsekvens och användning, inte bara med den använda AI-tekniken. Traditionell professionell utveckling fortsätter vara nödvändig för många kärnsystem.

**Huvudskillnad:** G3 skapar skalbara, säkra förutsättningar för professionella team; G4 breddar vilka som kan skapa digitalt värde inom dessa ramar. Dessa kan samexistera och växa stegvis. Undvik att antyda att G4 är fullt realiserad eller att generativ AI garanterar kvalitet.

## 4. Föreslagen bokdisposition – 17 huvudkapitel i tre delar

En kort, separat **Inledning** ingår före huvudkapitlen, men är inte ett av de 19 numrerade kapitlen. Förmågekapitlen grupperas pedagogiskt; CAP-IT-identiteterna bevaras internt och kan anges diskret i referensmaterialet.

### Inledning (cirka 600–900 ord)

*Vad handlar boken om, vem riktar den sig till, vilken förförståelse behövs och hur ska den läsas?* Ett inledande exempel visar en verksamhetsförändring som kräver flera IT-beställningar trots att varje enskild komponent fungerar. Förklara att texten vill förändra perspektivet på IT:s uppdrag, inte bedöma organisationers mognad på en fyrgradig skala.

### Del I – Varför och vart? (tre kapitel)

**1. När IT blir en broms trots fungerande system** (cirka 1 400–1 800 ord)  
Vägen från sammanhållna system till många beroenden; växande antal teknikbeställningar, specialfall, gemensamma kostnader och risk för otydliga säkerhetsgränser. Skilj grundbrister i G2 från behovet att förändra leveransmodellen. Avsluta med *den centrala frågan*: vad måste IT erbjuda för att andra ska kunna förändra snabbare utan att helheten blir mindre robust?

**2. Fyra generationer av IT – två förändringar i synsätt** (cirka 3 200–3 800 ord)  
Kort G1 och G2; fyllig G3 och G4 enligt avsnitt 3. Ett återkommande fiktivt fall visar vad som förändras för **verksamhetsmedarbetaren, utvecklingsteamet och IT/plattformsteamet** i respektive generation. Beskriv gränser, samexistens och att utvecklingsvägen inte är tekniskt förutbestämd. Viktigt: detta kapitel ska vara tillräckligt självständigt för att läsaren redan här ska förstå AI-assistenter, agenter och AI-byggda appar samt IT:s möjliggörarroll.

**3. Vad en gemensam IT-förmåga egentligen är** (cirka 1 400–1 900 ord)  
Skilj **förmåga** (vad organisationen måste kunna), **plattformstjänst** (återanvändbart erbjudande), **plattform** (teknisk/organisatorisk helhet), **produkt/IT-stöd** (värde för användare), samt ansvar och kvalitet. Ge kort översikt av samtliga 13 förmågor och varför en förmåga inte motsvarar en obligatorisk plattform. Presentera *två förbättringsspår*: åtgärda G2-arv och, där upprepning motiverar det, bygg G3-erbjudanden. Introducera de fyra vägvalen: behåll, förbättra/komplettera, ändra användning/ansvar, ersätt. Förklara här gemensamma begrepp som inte ska upprepas i 13 kapitel.

### Del II – Förmågorna som möjliggör förändringen (13 kapitel)

**Block A: Upplevelse, verksamhetsflöde och beslut**

**4. Interaktion, presentation och kanaler (CAP-IT-01)** – En fungerande backend är inte lika med en fungerande användarresa; tillgänglighet, kanaler, kontinuitet och självskapade gränssnitt.

**5. Process, workflow och ärendehantering (CAP-IT-02)** – Långlivade ärenden, tillstånd, ansvar och vad en agent faktiskt får utföra; lokal processlogik kontra gemensam processplattform.

**6. Regler och beslut (CAP-IT-03)** – Regelversioner, beslutsförklaring, mänskliga mandat och AI-rekommendation; skilj regelberäkning från beslut med verksamhetskonsekvens.

**Block B: Information, analys och utbyte**

**7. Datahantering och informationslagring (CAP-IT-04)** – Informationsägarskap, datakopior, konsistens, migrering och säker tillgång till data för verksamhetsnära lösningar.

**8. Analys, sökning och intelligent informationsbearbetning (CAP-IT-05)** – **Operativ värdekedja:** källa → kvalitet/bearbetning → analys/AI → ansvarig prioritering/bedömning → åtgärd → uppföljning. Mät nytta, tid och kostnad för felprioritering; nedprioritera uppräkning av AI-/ML-teknik. Visa hur assisterande och automatiserade former skiljer sig.

**9. Integration och informationsutbyte (CAP-IT-06)** – Externa beroenden, API:er/händelser/filer, kontrakt, fel, dubbletter och integrationer som kontrollerade byggblock för agenter och lokala appar.

**Block C: Tillit, klienter och skydd**

**10. Identitet och tillit (CAP-IT-07)** – Människor, maskiner och agentmandat; teknisk identitet skild från verksamhetens auktorisation.

**11. Slutanvändarmiljö och klientplattform (CAP-IT-11)** – Säkra, användbara klienter, delade och privata enheter, skydd för verksamhetens faktiska arbetssituationer.

**12. Cybersäkerhet och tekniskt skydd (CAP-IT-12)** – Riskbaserad kontroll, tydliga verkställandepunkter och skydd i självbetjänade miljöer, utan att allt ska lösas av en central säkerhetsprodukt.

**Block D: Leverans, körning och motståndskraft**

**13. Utveckling och teknisk leverans (CAP-IT-10)** – Från reproducerbara byggen till säkra paved roads; stödet för både professionella team och AI-stött verksamhetsskapande.

**14. Applikationsexekvering och körmiljö (CAP-IT-08)** – Driftsatta arbetslaster, olika rimliga körmiljöer, livscykel och riskanpassad körning av enklare respektive kritiska appar.

**15. Nätverk och konnektivitet (CAP-IT-13)** – Säkra trafikrelationer, beroenden och nätåtkomst utan manuella flaskhalsar; teknikval ska motiveras.

**16. Driftbarhet och motståndskraft (CAP-IT-09)** – Säker återhämtning, kontinuitet under störning, verksamhetens reservförfaranden och återgång efter avbrott; nya lösningar får inte hamna utanför driftansvaret.

**Kapitelmall för samtliga 13 förmågor** (riktvärde 1 900–2 450 ord per kapitel, sakliga undantag är möjliga):
1. *Varför förmågan spelar roll* – ett konkret verksamhetsproblem, maximal kort begreppsförklaring.
2. *När generation 2 inte riktigt räcker* – vad som måste lösas redan nu och vad som är återkommande skalproblem.
3. *Vad generation 3 förändrar* – lämpliga självbetjänade tjänster, nya ansvarsytor och vad som inte behöver centraliseras.
4. *Vad generation 4 gör möjligt* – minst ett **specifikt** exempel från assistent, agent, automation eller AI-stödd apputveckling, beroende på förmåga; inte samma generella agentvarning i varje kapitel.
5. *Hur man vet vad som behöver förändras* – 2–4 prövbara indikatorer och ett konkret vägval, inte en lång tekniklista.

**G1** får högst någon mening i relevanta förmågekapitel. **G2** är diagnostiken; **G3** och **G4** är huvudfördjupningen. Undvik mekaniska avsnitt av typen ”generation 1, 2, 3 och 4” om den gemensamma inledningen redan har gjort arbetet. Förmågekapitlen ska inte upprepa definitionen av självbetjäning, plattformsprodukt och delegering; de ska visa tillämpningen.

### Del III – IT:s nya roll (ett kapitel)

**17. Från systemleverantör till möjliggörare – ansvar, arbetssätt och kompetens** (cirka 3 200–4 000 ord)  
Ett tydligt **synteskapitel**, inte ytterligare en organisationshandbok. Beskriv förflyttningen för fyra roller: (a) verksamhetsägare och verksamhetsnära skapare, (b) produkt- och utvecklingsteam, (c) plattforms-/driftteam, (d) säkerhet, arkitektur och informationsansvar. Förklara *vem* som beslutar om verksamhetsregler, tillåten information, riskacceptans, tekniska standarder, support, kostnader och avveckling. Redogör för skillnaden mellan att ge behörighet att experimentera och mandat att publicera kritiska lösningar. Beskriv nya kompetenskrav inom produktutveckling av plattformar, utvecklarupplevelse, automation, AI-utvärdering, samarbete och verksamhetsförståelse. Visa hur organisationer kan gå fram stegvis: börja med flaskhalsar och återkommande behov, bygg ett fungerande standarderbjudande, prova med verkliga användare, inför riskanpassad styrning, mät effekten. Bevara plats för professionellt utvecklade kärnsystem och delat ansvar över tid.

**Kapitel 17 avslutas med en kort syntes** om samexistens, investeringar, förändringstakt och fortsatt lärande, utan att skapa ett separat metodkapitel. Bokens disposition omfattar alltså **3 inledande huvudkapitel + 13 förmågekapitel + 1 avslutande kapitel = 17 huvudkapitel**; den obligatoriska, korta inledningen ligger utanför numreringen.

## 5. Bilagor och separat referensmaterial

**Bilaga A: Översikt av de 13 IT-förmågorna** (cirka 700–1 000 ord). En tabell med namn, syfte, huvudansvar och viktigaste beroenden. Inte en upprepning av de 13 kapitlen. CAP-IT-koder kan anges här som referens.

**Bilaga B: Begrepp och förkortningar** (cirka 500–800 ord). Definiera återkommande begrepp, inklusive IT-förmåga, plattform, plattformstjänst, intern produkt, självbetjäning, tillit, riskanpassad publicering, RPO/RTO där det behövs.

**Bilaga C: Källor och vidare läsning** (omfattning efter verifiering). Kort strukturerat referensregister, baserat på faktiskt använda och kontrollerade källor. Ingen intern redaktionslogg i boktexten.

**Utanför den tryckta/bokexporterade texten:** De 13 YAML-modellerna, 92 unika PLS-identifierare, detaljerade generationsmatriser, tekniska prov, källspårbarhet och granskningsprotokoll. De kan följa med bokprojektet som digitalt referensmaterial, men ska inte räknas som bilagor som den vanliga läsaren förväntas läsa. Delade tjänster ska ha ett entydigt grunduppdrag i referensmaterialet.

## 6. Omfattningsbudget och skydd mot repetition

**Utgångspunkt ur senaste helhetsgranskningen:** omkring **46 600 ord** i de 13 granskade Markdown-kapitlen, inklusive listor, tabeller, källor och tekniska identifierare; inte ett färdigt bokmanus. En ren sammanslagning av dessa kapitel med ny inledning och avslutning skulle bli för lång och upprepande.

**Riktvärde för huvudmanus:** cirka **39 000–44 000 ord** inklusive inledning, del I, del II och avslutning, *exklusive* register och källförteckning. Hellre något kortare med bibehållen betydelse än exakt ordmål. Preliminär fördelning:

| Del | Ungefärlig ordmängd | Kommentar |
|---|---:|---|
| Inledning | 600–900 | Kort vägledning och mål |
| Del I: tre kapitel | 6 000–7 500 | G3 och G4 får störst utrymme |
| Del II: 13 förmågor | 25 000–30 000 | Från dagens ca 46 600 källord genom redigering och renodling |
| Del III: syntes och kort avslutning | 3 200–4 000 | Ansvar, arbetssätt och kompetens konkret |
| Bilagor A–B | 1 200–1 800 | Kortfattade uppslag, inte dubbelberättelse |

**Obs:** Delarnas intervall ger totalt cirka 34 800–42 400 ord för inledning och huvuddelar (utan bilagor); summor ska mätas mot verkliga manusversioner. Längd är ett **tak och redaktionell styrparameter**, inte en kvot som måste fyllas. Särskilt för förmågekapitlen ska borttagning av upprepade avsnitt kombineras med bibehållen specifik sakinformation.

**Regler för att inte bli långdragen:**

- Gemensam generationsbeskrivning och allmänna plattformsprinciper finns **en gång** i del I.
- Varje förmågekapitel tillför en **unik konsekvens** för G2, G3 och G4. Undvik standardstycken om AI-agenters mandat eller produktägarskap i samtliga kapitel.
- Teknikexempel (Kubernetes, containrar, meddelandeköer, särskilda AI-tekniker) används **bara när de förklarar ett verkligt vägval**, inte för katalogkänsla.
- Byt ut mindre värdefulla uppräkningar mot en konkret scen eller diagnostiskt prov.
- Inför högst ett centralt exempel per kapitel; fortsätt gärna ett gemensamt fiktivt fall men inte mekaniskt.
- Där samma tjänst stöder flera förmågor anges en tydlig primärförklaring och i andra kapitel enbart relevant beroende.
- Generationsetiketter är inte värdeomdömen; någon teknik eller lösning kan vara lämplig i alla fyra generationer.

## 7. Genomgående fiktivt fall och möjliga illustrationer

**Fiktivt fall: En större organisation hanterar ansökningar och kontroller i samverkan med andra aktörer.** Den har interna användare, externa parter, föränderliga regler, känsliga data och höga krav på tillgänglighet. En äldre lösning behöver leva vidare medan nya tjänster utvecklas. Verksamheten vill därefter införa analysstöd, säkra AI-assistenter, avgränsade agenter och mindre självskapade appar. Beskrivningen är generisk och ska inte förknippas med någon namngiven myndighet.

Fyra prövande scener:

1. **G2-friktion:** En förändring kräver flera manuella teknikbeställningar; ett fel uppstår mellan integration och processstatus.
2. **G3-vinst:** Ett team använder godkända utvecklings-, identitets-, integrations- och driftprofiler via självbetjäning med synlig kostnad, ansvar och livscykel.
3. **G4-assistent/agent:** En användare hittar relevant kunskap, sammanställer underlag och får hjälp med en avgränsad, spårbar arbetsuppgift; beslutskontroll skiljs från tekniska verktygsanrop.
4. **G4-app:** En verksamhetsspecialist använder AI-stödd kodgenerering för en intern applikation, testar den i avgränsad miljö och får en riskanpassad, förvaltad väg till bredare användning.

**Föreslagen illustrationplan (endast för beslut, inte produktion):**
- Fig 1: Fyra generationer med två axlar – *vem skapar lösningar* och *hur gemensamma förutsättningar tillhandahålls*.
- Fig 2: G2→G3 – från upprepade teknikbeställningar till självbetjänade plattformsprodukter.
- Fig 3: G3→G4 – assistent, agent och verksamhetsskapad app på gemensamma ramar.
- Fig 4: Översikt över de 13 förmågorna, grupperade enligt del II.
- Fig 5: Ansvarskarta: verksamhet, produktteam, plattformsteam och säkerhets-/arkitektur-/informationsansvar.
- Fig 6: Riskanpassad väg från personlig prototyp till kritisk produktionslösning.

Välj hellre **4–6 tydliga diagram i hela boken** än illustrationer i varje kapitel. Ingen diagramproduktion ingår i detta steg. Diagram ska vara källbara, tillgängliga och konsekvent gestaltade.

## 8. Återanvändning och redaktionell spårbarhet

| Källa | Status och planerad användning |
|---|---|
| 13 kritiskt granskade CAP-IT-kapitel | **Primär textkälla** för del II; bevara sakliga nyanser, men redigera för läsbarhet och samspel |
| CAP-IT-09 v3, övriga tolv v2 | Exakt identifierade senaste redaktionsnivåer; inga äldre utkast får tyst ersätta dem |
| 13 associerade YAML-modeller | Kontrollera tjänsteidentiteter, ansvar, generationsbeskrivningar och källreferenser; **inte** direkt boktext |
| Redaktionell helhetsgranskning v2 | Styr upprepningsreducering, gränsdragningar, operativ AI-nytta, verifiering och kapitelprioritet |
| Övergångsanalyser G1→G2, G2→G3, G3→G4 | Underlag för generationernas innebörd och de två förbättringsspåren |
| Förmågeöversikt och plattformsöversikt v1.1 | Fastställa 13 förmågor, 92 unika tjänster och deras relationer; rätta inte källmodellen tyst |
| Den tidigare bokliknande generationsbeskrivningen | Inspirations-/historikunderlag; använd inte som oidentifierat nytillkommet faktastöd |

**Viktigt:** Bokförfattarens sammanbindande resonemang, föreslagna G4-scenarier och eventuella verksamhetsexempel måste märkas i arbetsdokument som *redaktionell analys/illustration*, inte felaktigt påstås vara observationer i befintliga underlag. Granska varje tekniskt/juridiskt verifieringsbart påstående mot en lämplig primärkälla när det införs i publicerbar text. Inga myndighetsspecifika observationer eller riktiga incidenter ska återges som generella fakta utan källa.

**Föreslagen intern spårning vid kapitelredigering:** kapitel-ID → originalfil och version → redigerad bokkapitelversion → ändringssammanfattning → berörda YAML-fält → käll-/faktakontroll. Detaljerade schemaändringar i YAML hanteras som separat arbetsström om detta blir nödvändigt; blanda inte ihop dem med språkrevision.

## 9. Källpolicy och aktualitet

- Primära publikationer och standarder prioriteras för tekniska definitioner, best practice och säkerhetskrav; daterade utkast identifieras som utkast.
- Beskriv G4 som **framtidsorienterade organisatoriska möjligheter** och tydliggör osäkerhet om teknik, mognad och effekter. Undvik löften om att AI automatiskt ökar kvaliteten.
- Verksamhetsexempel är uttryckligen fiktiva. Skilj generell god praxis från rättsliga krav som varierar med sektor och jurisdiktion.
- Källor kan presenteras samlat i en kort referensdel; internt spåras vilka påståenden varje källa stöder.
- Länkar, versionsnummer och tidskänsliga AI-påståenden granskas på nytt före publicering.
- Avgränsning mellan *författarens redaktionella syntes*, befintlig sakmodell och kontrollerad extern fakta dokumenteras i arbetsmaterialet.

## 10. Kvalitetsgrindar innan full produktion

**Grind A – godkänd bokplan:** Godkänn titel och undertitel, målgrupp, tredelning, G3/G4-vikt, kapitelordning, bilageprincip och omfattningsram. Författare och omslag kan beslutas inför projektstart/export enligt verktygets krav.

**Grind B – provmanus:** Skriv inledning, kapitel 2 om generationerna och **ett** kontrasterande förmågekapitel (rekommenderat CAP-IT-05 med stark operativ AI-koppling). Testa om läsaren förstår ansvars-/teknikförflyttningen utan repetitionskänsla. Mät ord, läsbarhet och sakförlust mot granskad originaltext. Godkänn eller justera mall.

**Grind C – tre kapitel i kontrast:** Bearbeta därefter CAP-IT-09 och CAP-IT-02 för att testa teknikdrift respektive verksamhetsprocesser. Bedöm om samma kapitelmall fungerar för olika innehåll utan att bli mekanisk.

**Grind D – resterande tio:** Redigera i tematiska grupper; behåll versionsspårning och kontrollera delade PLS-ansvar. Varje redigering får ändringslogg och läsarfärdig granskning.

**Grind E – boksyn och slutkontroll:** Läs obrutet manus, granska repetitionsgrad, förståelse av G4 och IT:s möjliggörarroll, kontrollera källor, illustrationer, navigation och bilagor. Extern sakkontroll är separat från intern redaktionell granskning. Exportera PDF/EPUB först efter ett verifierat bokprojekt och nödvändiga verktyg.

**Beslut om granskningsansvar:** Manuell granskning av användaren eller automatisk intern redaktionell granskning per kapitel kan väljas efter att en kapitelrevision finns. Inget kapitel eller bokprojekt är godkänt bara genom denna plan.

## 11. Beslutspunkter för godkännande

**Föreslagna standardval att godkänna tillsammans:**

1. Titel: *Från IT-leverantör till möjliggörare för digitalisering*; undertitel enligt avsnitt 1.
2. Svenska, profil `factbook`, målgrupp och ton enligt avsnitt 2.
3. Del I om generationerna, del II med alla 13 förmågor och del III om ansvar/kompetens.
4. G1/G2 relativt korta, G3/G4 jämbördigt fördjupade; G4:s tre konkreta former explicit.
5. Förmågor i den föreslagna tematiska ordningen, med CAP-IT-mappning som bakgrund.
6. Bilagor A–C korta; YAML och teknisk katalog separat.
7. Koncentrerad ordnivå, ungefär 39 000–44 000 ord inklusive inledning/huvuddelar före referensregister, med möjlighet att korta ytterligare.
8. Provskriv först inledning, generationskapitlet och CAP-IT-05; därefter CAP-IT-09 och CAP-IT-02.

**Kan fastställas senare utan att stoppa bokplanen:** Författaruppgift, exakt omslagsform, vilka 4–6 föreslagna diagram som ska skapas, slutlig boktypografisk form och exportdatum.

**Det denna leverans inte gör:** Skapar inte bokprojektets `book.yaml`, en projekt-ZIP, redigerade bokkapitel, illustrationer, EPUB eller PDF. Inga befintliga kapitel eller YAML-filer är ändrade.
