# CAP-IT-11 – Slutanvändarmiljö och klientplattform

En digital tjänst slutar inte vid servern. Den behöver nås från en dator, mobil, surfplatta, en specialiserad arbetsstation eller en virtuell arbetsplats. **Slutanvändarmiljö och klientplattform** är förmågan att erbjuda och livscykelhantera säkra, förvaltade och användbara tekniska miljöer där människor använder organisationens digitala tjänster. Förmågan handlar inte främst om vilket operativsystem eller vilken enhetsleverantör man väljer. Den handlar om att en lämplig klient ska fungera, vara skyddad, kunna förändras utan oacceptabla avbrott och kunna avvecklas utan att information och åtkomst lämnas kvar.

Fyra tjänster ingår i den etablerade förmågemodellen: **UEM/MDM** för hantering av enheter (PLS-045), **applikationsdistribution till klienter** (PLS-046), **endpointskydd** (PLS-077) och **virtuella skrivbord/DaaS** (PLS-047). De stöds av tre konceptuella plattformar: PLT-010 Endpointhanteringsplattform, PLT-011 Security Operations- och skyddsplattform och PLT-037 Virtuell arbetsplatsplattform. Detta är modellens avgränsning, inte en obligatorisk inköpslista. Några verksamheter använder bara två av tjänsterna i större skala; andra har goda skäl att använda alla fyra.

Fyra generationer används som **analytiska idealtyper**. De är inte historiskt vattentäta tidsperioder eller en tekniktrappa som alla organisationer måste följa. Den huvudsakliga utgångspunkten är generation 2: fler tjänster, fler klienttyper och snabbare förändringar, men inte alltid ett sammanhängande ansvar för den digitala arbetsplatsen. Vi skiljer därför mellan sådant som måste fungera **redan i generation 2** och det som kan motivera en **gemensam självbetjänad plattform i generation 3**. Generation 4 är ett scenario med mer verksamhetsnära och AI-stödd digitalisering, inte en fastställd framtid.

## Kort tillbakablick: generation 1

När många IT-stöd bestod av större, sammanhållna applikationer kunde klientmiljön ofta standardiseras kring en stationär dator, ett fåtal operativsystem och ett mindre antal installerade program. Klientdrift tog emot beställningar, byggde standardavbilder, installerade program och återställde felaktiga enheter. En gemensam image och planerade uppgraderingsfönster kunde ge god stabilitet i en relativt homogen miljö. Den modellen var inte nödvändigtvis osäker eller omodern för sitt faktiska behov.

**Förflyttningen G1→G2** innebar fler webbtjänster, mobila enheter, distansarbete, externa användare och fler applikationsuppdateringar. Klientmiljön behövde då stödja flera operativsystem, kortare förändringscykler och åtkomst från olika sammanhang. Samtidigt levde manuella beställningar, lokala administratörsrättigheter och särskilda programinstallationer ofta kvar. Det är detta generationsarv som behöver granskas – inte klientens ålder i sig.

## Generation 2 – flera enheter, tjänster och ansvar

### När blir förmågan verksamhetskritisk?

En handläggare använder ett ärendesystem i webbläsaren, en fältmedarbetare dokumenterar besök i mobilen och en extern konsult använder en äldre klientapplikation. Alla tre kan arbeta mot samma bakomliggande verksamhetstjänster. Men en föråldrad webbläsare, en mobil som inte synkroniserat sin säkerhetspolicy eller en installerad klient med fel version kan göra att användarresan misslyckas även när servrarna är friska. Då är det inte tillräckligt att övervaka applikationsservern; organisationen behöver veta vilka klienter som används, hur de skyddas och var förändringar har fastnat.

Den första frågan är **vilka enheter och åtkomstsituationer som faktiskt finns**. Äger organisationen enheterna? Är de personliga, delade eller tillfälliga? Finns verksamhetskritiska offlineklienter, specialutrustning eller användare med tillgänglighetsbehov? Vilken information behandlas lokalt? Ett riskbaserat klienterbjudande kan behöva flera standardprofiler. Att försöka pressa en fältsurfplatta och en delad terminal i samma policy kan skapa både säkerhetsluckor och användbarhetsproblem.

