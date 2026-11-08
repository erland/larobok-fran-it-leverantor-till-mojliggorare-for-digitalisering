# Fyra generationer av IT – två förändringar i synsätt

Generationerna beskriver inte fyra teknikpaket som varje organisation måste införa i ordning. De beskriver hur IT:s uppdrag kan förändras: från att leverera och drifta enskilda system till att möjliggöra självständiga utvecklingsteam – och därefter ge verksamheten större möjlighet att själv skapa digitala förbättringar. Olika generationer kan finnas samtidigt i samma organisation.

## Generation 1 – det sammanhållna IT-stödet

I generation 1 byggs ett IT-stöd ofta som en relativt sammanhållen enhet: användargränssnitt, verksamhetslogik och datalagring hör nära ihop. Beställning, utveckling och drift organiseras kring ett system eller en större applikationsmiljö. Driftorganisationen kan skapa en robust helhet med tydliga servrar, databaser, nätverksgränser och driftprocedurer.

Det arbetssättet hade styrkor. Relativt få systemgränser gjorde beroenden överblickbara, ansvaret kunde vara tydligt och förändringarna var ofta hanterliga inom en gemensam livscykel. Samtidigt kunde varje nytt IT-stöd bli en egen teknisk ö med egna anpassningar. Stora förändringar krävde omfattande samordning inom systemet, och beroendet av enskilda leverantörer eller specialister kunde bli stort.

Det är viktigt att inte läsa denna beskrivning som kritik av monolitiska system i sig. Ett välavgränsat, sammanhållet system kan fortfarande vara ett bra val. Generationen handlar här främst om hur IT-leveransen organiseras och hur många återanvändbara förutsättningar som finns utanför det enskilda systemet.

## Generation 2 – när antalet tjänster växer snabbare än arbetssätten förändras

I generation 2 har många IT-stöd delats upp i mindre applikationer, tjänster och integrationsflöden. En del förändringar går snabbare, eftersom olika team kan utveckla olika delar oberoende av varandra. Det kan också bli lättare att använda olika tekniker för olika behov.

Men fler delar innebär fler samverkanspunkter. En förändring i en verksamhetsprocess kan behöva koordineras över flera team och system. Teknikgränserna blir ibland fler än verksamhetsgränserna. Organisationen behöver förstå API-kontrakt, informationsägarskap, identiteter, felkedjor och driftansvar mellan tjänster.

Många organisationer behåller samtidigt en uppdelning där utvecklingsteam levererar kod men måste lämna över driftsättning, felsökning och ändringar i produktionsmiljön till andra funktioner. En ny tjänst kan kräva separata beställningar av körmiljö, databas och nätåtkomst; efter driftsättning är det oklart vem som äger felet när ett verksamhetsflöde stannar. Gemensam infrastruktur kan minska kostnader men ändrar inte i sig detta fragmenterade livscykelansvar.

En organisation kan alltså ha moderna mikrotjänster och ändå arbeta som en traditionell IT-leverantör. Det är just den diskrepansen som gör generation 2 till en viktig utgångspunkt för resten av boken.

## Generation 3 – utvecklingsteam kan äga sina tjänsters hela livscykel

Den första stora förflyttningen är inte att göra tekniska beställningar snabbare. Den är att ge utvecklings- och produktteam förutsättningar att själva ta ansvar för sina digitala tjänster från driftsättning till avveckling. Teamet ska kunna släppa nya versioner, övervaka verksamhetsfunktion och tekniskt beteende, felsöka incidenter, uppdatera beroenden, skala och till sist avveckla tjänsten – utan att varje normal åtgärd måste lämnas över till en annan organisatorisk funktion.

Det förutsätter inte att varje utvecklare blir nätverks-, databas- eller säkerhetsspecialist. Tvärtom bygger modellen på att gemensamma plattformsteam erbjuder säkra, robusta och väldokumenterade tekniska förutsättningar som produktteam kan använda direkt. Produktteamet ansvarar för sin tjänst; plattformsteamet ansvarar för den gemensamma plattformstjänst som gör arbetet möjligt. Ansvarsgränsen måste vara dokumenterad, prövad vid incidenter och anpassad till tjänstens risk. [K002]

