# Nätverk och konnektivitet

*CAP-IT-13 · Faktaboksunderlag · version 2.0 · 7 november 2026*

En utvecklare behöver koppla en ny tjänst till en databas och två andra tjänster. Det som förefaller vara några få anrop riskerar att bli en kedja av ärenden: rätt nätverkszon måste fastställas, en brandväggsöppning beställas, DNS konfigureras och en extern anslutning kontrolleras. Varje del kan hanteras för sig utan att någon har en sammanhållen bild av beroendena. Samtidigt kan en gammal, bred brandväggsregel bli kvar långt efter att tjänsten avvecklats. Det är en igenkännbar situation i en organisation som har delat upp sina applikationer i mindre tjänster, men behållit nätverkets äldre arbetsformer.

Det här kapitlet börjar därför i **generation 2**, den distribuerade IT-miljön. Det beskriver först vilket nätverksstöd som behövs redan där, sedan hur en organisation kan gå vidare till gemensamma, automatiserade plattformserbjudanden och slutligen vilka ytterligare behov som uppstår när verksamheten i större utsträckning kan skapa egna digitala lösningar.

## Vad förmågan handlar om

Nätverk och konnektivitet är förmågan att ge människor, enheter, applikationer och plattformar rätt möjligheter att kommunicera – med lämplig tillgänglighet, prestanda, skydd och förvaltning. Den omfattar bland annat namnuppslagning, adressering, lokala nät, anslutningar mellan platser, internetanslutning, trafikvägar, lastbalansering, nätsegmentering och tekniska trafikpolicyer.

Det är viktigt att skilja **att två parter tekniskt kan nå varandra** från **att deras informationsutbyte är korrekt och tillåtet**. Nätverksförmågan hanterar anslutbarheten (*reachability*), medan CAP-IT-06 Integration och informationsutbyte tar ansvar för API- och meddelandekontrakt, och CAP-IT-07 Identitet och tillit för identitet och tekniskt tillitsunderlag. CAP-IT-12 Cybersäkerhet och tekniskt skydd kompletterar med andra skyddsmekanismer. Ett öppet nätflöde innebär alltså varken att anropet är autentiserat eller att mottagaren ska lämna ut begärda uppgifter.

En enskild server, en användare på kontoret och en tillfällig AI-assistent kan ha olika behov. En förmåga som fungerar väl behöver kunna ge rätt sorts anslutning för varje situation – inte tvinga allt genom samma teknik, samma zoner eller samma godkännandekö.

## När är förmågan relevant?

Nästan varje digitalt IT-stöd behöver någon nätverksanslutning, men det betyder inte att alla organisationer behöver alla tolv tjänster i den konceptuella förmågemodellen. Börja med att undersöka: Finns flera geografiska platser? Hur många tekniska tjänster kommunicerar internt? Finns internetexponerade API:er, externa myndighetsanslutningar eller särskilda fältverksamheter? Vilka konsekvenser får förlorad anslutning, hög fördröjning eller otillåten åtkomst? Finns tjänster med mycket kort livslängd?

**Kritisk nätverksfunktion är inte samma sak som krav på en central nätverksplattform.** För en enskild liten lösning kan välskötta, relativt enkla nätresurser räcka. För hundratals återkommande och föränderliga tjänsteflöden blir standardisering, spårbarhet och automation betydligt mer värdefullt. En verksamhet utan mediedistribution eller specialiserad fältkommunikation behöver inte bygga sådana plattformstjänster enbart därför att de finns i katalogen.

## Kort tillbakablick: generation 1 och arvet in i generation 2

I den traditionella modellen var antalet stora system och trafikrelationer ofta hanterbart. Servergrupper kunde placeras i zoner, brandväggar kunde avskilja miljöer och nätverksändringar kunde behandlas som relativt sällsynta beställningar. Det arbetssättet kunde ge robusthet och tydliga ansvar när beroendena var få och stabila. Även i dag är fast segmentering, väldokumenterade länkar och manuella beslut fullt rimliga för vissa stabila eller särskilt riskfyllda miljöer.