### Förlorad mobil, misslyckad uppdatering och extern konsult

Betrakta ett sammanhängande diagnostiskt exempel. En fältmedarbetare förlorar sin telefon efter att ha arbetat offline med ett antal ärenden. Samma vecka rullas en ny version av ett klientprogram ut och får vissa bärbara datorer att krascha. Dessutom avslutar en extern konsult sitt uppdrag men har fortfarande en aktiv virtuell arbetsplats. Alla tre händelserna testar klientförmågan, men på olika sätt.

För den förlorade mobilen behöver organisationen ta reda på **vilka data som faktiskt lagrades lokalt**, om de är krypterade, vilka konton och sessioner som kan användas och vilka åtgärder som stöds av enhetens hanteringsläge. En fjärrradering kan fördröjas eller aldrig genomföras om enheten inte ansluter igen. Att skicka ett raderingskommando är därför inte samma sak som att bevisa att data har raderats. Åtkomst kan behöva spärras separat genom identitets- och sessionstjänsterna, och offlineuppgifter kan behöva hanteras som ett informations- och kontinuitetsproblem.

För klientuppdateringen behöver organisationen veta vilka enheter som omfattades, om problemet kan isoleras till en viss drivrutin eller programversion och hur vidare utrullning stoppas. Att återställa en paketversion är inte alltid lika enkelt som att avinstallera den nya: datamigrering, inställningar, säkerhetspatchar och beroenden kan göra en teknisk nedgradering riskabel eller omöjlig. Ibland är en framåträttande version, en alternativ arbetsväg eller återställning av hela klientprofilen säkrare. **Utrullning i ringar**, där en begränsad grupp uppdateras före resten, minskar konsekvensen när fel uppstår men ersätter inte fungerande återhämtningsrutiner.

För konsulten behöver organisationen kunna visa att uppdragets slut utlöser rätt åtgärder: nya inloggningar stoppas, befintliga sessioner hanteras enligt fastställda tidsgränser och virtuella profiler, temporära filer och licenser avslutas. Här behöver klientplattformen samverka med identitetshantering och informationsägare. Att avveckla ett virtuellt skrivbord tar inte automatiskt bort externt exporterade filer.

Ett enda diagnosprov kan alltså följa **enhet, identitet, applikation, data och ansvar** från tilldelning till avslut. Det visar också varför ett centralt verktyg inte ensamt löser alla problem.

### Fyra funktioner – olika ansvarsgränser

**Enhetshantering (UEM/MDM)** omfattar registrering, enhetsprofiler, operativsystemsversioner, krypteringsstatus, konfiguration och efterlevnadssignaler. Hanteringsgraden beror på enhetstyp, ägarförhållande och operativsystemets funktioner. En personligt ägd mobil kan till exempel tillåta en begränsad förvaltning av arbetsappar och arbetsdata utan att organisationen har rätt eller teknisk möjlighet att hantera hela den privata enheten. Man måste inte välja samma styrmodell för ägda och privata enheter.

**Applikationsdistribution** handlar om paketering, signering och kontrollerad installation eller uppdatering av klientprogram. Det är något annat än att bygga källkod eller distribuera en webbtjänst: de aktiviteterna hör främst till CAP-IT-10. För rena webblösningar kan behovet av särskild klientdistribution vara litet, medan äldre lokalprogram, mobilappar och specialiserade klienter behöver robustare distribution.

**Endpointskydd** omfattar hotförebyggande, detektion, lokal isolering och incidentstöd. Detektionsförmåga, säkerhetsanalys och respons hör till CAP-IT-12. Klientplattformen måste däremot bidra till att skyddet faktiskt installeras, är aktivt på relevanta enheter och inte slutar rapportera utan att någon märker det. En grön complianceindikator är en signal, inte ett bevis på att enheten är ofarlig. Tjänsten måste bedömas med prov av både skyddets täckning och responsens funktion.

**Virtuella skrivbord eller DaaS** är ett särskilt sätt att tillhandahålla en klientmiljö. Det kan underlätta stöd för äldre applikationer, begränsa lokal datalagring eller ge tidsbegränsad åtkomst för konsulter. Det är ingen generell förutsättning för moderna webbapplikationer. Ett virtuellt skrivbord kan fortfarande låta användaren kopiera information till urklipp, skriva ut, fotografera skärmen eller exportera filer. Isoleringens värde måste därför verifieras mot de faktiska informationsflödena, inte antas utifrån produktnamnet.