### Livscykelansvar i praktiken

Ta en tjänst som visar ärendestatus. Produktteamet behöver kunna leverera nya versioner, läsa relevant telemetri, felsöka felaktiga uppdateringar och vid behov återställa tjänsten. När den avvecklas måste även anslutningar och behörigheter stängas och information hanteras enligt gällande regler. Plattformen ska ge teamet godkända vägar för dessa moment, utan att ge obegränsad infrastrukturåtkomst. För riskfyllda åtgärder finns särskild prövning.

### Driftorganisation och plattformsteam – olika uppdrag

En driftsorganisation i generation 2 kan redan förvalta gemensamma databaser, servrar och containermiljöer med hög säkerhet och tillgänglighet. Skillnaden ligger därför inte i tekniken eller kompetensnivån, utan i vem som kan göra vad.

Driftorganisationens tjänst är ofta att driva miljön och utföra tekniska åtgärder åt andra. Plattformsteamet i generation 3 förvaltar i stället en intern produkt som utvecklingsteamen kan använda och driva sina egna tjänster på. Det innebär dokumenterade gränssnitt, självbetjäning, stödda versioner, förutsägbara uppgraderingar och verktyg för felsökning. Plattformsteamet följer både driftsäkerheten och hur väl andra team kan arbeta självständigt.

Vid ett applikationsfel kan produktteamet normalt själv använda loggar och mätvärden och genomföra tillåtna åtgärder. Vid ett fel i den gemensamma plattformen ansvarar plattformsteamet; vid gränsfall krävs samarbete. Driftkompetensen försvinner inte – den används för att göra många andra team självständiga utan att robustheten går förlorad.

### Säkerhet och robusthet byggs in i arbetssättet

Fördefinierade behörigheter, spårbara leveranser, godkända anslutningar och testad återställning ska vara en naturlig del av den väg teamen använder. Produktteamet ansvarar för applikationens beteende och verksamhetsnytta; plattformsteamet för den gemensamma tjänstens funktion, uppgraderingar och driftsäkerhet. Informationsägarskap och verksamhetsbeslut ligger där de hör hemma och behöver också vara uttryckligt fördelade.

En plattform måste förvaltas som en produkt, med användare, prioriteringar, stöd och livscykel. En självbetjäningsportal som bara vidarebefordrar manuella beställningar är inte tillräcklig.

### Vad visar att förflyttningen fungerar?

Det avgörande är inte antalet införda plattformar. Kan produktteamet driftsätta, övervaka, felsöka, uppdatera och avveckla sin tjänst med bibehållna kontroller? Kan plattformen själv uppgraderas utan ett separat projekt för varje användande team? Det är de förmågorna, inte tekniken i sig, som visar skillnaden.

## Generation 4 – verksamheten får större digital handlingskraft

I stora organisationer finns fler idéer till digitala förbättringar än utvecklingsteamen har möjlighet att genomföra. Många är lokala: förenkla sammanställningar, jämföra underlag eller stödja en särskild arbetsrutin. Var för sig är de för små för ett traditionellt IT-projekt, men tillsammans kan de frigöra betydande tid och förbättra kvaliteten.

De som utför arbetet känner dessutom ofta behoven bäst. När de själva kan pröva en idé blir återkopplingen snabbare och vägen kortare mellan problem och användbar lösning. Generation 4 handlar om denna breddade handlingskraft, inte om AI för AI:s skull.

I generation 3 blir professionella utvecklingsteam mindre beroende av andra IT-funktioner. I generation 4 blir verksamheten mindre beroende av att varje digital förbättring måste genomföras av professionella utvecklare. Det förutsätter inte AI. En grupp kan till exempel själv bygga ett formulär för kompletteringsuppgifter, lägga till en påminnelse i ett enkelt ärendeflöde och prova villkor för när ärendet ska skickas vidare. Med en godkänd skapandemiljö kan gruppen testa utan att ändra riktiga ärenden, publicera för en avgränsad grupp och följa upp användningen. Ägaren av processen och reglerna behöver fortfarande godkänna innehållet och eventuella beslut. AI-assistenter, AI-agenter och AI-stödd apputveckling ger därutöver andra vägar till samma slags självständighet.