När en monolit delas upp i flera tjänster ökar ofta antalet trafikrelationer. Ett verksamhetsflöde som tidigare byggde på interna anrop kan nu kräva nättrafik mellan klient, ingress, flera tjänster och datalager. Däremot behöver inte varje uppdelning i mindre tjänster medföra motsvarande ökning av nätverksregler: det beror på topologi, kommunikationsmönster och hur säkerhetsgränser utformas. Felen kan uppträda som intermittenta fördröjningar eller att endast vissa delar av verksamhetsflödet fungerar. Det är inte säkert att nätverksfunktionens dokumentation, beställningsrutiner och ansvar följde med i förändringen.

**Kvarvarande generationsarv** kan därför bestå av alltför grova brandväggszoner, manuellt hanterade namnposter, personberoende kunskap om trafikvägar och regler som saknar känd ägare. Detta är inte i första hand ett argument för att införa en ny plattform. Det är tecken på grundläggande brister som kan behöva åtgärdas för att den distribuerade miljön ska bli begriplig och säker.

## Generation 2 – många tjänster, många kommunikationsberoenden

### Vilket stöd behöver finnas?

Organisationen behöver veta **vilka tjänster som ska kunna tala med vilka**, över vilka gränser, med vilken tillgänglighet och för vilket ändamål. Det kräver inte att varje nätflöde finns i en perfekt central modell, men kritiska beroenden ska gå att härleda från tjänst till trafikregel, namnuppslagning, lastbalanserare och eventuell extern anslutning. Både tillåten och avvisad trafik måste kunna felsökas utifrån tillräckliga loggar, konfigurationsuppgifter och tydligt ägarskap. Fullständig registrering av varje paket är varken nödvändig eller alltid förenlig med integritets- och lagringskrav.

Namnuppslagning (DNS) och IP-adresshantering (IPAM) behöver vara korrekta och ha tydliga ägare. Lastbalansering och ingress behöver förmedla trafik till rätt instanser och hantera degradering när en instans faller bort. För kommunikation mellan datacenter, moln, plattformar och verksamhetsplatser behöver kapacitet, fördröjning och redundans följas i relation till verksamhetens krav. Om många arbetslaster delar nät behöver man begränsa onödiga kommunikationsvägar så att ett fel eller intrång inte sprids fritt i miljön.

Trafikregler kan fortsätta vara centralt förvaltade och delvis manuella. Men processen behöver hantera fler ändringar, ha rimliga ledtider och kunna visa varför varje öppning finns. En regel som tillåter all trafik mellan två stora zoner därför att detaljerna är svåra att administrera är inte automatiskt en god lösning. Omvänt ska strikta regler inte införas så mekaniskt att nödvändig kommunikation ständigt bryts eller att team kringgår kontrollerna.

NIST:s Zero Trust-arkitektur ger en användbar princip: ingen resurs eller aktör ska få implicit tillit enbart för att den finns i ett internt nät. Men detta innebär inte att brandväggar, segmentering eller fysisk nätverksdesign blir oviktiga. Nätkontroll och autentisering kompletterar varandra.

### Hur ansvaret behöver fungera

Nätverksfunktionen ansvarar för säkra trafikvägar, tekniska anslutningsprofiler, ändringsbarhet och felsökningsbarhet. Applikations- eller produktteamet behöver ange ändamålet, vilka tjänster som måste kommunicera och vilka konsekvenser avbrott får. Identitets- och säkerhetsfunktionerna ansvarar för kompletterande krav och regler, medan integrationsansvaret omfattar innehåll och kontrakt i informationsutbytet. Någon måste kunna samordna en incident som sträcker sig över dessa gränser.

En vanlig fallgrop är att nätverksteamet förväntas härleda verksamhetens behov från en teknisk portlista. En annan är att utvecklingsteam ges full frihet att öppna kommunikation utan ägarskap, granskning eller avveckling. Båda ytterligheterna skapar risker och långsamma förändringar.

### Indikatorer på att förmågan ger tillräckligt stöd

- En representativ verksamhetskedja kan följas genom DNS, ingress, interna och externa nätflöden utan att team måste rekonstruera trafikbilden från minnet.
- Ett kontrollerat test visar att en otillåten anslutning blockeras och, där tekniken medger det, vilken policy som orsakade avslaget. Tillåtna anrop fungerar utan odokumenterade undantag.
- Ett riskanpassat felprov eller en övning visar om alternativa nätvägar och lastbalansering fungerar enligt överenskomna mål. Nätverkets reservvägar kan inte ensamma garantera att ett helt verksamhetsflöde fortsätter fungera; även applikationens felhantering måste prövas.
- Regler, namnposter och externa anslutningar har identifierbara ägare och rutiner för ändring och avveckling. Stickprov på avvecklade tjänster visar att onödiga vägar verkligen stängs.
- Beställnings- och felsökningstider mäts för olika typer av ärenden; enstaka komplicerade undantag blandas inte ihop med enkla normalfall.