### Privatägda, delade och specialiserade enheter – olika kontrollmöjligheter

För en **organisationsägd, fullt hanterad klient** kan enhetsansvarig ofta ställa mer omfattande krav på konfiguration, inventering och åtgärder. För **privatägda enheter (BYOD)** måste hanteringen däremot avgränsas av överenskommen policy, integritet och den teknik som faktiskt stöds. En hanterad arbetsprofil eller applikationsbehållare kan minska åtkomsten till privat information och möjliggöra borttagning av vissa arbetsdata. Den garanterar inte att alla arbetsuppgifter kan raderas: exporterade filer, kopierat innehåll, lokala säkerhetskopior och redan delad information kan finnas kvar. En arbetsplats bör därför skilja mellan *rätt att hantera viss arbetsdata*, *teknisk möjlighet att radera den* och *bevis för att radering har utförts*. Fullständig radering av en privat enhet får inte antas vara vare sig möjlig eller lämplig.

En **delad terminal** behöver i stället provas för användarbyte. När en person loggar ut och en annan loggar in ska kvarvarande dokument, cache, nedladdningar, åtkomsttoken, skrivarköer och pågående webbsessioner inte exponera föregående användares information. Enheten kan tekniskt rapporteras som godkänd samtidigt som den aktuella sessionen eller användarväxlingen är osäker. En gemensam enhetsprofil löser inte automatisk separation mellan användare; testet måste göras genom ett faktiskt byte.

**Specialklienter, medicinsk eller industriell utrustning och offlinefältenheter** kan ha leverantörslåsta system eller långa godkännandecykler. Det innebär varken att osupporterade system bör accepteras utan vidare eller att normal patch- och EDR-policy alltid kan appliceras. Där behöver organisationen dokumentera risk, berörd informationsmängd, ägare, kompenserande skydd, tillåten nätanslutning, underhållsfönster och en realistisk plan för ersättning eller avveckling. En långvarigt offline klient måste dessutom kunna skilja mellan osynkroniserade arbetsuppgifter och föråldrade åtkomstbeslut; en lokal kö får inte okontrollerat återspelas efter att användarens mandat har upphört.

### Vad måste fungera redan i generation 2?

För relevanta klienter behövs en trovärdig inventering, ansvarig förvaltningsfunktion, riskanpassad patchning och skydd, dokumenterade åtkomstvägar, kontrollerad distribution och hantering av förlorade eller avvecklade enheter. Det betyder inte att allt måste ske genom en enda produktsvit eller i en portal. En liten organisation med få likartade klienter kan uppfylla kraven med enklare verktyg och tydliga rutiner; en stor heterogen flotta kan behöva avancerad central hantering redan nu.

Mät **täckning och utfall**, inte bara antalet inköpta licenser: hur många faktiska klienter saknar känd ägare, nödvändiga uppdateringar eller fungerande skydd? Hur lång tid tar det att stoppa åtkomst för en förlorad enhet? Hur ofta leder en utrullning till användarstörningar, och hur snabbt kan den stoppas? Kan en användare genomföra sin arbetsuppgift på en tillåten klient, även med hjälpmedel eller begränsad nätanslutning? Klientplattformen ersätter inte tillgänglighetsarbetet i CAP-IT-01 men måste ge kompatibla tekniska förutsättningar.

### Grundproblem eller motiv för generation 3?

Två åtgärdsspår ska hållas åtskilda. **Spår A – rätta generationsarvet:** skapa känd enhetsinventering, säkra livscykler, tydligt ansvar, verifierbar patchning, kontrollerad uppdatering och hantering av incidenter. Dessa behov kan inte skjutas upp tills en ny plattform finns. **Spår B – bygg ett återanvändbart erbjudande:** när många team regelbundet beställer samma klientprofiler, program, åtkomster och undantag kan standardisering och självbetjäning minska ledtid och variation. Den andra typen av problem är en plattformsmognadsfråga, inte nödvändigtvis en akut säkerhetsbrist.