### AI-assistenter: medarbetaren skapar sitt eget stöd

En medarbetare som ofta behöver tolka instruktioner, jämföra dokument eller sammanställa ärendeunderlag behöver inte nöja sig med en allmän AI-assistent. Redan i dag går det att skapa specialiserade assistenter genom att kombinera egna instruktioner, godkända kunskapskällor och återanvändbara funktioner, till exempel *skills* eller anslutningar till andra verktyg. Verksamheten kan därmed själv utforma, prova och förbättra ett stöd nära det dagliga arbetet, utan att beställa ett separat IT-projekt för varje behov.

En assistent kan exempelvis hjälpa en handläggargrupp att hitta relevanta regler, jämföra underlag och skriva förslag som medarbetarna granskar. Nyttan ligger både i snabbare arbete och i att de som kan verksamheten bäst kan forma hjälpmedlet. Men ett välformulerat svar är inte nödvändigtvis korrekt: källor kan vara inaktuella och viktig information kan saknas. Därför behövs godkänd informationsåtkomst, möjlighet att kontrollera källorna och tydligt ansvar för hur resultatet används.

IT:s uppgift blir att erbjuda säkra AI-tjänster och gemensamma byggstenar som verksamheten kan använda själv: identitet, behörigheter, informationsanslutningar och uppföljning. En personlig assistent med begränsad information kan ges stor frihet att experimentera; en assistent som delas brett eller används för känsliga uppgifter kräver mer prövning och förvaltning. När assistenten också får utföra handlingar i andra system växer den in i nästa möjlighet: AI-agenter.

### AI-agenter: från förslag till begränsade handlingar

En AI-agent skiljer sig från en ren frågeassistent genom att den kan använda verktyg och genomföra steg i ett arbetsflöde. En agent skulle exempelvis kunna kontrollera om en ansökan innehåller alla nödvändiga bilagor, hämta kompletterande fakta från godkända källor och föreslå nästa åtgärd. Inom ett begränsat uppdrag skulle den även kunna skapa en arbetsuppgift eller skicka en standardiserad begäran om komplettering.

Här förändras riskbilden. Ett felaktigt svar kan vilseleda en människa; ett felaktigt verktygsanrop kan ändra information eller sätta i gång en verklig process. Därför är det inte tillräckligt att instruera agenten att bara göra sådant den har tillåtelse till. Begränsningen måste verkställas i den tekniska miljö som agenten använder.

Organisationen behöver kunna svara på vem som gav agenten uppdraget, vilken information den får läsa, vilka verktyg den får anropa, vilka belopps-, tids- eller åtgärdsgränser som gäller och vilka steg som kräver mänskligt godkännande. Behörighet bör prövas vid betrodda kontrollpunkter, inte enbart utifrån agentens egen beskrivning av sitt mandat. Resultatet måste kunna följas och utvärderas.

Det måste också finnas sätt att pausa eller stoppa agentens fortsatta arbete. Men att dra tillbaka ett mandat kan inte alltid upphäva sådant som redan har skickats till andra system, kölagts eller utförts. Externa handlingar kan kräva särskild hantering eller kompenserande processer, och vissa konsekvenser är inte återställbara.

Med dessa gränser kan verksamheten själv förbättra återkommande arbetsflöden som tidigare skulle ha krävt ett nytt utvecklingsuppdrag, medan IT tillhandahåller säkra integrationsmöjligheter och kontroller för genomförandet. Utan dessa gränser riskerar automation att göra fel snabbare snarare än att skapa värde.

### AI-stödd applikationsutveckling: fler kan skapa lösningar

Den tredje möjligheten gäller själva utvecklingen. Genom att beskriva önskat beteende i naturligt språk, pröva resultat och iterera med en kodgenererande AI kan en verksamhetsnära medarbetare skapa en prototyp eller ibland en användbar applikation utan samma omfattning av traditionell programmering som tidigare. Detta sätt att arbeta kallas ofta *vibe programming* eller *vibe coding*.