### Indikatorer på olämplig teknik eller plattform

**Funktion och interoperabilitet.** Utrustning eller verktyg kan inte hantera nödvändiga trafikmönster, kryptering eller namnupplösning i de miljöer som används. Pröva ett representativt tvärmiljöflöde innan produktens begränsningar fastslås.

**Säkerhet och livscykel.** Nätverksprodukter får inte säkerhetsuppdateringar eller saknar stöd för tillräckligt snäva trafikregler. Kontrollera versionsstöd, regelgranularitet och faktisk förändringshantering. Även en modern produkt kan vara osäkert konfigurerad.

**Automatiserbarhet.** Varje standardändring kräver handarbete i en konsol, trots att miljöerna ändras ofta. Undersök om API, deklarativa modeller eller befintliga automationsverktyg kan användas innan produkten byts.

**Kostnad och skala.** En växande mängd nätverksregler, licenser eller anslutningar medför kraftig kostnads- eller ledtidsökning. Bedöm trafik, regelmängd, faktisk driftstid och ägandekostnad snarare än enbart styckepris.

**Leverantörsberoende.** Policyer, nätkonfiguration och driftdata kan inte exporteras eller testas i en alternativ miljö utan orimligt arbete. Genomför ett begränsat migreringsprov och uppskatta effekten av att byta verktyg.

Dessa tecken ska alltid följas av en orsaksanalys: handlar det om själva tekniken, integrationer, arkitektur, sättet att använda den eller organisatoriska beslut? En produkt som saknar en viss automationsfunktion är inte nödvändigtvis olämplig för en stabil och sällan förändrad miljö. Omvänt kan en modern nätprodukt vara ett dåligt val om dess driftmodell skapar ett svårt beroende till en liten grupp specialister.

### Två förbättringsspår i generation 2

**Spår A – få distribuerad konnektivitet att fungera.** Kartlägg kritiska kommunikationsrelationer, minska obefogat breda trafikvägar, inför ägarskap och avveckling av regler, förbättra felsökning och verifiera redundans. Detta behöver fungera även om organisationen behåller dagens nätplattformar och beställningsmodell.

**Spår B – minska repetitivt manuellt arbete genom gemensamma erbjudanden.** Om många team ständigt behöver samma säkra nätmönster kan nätverksfunktionen erbjuda godkända profiler för ingress, namn, segmentering och anslutning. Börja med ett fåtal vanliga tjänstetyper och mät om ledtid, risk och supportarbete verkligen minskar.

Det är ofta klokt att genomföra vissa åtgärder i spår A i samma förändring som spår B, men utan att göra en plattformssatsning till ett villkor för grundläggande säkerhet.

### Ett enkelt diagnostiskt prov

Välj två vanliga förändringar – till exempel att lägga till en tillåten tjänstförbindelse och att avveckla en befintlig. Följ dem från begäran till verifierat slutläge. Registrera väntetid, faktiskt arbete, antal inblandade team, oklara beslut och eventuella undantag. Gör därefter ett riskanpassat prov av en otillåten anslutning. Om den tekniska kontrollen fallerar är det ett **grundproblem i generation 2**. Om kontrollen fungerar men varje identiskt normalfall kräver samma långa manuella kedja är det i stället ett **möjligt motiv för generation 3**. Dessa två slutsatser kan gälla samtidigt.

## Övergången 2 → 3 – från manuella nätbeställningar till förvaltade erbjudanden

När normalfallen återkommer i stor skala blir manuella godkännanden och konfigurationer ett hinder även om varje nätverksbeslut är tekniskt korrekt. Då kan plattformsorienteringen vara motiverad: ett utvecklingsteam deklarerar exempelvis att en tjänst behöver exponeras via en godkänd ingressprofil och nå en viss databastjänst. Plattformen kontrollerar begäran mot policy, tilldelar eller ändrar nätresurser och följer deras livscykel.