## Från generation 2 till generation 3 – en förvaltad digital arbetsplats

Generation 3 innebär att den digitala arbetsplatsen utvecklas till ett **internt produkterbjudande**. Ett klientplattformsteam erbjuder godkända profiler för vanliga användningsfall och ansvarar för deras stöd, uppgradering, övervakning, kostnad och avveckling. Nya enheter kan automatiskt registreras och konfigureras där tekniken medger det. Användare kan begära godkända appar genom en katalog, medan känsligare installationer kräver ett tydligt godkännandeflöde.

Självbetjäning betyder inte att alla får administratörsrättigheter. Det betyder att de behov som har bedömts som säkra och återkommande kan tillgodoses utan en ny manuell specialutredning. Plattformen behöver erbjuda förutsägbara ledtider, begripliga villkor och tillgängliga alternativ för användare med särskilda behov. Ett enkelt ärende kan ibland vara bättre än en komplex portal om användargruppen är liten.

Den svåra delen är inte nyregistrering utan **hela livscykeln**. En förvaltad klientprofil ska kunna ändras, migreras, återställas efter fel, följas upp och tas ur bruk. Ett misslyckat policybeslut kan slå mot tusentals enheter samtidigt; därför behövs pilotringar, stoppvillkor, ansvariga beslutsfattare och en fungerande administrativ återhämtningsväg. En åtkomstpolicy som oavsiktligt spärrar allas klienter måste kunna korrigeras utan att vara beroende av just de spärrade klienterna.

Ett meningsfullt plattformstest följer en hel kedja: en ny medarbetare får rätt klientprofil och nödvändiga program, använder en tjänst, får en appuppdatering, hamnar i en kontrollerad avvikelse, byter roll och lämnar sedan organisationen. Kontrollera vilka steg som sker utan manuell handpåläggning, vad de kostar och om användaren faktiskt kan arbeta. **Provisioneringens hastighet** är bara en del av kvaliteten; lämpligt mått är också hur snabbt fel kan rättas och rättigheter avslutas.

Plattformstjänsten måste ha klara ansvarsgränser. Klientteamet förvaltar enheter och standardprofiler. Applikationsteamen ansvarar för stöd för de klienter de valt. IAM-teamet hanterar identiteter och tillitsbeslut. Säkerhetsteamet definierar och förvaltar säkerhetskontroller. Informationsägaren bestämmer vad användningen av känsliga data tillåter. Den gemensamma plattformen samordnar dessa förmågor men tar inte över alla besluten.

### Återhämtning från centrala policyfel och klientuppdateringar

En självbetjänad klientplattform kan också öka **spridningshastigheten för fel**. En felaktig central compliancepolicy kan stänga ute många användare samtidigt, och ett felaktigt program- eller drivrutinspaket kan slå ut en hel verksamhetsgrupp. Därför bör varje standardprofil ha en definierad ändringsägare, testgrupp, mätbara stoppvillkor och en separat, skyddad reservväg för administration. Reservvägen ska testas i förväg; det räcker inte att den finns beskriven i ett dokument.

En framgångsrik uppdatering betyder att **verksamhetsuppgiften fortfarande kan utföras**, inte bara att paketet visar installerad status. Kontrollera exempelvis inloggning, hjälpmedel, utskrift, externa tillbehör och kritiska arbetsflöden efter klient- eller webbläsarändringen. För mobilappar som distribueras via butiker eller förvaltas av operativsystemet är återkallelse, versionsnedgradering och tidpunkt för installation ibland delvis utanför organisationens direkta kontroll. Då blir bakåtkompatibilitet, möjlighet att stoppa serverbaserade funktioner och säkra alternativa arbetssätt viktigare än ett löfte om omedelbar rollback.

### Varför inte alltid en enda klientplattform?

Det kan finnas goda skäl att använda olika hanteringsvägar för kontorsdatorer, fältenheter och specialutrustning. Licensvillkor, livslängd, offlinekrav, säkerhetscertifieringar eller operativsystemets begränsningar kan göra en enhetlig produkt olämplig. Plattformsmognad bör därför bedömas utifrån om **flera godkända profiler går att förstå och förvalta som en helhet**, inte om de delar leverantör.