Begreppet fångar en viktig förändring: tröskeln för att ta fram programvara kan sjunka kraftigt. En medarbetare som känner arbetsprocessen väl kan själv prova en idé, utforma ett enkelt gränssnitt och upptäcka vilka krav som verkligen spelar roll. Det kan minska avståndet mellan verksamhetsproblem och fungerande lösning. Många små behov som tidigare aldrig nådde högt nog i en central utvecklingskö kan därmed prövas till låg kostnad, utan att professionella utvecklare behöver bygga varje första version.

Men förmågan att generera kod är inte samma sak som förmågan att ta ansvar för en produkt. En applikation kan fungera väl i ett demonstrationsfall och ändå innehålla säkerhetsbrister, felaktiga beräkningar, otillräcklig tillgänglighet eller antaganden som faller när flera användare arbetar samtidigt. Koden kan dessutom innehålla beroenden som måste uppdateras och data som måste hanteras under många år.

Det är därför hjälpsamt att skilja mellan tre nivåer av lösningar:

1. Personligt hjälpmedel eller prototyp. En medarbetare prövar ett arbetssätt med begränsad information, begränsad spridning och små konsekvenser om lösningen slutar fungera. Snabb återkoppling och möjlighet att radera experimentet är centralt.
2. Delad verksamhetslösning. Ett team eller en avdelning börjar förlita sig på applikationen. Då behövs ägare, versionshantering, tester, stöd för användare, kontroll av informationsåtkomst och en tydlig plan för underhåll.
3. Verksamhetskritisk eller rättsligt betydelsefull lösning. Om applikationen påverkar rättigheter, stora värden, säkerhet eller grunduppdraget krävs en annan nivå av granskning, driftsäkerhet och långsiktigt ansvar. Professionell utveckling kan vara det lämpliga valet, även om idén först skapades med AI-stöd.

### Från experiment till något andra förlitar sig på

När ett experiment sprids behövs fler kontroller. En AI-assistent ska utvärderas för felaktiga svar, en agent för konsekvenserna av sina handlingar och en AI-genererad applikation för kod och säkerhet. En lokal lösning som blir verksamhetskritisk kan behöva övergå till ett professionellt produktteam. Styrningen ska följa konsekvenserna av ett fel, inte vara lika tung för varje experiment.

### IT:s uppdrag när fler kan skapa själva

IT behöver erbjuda godkänd AI-åtkomst, säkra informationsgränssnitt, tydliga identiteter, lättanvända testmiljöer och vägar till införande och avveckling. Verktygen måste vara begripliga även för personer som inte är utvecklare. Professionella produktteam behövs fortsatt för kärnsystem, känsliga beslut och andra lösningar där kraven är höga.

Utmaningen är att ge verksamheten större frihet utan att skapa hundratals osynliga och oförvaltade lösningar. IT:s uppdrag blir att göra säkra förbättringar möjliga i stor skala, samtidigt som verksamheten behåller ansvar för sina behov och resultat. Hur detta förändrar arbetssätt, roller och kompetens återkommer boken till i avslutningskapitlet.

## Samma behov, olika handlingsutrymme

Ta en önskan om bättre stöd för att upptäcka ofullständiga ärendeunderlag. I generation 1 ändras det sammanhållna systemet; i generation 2 behöver flera tekniska tjänster samordnas. I generation 3 kan ett produktteam genomföra och driva förändringen med hjälp av gemensamma plattformar. I generation 4 kan verksamheten dessutom själv prova ett begränsat AI-stöd eller ett mindre hjälpverktyg innan en större lösning utvecklas. Kärnsystemet behöver inte bytas ut för att sättet att skapa förbättringar ska förändras.

## Ingen generation passar överallt

Ett sammanhållet system kan vara rätt val, och riskfyllda ändringar kan fortsatt kräva manuell granskning. Generation 4 är heller inte ett etablerat slutläge: AI förändras snabbt och organisationernas möjligheter skiljer sig åt. Poängen är inte att allt ska bli självbetjänat, utan att förmåga och ansvar placeras där förändringar kan genomföras säkert och ge nytta.

Nästa kapitel visar vilka gemensamma IT-förmågor som behöver finnas för att detta ska fungera – oavsett vilka tekniska produkter organisationen väljer.