Den stora vinsten uppstår först när standardfallen återkommer tillräckligt ofta och riskminskningen eller den sparade arbetsinsatsen motiverar kostnaden för en förvaltad tjänst. Detta kräver mer än ett självbetjäningsformulär. Bakom gränssnittet måste det finnas automatiserade nätprofiler, fungerande identitets- och behörighetskontroll, policyvalidering, spårbar förändring och tydligt produktansvar. Standardfallen ska vara tillräckligt enkla för att teamen ska välja dem, medan högriskundantag fortfarande kan kräva manuell prövning. När en tjänst avvecklas ska dess nätvägar kunna tas bort kontrollerat.

Service mesh, programvarudefinierade nät och policy-as-code kan bidra, men är **inte obligatoriska teknikval** för generation 3. Ett service mesh kan dessutom tillföra betydande drift- och felsökningskomplexitet och behöver motiveras av faktiska behov. Ett service mesh kan vara motiverat där behov av tjänst-till-tjänst-kryptering, trafikpolicy och observerbarhet återkommer i stor skala. Det är inte en ersättning för fysisk konnektivitet, identitetsansvar eller applikationens egen auktorisation. En enklare nätprofil kan vara bättre för mindre eller stabila system.

**Beredskap för övergången** finns när det går att namnge återkommande konsumentbehov, standardisera ett begränsat antal trafikprofiler, definiera vilka team som äger deklarationerna och visa hur undantag, säkerhetsuppdateringar och avveckling ska hanteras. Om nätverksinventeringen är opålitlig, rättigheterna oklara och varje specialfall kräver en unik konstruktion bör detta hanteras först eller parallellt med en snävt avgränsad pilot.

## Generation 3 – nätverket som en användbar plattformstjänst

En fungerande nätverksplattform levererar inte bara brandväggsregler. Den erbjuder standardiserade kontrakt för konnektivitet: vilka miljöer som får anslutas, vilka säkerhets- och tillgänglighetsprofiler som gäller och vad ett team behöver deklarera för att få en fungerande tjänst. Nätverksprofiler kan integreras med infrastruktur som kod och applikationsleverans så att skapande, ändring och borttagning sker samordnat.

Plattformsteamet äger profilerna, dokumentationen, tjänstekvaliteten och deras tekniska livscykel, inklusive ändring, versionsskiften, felhantering och avveckling. Applikationsteamen äger vilka beroenden de deklarerar och hur applikationen fungerar vid nätstörningar. Säkerhetsteamet ansvarar för policyprinciper och undantag, inte för att manuellt utföra varje standardbeställning.

### Vanliga fallgropar och fungerande stöd

En portal kan se modern ut men fortfarande skicka varje begäran till en administratör. Automatisering kan också skapa nya risker om gamla trafikregler aldrig städas bort, om policyer används utan test eller om plattformsteamet inte erbjuder begriplig felsökning. En annan fallgrop är att en enda nätprofil tvingas på olika behov: fältanslutningar, internetexponering och intern tjänstkommunikation behöver inte ha samma tekniska lösning.

En fungerande förmåga märks när ett team kan etablera och avveckla en godkänd standardrelation på ett kontrollerat och dokumenterat sätt, när policyfel ger användbar återkoppling och när central support inte måste utföra rutinuppgifter. Stickprov bör kontrollera både anslutning och nekad trafik, ändring av befintliga flöden, återställning efter felaktig policyändring samt att avveckling verkligen städar upp regler och namnposter. Följ även andelen normalfall som klaras utan manuellt specialistarbete, ledtider, undantagens livslängd och påverkan på incidenter.

### När tekniken eller plattformen bör ifrågasättas

Varningssignaler är att det saknas stabilt API eller deklarativt gränssnitt, att nätpolicyn inte kan testas före införande, att automatisering kräver osäkra privilegier eller att produkten inte klarar nödvändig isolering mellan konsumenter. Höga kostnader för varje ny tenant eller isolerad miljö kan också vara en begränsning. Men ett plattformsproblem kan lika gärna bero på att erbjudandet inte är paketerat, att tjänsteansvaret är otydligt eller att konsumenterna saknar dokumentation. Utvärdera därför **behåll, komplettera, förändra användning/ansvar eller ersätt** innan investering beslutas.

## Övergången 3 → 4 – fler skapare, mer varierad risk