På samma sätt är virtuell arbetsplats en produkt för vissa behov, inte en destinationsarkitektur. Om en lättanvänd webbapplikation fungerar säkert på en hanterad dator kan ett fullt virtuellt skrivbord tillföra kostnad och fördröjning utan motsvarande nytta. Om en äldre applikation annars kräver lokal installation och breda rättigheter kan en förvaltad fjärrmiljö däremot minska risken avsevärt. Värdet är användningsfallsberoende.

## Generation 4 – klienten som kontrollerad ingång till verksamhetsnära utveckling

I ett tänkbart fjärde generationsmönster kan verksamheten snabbare skapa och använda AI-stödda applikationer. Klientens roll blir då att erbjuda **kontrollerad konsumtion av fler och snabbare föränderliga tjänster**. Det innebär inte att alla medarbetare ska använda privat utrustning eller att en AI-assistent automatiskt får åtkomst till lokala filer och interna system.

En klient kan vara hanterad utan att varje tjänst är betrodd, och en tjänst kan vara godkänd utan att varje enhet är lämplig att använda den på. Åtkomst behöver därför bedömas utifrån användarens identitet, enhetens tillstånd, informationens känslighet, sessionens sammanhang och handlingens risk. Klientstatus kan vara en värdefull signal till CAP-IT-07, men den ger inte verksamhetsbehörighet i sig. Ett godkänt säkerhetstillstånd kan dessutom föråldras mellan två kontroller; det behövs beslut om uppdateringsfrekvens och hur osäkerhet hanteras.

För verksamhetsnära appar kan en standardwebbläsare med styrda inställningar vara tillräcklig. För särskilt känsliga dokument eller externa uppdrag kan en isolerad webbläsarmiljö eller virtuell arbetsplats vara bättre. Begränsningar av urklipp, nedladdning och utskrift kan minska vissa risker men inte eliminera dem, och felaktigt skärpta restriktioner kan göra arbetet orimligt svårt. Användarupplevelse, informationsskydd och kostnad behöver därför bedömas tillsammans.

AI-assistenter på klienten skapar nya frågor om **vilka filer och sessioner de får läsa, vilka externa tjänster de får kontakta och vilka åtgärder de får initiera**. Det räcker inte att en modell instrueras att följa regler. Åtkomst behöver tekniska spärrar, granskningsbar användning och ibland mänskligt godkännande vid riskfyllda handlingar. Samtidigt ska man inte likställa installerad AI-programvara med egen AI-modellkörning eller anta att den kräver GPU, DaaS eller en ny klientplattform.

Generation 4 bör alltså förstås som en förstärkt förmåga att **ge rätt arbetsform rätt riskprofil** med snabb och kontrollerbar livscykel. Den bygger på det som redan måste fungera i generation 2 och 3; den ersätter inte behovet av patchning, endpointskydd, återkallelse eller användbarhet.

### Vem agerar när klienten blir en verksamhetsincident?

Om en fältenhet misstänks vara komprometterad samtidigt som den innehåller lokalt sparade ärenden behövs en uttalad **gemensam incidentkedja**. Klientteamet ansvarar för att lokalisera enheten, verifiera status och genomföra säkra enhetsåtgärder. Säkerhetsfunktionen (CAP-IT-12) leder den tekniska hotbedömningen och beslutar tillsammans med utsedda ansvariga om isolering och bevissäkring. IAM (CAP-IT-07) verkställer beslut om att begränsa identiteter, token och sessioner. Applikations- och informationsägare bedömer vilka uppgifter som kan ha exponerats, om osynkroniserat arbete riskerar att förloras och vilken reservprocess som behövs. Verksamheten ansvarar för prioritering när en säkerhetsåtgärd samtidigt stoppar en kritisk tjänst. Incidentledning och eventuella informationssäkerhets- eller integritetsanmälningar behöver följa organisationens fastställda ansvar; klientplattformen ska inte ensam avgöra dessa frågor.

Provfrågan är konkret: **kan organisationen isolera en testklient utan att samtidigt förstöra nödvändiga utredningsspår eller tyst tappa osynkroniserad verksamhetsinformation?** Det finns inte alltid ett perfekt tekniskt svar, men ansvar för riskavvägningen måste vara känt före incidenten.