När även verksamhetsnära team kan skapa egna applikationer och automatiserade arbetsflöden förändras efterfrågan på nätverket. Nya lösningar kan vara kortlivade, skapas snabbt och behöva ansluta till både interna resurser och externa AI-tjänster. Då ökar värdet av policybundna standardprofiler, tydligt ägarskap, begränsad utgående trafik (*egress*) och automatisk avveckling.

Det avgörande är inte att ge AI-agenter ett eget nätverk som i sig gör dem säkra. En agent kan ha teknisk kommunikationsförmåga utan att vara behörig att läsa information eller utföra en handling. Agentens identitet, verktygsmandat och dataåtkomst behöver kontrolleras i angränsande förmågor. Nätverket bör däremot kunna begränsa vilka destinationer och typer av trafik en lösning får använda och göra avvikelser synliga.

**Beredskap** innebär att godkända profiler kan nyttjas utan omfattande specialarbete, att ansvariga personer eller team går att identifiera, att kostnader och anslutningar går att följa och att en lösning kan isoleras utan att okontrollerat påverka andra system.

## Generation 4 – riskstyrd anslutning för verksamhetsnära lösningar

Förmågan behöver kunna hantera fler, ofta mer tillfälliga konsumenter. En låg-risklösning som använder en godkänd offentlig tjänst kan få en standardprofil, medan en lösning som ska överföra känslig information till en extern mottagare behöver striktare kontroller och ibland särskilt godkännande. Vissa äldre eller verksamhetskritiska system kan fortsatt vara stabila och manuellt förvaltade – generationsmodellen kräver inte att de byggs om.

**Indikatorer på tillräckligt stöd** är att en ny lösning kan få rätt anslutningsprofil utan att användaren behöver förstå alla nätverksdetaljer, att definierade otillåtna destinationer blockeras inom kontrollens tekniska räckvidd, att tilldelade anslutningar och kostnader kan härledas till en ansvarig och att borttagning av lösningen avvecklar dess nätåtkomst. Det bör också gå att pausa ett problematiskt flöde och utreda vilka tekniska kommunikationsvägar som använts.

**Fallgropar** är att använda nätfilter som substitut för faktisk åtkomstkontroll, att ge alla AI-arbetsflöden samma vida utgående internetåtkomst, att förlita sig på domänfilter som om de ensamma säkert identifierade mottagaren eller att tro att stopp av trafik återkallar externa handlingar som redan genomförts. Avstängning kan minska fortsatt risk, men redan utsända data eller meddelanden kan inte automatiskt tas tillbaka.

**Indikatorer på olämpliga teknik- och plattformsval** är att lösningar inte kan tilldelas åtskilda nätprofiler, att kortlivade anslutningar inte kan avvecklas automatiskt, att policyundantag inte är spårbara eller att nödvändig destination- och trafikbegränsning inte kan uttryckas utan breda undantag. Pröva först befintliga funktioner, nätarkitektur och identitetsintegration innan ett teknikbyte rekommenderas.

## Ett återkommande exempel – ett ärendehanteringsstöd

Ett ärendehanteringsstöd som tidigare var en monolit består nu av webbgränssnitt, API, handläggningstjänst, databas och en anslutning till en extern myndighet. I generation 2 går det att dokumentera varje trafikrelation, identifiera vem som äger den och prova vad som händer när en länk eller tjänst faller bort. Det minskar risken för att ett ärendeflöde slutar fungera trots att alla servrar ser friska ut.

Om fem andra team sedan behöver samma slags ingress, DNS-registrering och skyddade databaskommunikation kan dessa behov paketeras som standardprofiler i generation 3. Teamen deklarerar sina beroenden; plattformen kontrollerar och etablerar de tillåtna vägarna. Särskilda myndighetsanslutningar kan fortfarande hanteras med strängare prövning.

I generation 4 kan en handläggare få stöd av en AI-assistent som söker i godkända informationskällor. Assistenten får då inte en generell väg till alla databaser eller internetdestinationer. Nätprofil, teknisk identitet och verksamhetsbehörighet samverkar, men är inte samma sak.

## Praktisk bedömning – vad bör organisationen göra först?

Börja med en viktig tjänstekedja och undersök vilka tekniska kommunikationsrelationer som verkligen krävs. Kontrollera trafikregler, namnuppslagning, extern anslutning, fördröjning och återställningsvägar. Välj därefter ett återkommande standardfall och mät hur lång tid det tar att skapa, ändra och avveckla konnektiviteten. Fråga om fördröjningen beror på teknikens begränsningar, ofullständig information, oklara mandat eller rimliga säkerhetsbeslut.

Om grundläggande kontroll och spårbarhet saknas behöver dessa brister åtgärdas. Det kan ske före eller inom en begränsad plattformssatsning, men de får inte lämnas olösta i väntan på ett generationsskifte. Om grunderna fungerar men samma beställningar återkommer i stor skala kan en självbetjänad nätprofil vara nästa ekonomiskt och tekniskt rimliga steg. Om organisationen samtidigt får fler verksamhetsutvecklade lösningar behöver den bygga in riskstyrning och livscykelhantering i dessa profiler. Det finns ingen anledning att tvinga alla nätverksmiljöer till samma lösning.

## Teknisk orientering – vilka plattformstjänster stöder förmågan?

Källmodellen beskriver tolv tjänster inom åtta konceptuella plattformar. Alla ska inte införas av varje organisation. Grundläggande anslutbarhet, DNS/IPAM, lämplig nätavgränsning och relevanta trafikvägar är vanliga behov; de kan ibland tillhandahållas av en extern drift- eller molnleverantör i stället för en egen central plattform. Lastbalansering och ingress blir aktuella för exponerade tjänster. LAN/WLAN och WAN beror på arbetsplatser och geografisk utbredning. Extern systemanslutning, mediedistribution och verksamhetskritisk fältkommunikation är tydligt behovsstyrda. Webb- och API-skydd har ett delat beroende med cybersäkerhetsförmågan; det är inte samma sak som API Management eller applikationsauktorisation.

| Plattformstjänst | När den främst blir relevant |
|---|---|
| PLS-054 DNS och IPAM | Namn, adresser och ändringsbarhet för nätresurser |
| PLS-058 Nätsegmentering och trafikpolicy | Avgränsa tillåtna kommunikationsrelationer |
| PLS-072 Datacenter- och plattformskonnektivitet | Trafik inom och mellan plattformsmiljöer |
| PLS-057 Lastbalansering och ingress | Exponera och fördela inkommande tjänstetrafik |
| PLS-073 Internet- och edgeanslutning | Säker trafik till och från internet |
| PLS-056 Fjärråtkomst | Distansarbete och kontrollerad fjärradministration |
| PLS-055 LAN och trådlöst nätverk | Arbetsplatser och lokala enheter |
| PLS-071 WAN och platskonnektivitet | Organisationer med flera platser |
| PLS-079 Säker extern system- och myndighetsanslutning | Utbyte med externa parter och myndigheter |
| PLS-087 Webb- och API-skydd | Skydda exponerade webb- och API-tjänster |
| PLS-089 Mediedistribution och streaming | Tjänster med särskilda medie- och distributionskrav |
| PLS-076 Verksamhetskritisk fältkommunikation | Fältverksamhet med stränga tillgänglighetskrav |

## Källor och avgränsningar

**Grundmodell:** *Från systemdrift till digital självständighet*, *Förmågeöversikt – tekniska IT-förmågor* (CAP-IT-13) samt *Plattformsöversikt – konceptuella plattformar* (modellbaseline v1.1). Namn, ID:n och direkta förmågekopplingar följer dessa. Bokens generationstolkningar, indikatorer, riskavvägningar och föreslagna kontroller är analytiska bedömningar, inte obligatoriska krav i plattformskatalogen.

**Kompletterande referenser (principstöd, inte bevis för den egna generationsindelningen):** NIST SP 800-207, *Zero Trust Architecture* (2020), https://csrc.nist.gov/pubs/sp/800/207/final; NIST SP 800-204A, *Building Secure Microservices-based Applications Using Service-Mesh Architecture* (2020), https://csrc.nist.gov/pubs/sp/800/204/a/final; CNCF, *Platform engineering maturity: From toolchain to self-service* (2026), https://www.cncf.io/blog/2026/09/01/platform-engineering-maturity-from-toolchain-to-self-service/.

Dessa referensramverk är inte identiska med generationsmodellen och ska inte läsas som krav på specifika produkter. Generation 4 är en framåtblickande bedömning av möjliga behov, inte ett påstående om ett universellt etablerat driftmönster.