## Hur upptäcker man att dagens teknik eller plattform inte längre passar?

En teknikdiagnos börjar i ett observerbart problem, inte i en produktjämförelse. Om mobiltelefoner saknar säkerhetsstatus kan orsaken vara att vissa enheter aldrig registrerats, att de tillhör ett hanteringsläge som inte ger önskad signal, att rapporteringen är felkonfigurerad eller att produkten faktiskt saknar erforderlig funktion. Om appar uppdateras långsamt kan problemet vara paketeringskompetens, testansvar, beslutsregler eller en distributionslösning som inte stödjer riktad utrullning. Om virtuella skrivbord känns långsamma kan nätverk, kapacitet, grafikkrav, placering och användarprofil vara viktigare än vilket DaaS-varumärke som används.

Undersök därför i denna ordning: **(1) vad behöver användaren och verksamheten uppnå, (2) vilka mätbara fel uppstår och var, (3) är orsaken policy/ansvar, konfiguration/integration, arkitektur eller en dokumenterad produktbegränsning, (4) kan problemet avhjälpas genom bättre användning eller komplettering, (5) först därefter – finns skäl för byte?** Fyra möjliga utfall är att behålla, komplettera, ändra användning/ägarskap eller ersätta. Ett generationsbyte kräver inte ett produktbyte.

Varningssignaler om **olämplig teknik** kan vara att förvaltade enheter inte kan uppgraderas inom nödvändig tid trots fungerande processer, att nödvändiga skyddskontroller saknas för relevanta enhetstyper, att plattformen inte erbjuder fungerande automatiseringsgränssnitt för återkommande behov eller att licens- och driftkostnader blir oproportionerliga jämfört med enklare alternativ. Men varningssignaler är undersökningspunkter, inte automatiska domar. En specialklient som behöver undantas från normal patchrytm kan kräva kompenserande skydd och tydligt ägarskap snarare än utbyte av hela klientplattformen.

För varje åtgärd ska **funktionskritikalitet**, **nytta av en gemensam plattform** och **behov av automatisering** bedömas separat. Det kan vara kritiskt att skydda klienter utan att bygga en egen endpointplattform. Det kan vara lämpligt att erbjuda DaaS för en liten extern användargrupp utan att göra det till standard för alla. Och det kan vara mer angeläget att åtgärda okända eller oskyddade enheter än att bygga en snyggare självbetjäningsportal.

## Nio verifieringsprov för en fungerande klientförmåga

1. **Ny enhet:** En godkänd dator eller mobil registreras, får rätt profil och skydd, och blir användbar utan oklara handgrepp. Dokumentera faktiskt förlopp och ledtid.
2. **Förlorad eller stulen enhet:** Testa spärr av nya sessioner, hantering av befintliga sessioner och fjärråtgärd på en testklient som avsiktligt hålls offline. Redovisa vad som är bekräftat respektive endast begärt.
3. **Felaktig uppdatering:** Distribuera ett ofarligt testpaket till en ring, upptäck fel, stoppa utrullningen och prova fungerande återhämtning även om nedgradering inte är möjlig.
4. **Säkerhetstäckning:** Skapa en kontrollerad avvikelse där endpointskydd saknas eller inte rapporterar. Kontrollera att tillståndet upptäcks och att åtgärdsansvaret är tydligt.
5. **Tillfällig virtuell arbetsplats:** Tilldela en extern testanvändare tidsbegränsad åtkomst, prova profilens informationsbegränsningar och avveckla session och resurser, inklusive kostnad och kvarvarande data.
6. **Åtkomst från olämplig klient:** Prova att en högriskresurs begränsar åtkomst från icke-kompatibel testklient. Dokumentera felaktiga spärrar, särskilda behov och hur en legitim användare återfår fungerande åtkomst.
7. **Delad enhet eller BYOD:** Byt användare på en delad testterminal och prova vad nästa användare kan se. För privat enhet, prova endast avtalad hantering av arbetsdata och dokumentera vad som kan respektive inte kan raderas eller kontrolleras.
8. **Specialklient och störd uppkoppling:** Följ en längre offlineperiod, försök synkronisera efter att ett mandat löpt ut och visa hur både dataförlust och obehörig återspelning förhindras eller hanteras.
9. **Kritiskt användarflöde och hjälpmedel:** Genomför ett representativt arbete före och efter klientuppdatering med relevanta hjälpmedel eller kringutrustning; mät faktiskt utfall, inte bara installationsstatus.

Dessa prov ska utformas för den egna verksamhetens informationsklassning och klienttyper. De bevisar inte all säkerhet; de gör däremot ansvar, avvikelser och plattformens faktiska erbjudande synliga.

## Mätbar kvalitet – också för användare med särskilda behov

Tre typer av uppföljning bör redovisas separat. **Säkerhet och kontroll:** andel enheter med verifierad ansvarig och godtagbar skyddsstatus, tid från riskupptäckt till åtgärd och antal öppna undantag med passerat slutdatum. **Livscykel och effektivitet:** tid till fungerande arbetsplats, andel uppdateringar som stoppas i pilotring innan bred påverkan och antal avvecklade enheter där data- och åtkomståtgärder är bekräftade respektive fortfarande osäkra. **Faktisk användbarhet:** andel representativa användare som kan slutföra en kärnuppgift på sin godkända klient, med relevanta hjälpmedel, specialtillbehör och normal respektive bristfällig uppkoppling.

Mått behöver segmenteras. Ett genomsnitt för alla kontorsdatorer kan dölja att en liten grupp med skärmläsare, en delad receptionsterminal eller en fältenhet med intermittent nätverk inte längre fungerar. Ett rimligt prov är att definiera ett kärnflöde per viktig klientklass, inklusive åtkomst, lokalt arbete, avbrott och återhämtning. Dokumentera vilken del av felet som hör till klientplattformen respektive användargränssnittet i CAP-IT-01, nätverket i CAP-IT-13 eller verksamhetsapplikationen.

## Slutsats: en förmåga att konsumera digitala tjänster, inte bara hantera datorer

Slutanvändarmiljön följer samma utvecklingslogik som andra IT-förmågor, men har en särskild egenskap: **användaren upplever omedelbart följderna av brister i klientens funktion och skydd**. Generation 1 kunde skapa stabilitet med få standardmiljöer. Generation 2 behöver kontroll över många typer av klienter och snabbare förändringar. Generation 3 gör återkommande klientbehov till pålitliga, förvaltade erbjudanden som användare och team lätt kan använda. Generation 4 kan dessutom stödja fler verksamhetsnära och AI-stödda lösningar med riskanpassade åtkomstvägar.

Det viktigaste beslutet är inte att välja det mest avancerade verktyget. Det är att avgöra **vad som behöver fungera säkert redan nu**, **vilka återkommande moment som tjänar på en gemensam plattform** och **vilka teknikval som ger bästa stöd utan att skapa onödig komplexitet**.

## Källor och redaktionell evidens

**Primärt underlag:** *Förmågeöversikt – tekniska IT-förmågor*, baseline v1.1 (CAP-IT-11); *Plattformsöversikt – konceptuella plattformar* (PLS-045, PLS-046, PLS-077, PLS-047 samt deras PLT-kopplingar); *Från systemdrift till digital självständighet* (generationsram). Tjänsteidentiteter och definitioner är hämtade ur underlaget. Generationstolkningar, exempel, diagnosmetoder och indikatorer är redaktionella arkitekturbedömningar – inte empiriska påståenden om någon bestämd organisation.

**Kompletterande tekniska referenser:** NIST SP 800-124 Rev. 2 (2023), [Guidelines for Managing the Security of Mobile Devices in the Enterprise](https://csrc.nist.gov/pubs/sp/800/124/r2/final), om mobila enheters livscykel och säkerhet; NIST SP 800-46 Rev. 2 (2016), [Guide to Enterprise Telework, Remote Access, and BYOD Security](https://csrc.nist.gov/pubs/sp/800/46/r2/final), om riskbaserad fjärråtkomst och personligt ägda enheter; NIST SP 800-53 Rev. 5, [Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final), som kontrollkatalog för riskanpassat urval (inklusive senare uppdateringar; kontrollkatalogen är inte ett föreskrivet teknikval). Dessa källor fastställer inte att någon viss plattformstjänst är obligatorisk i en viss generation.
