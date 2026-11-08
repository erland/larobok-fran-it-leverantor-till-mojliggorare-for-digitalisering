# Slutanvändarmiljö och klientplattform

En digital tjänst kan fungera utmärkt i sina servrar och ändå vara otillgänglig för den som ska använda den. En uppdatering kan slå ut ett klientprogram, en fältmedarbetare kan sakna uppkoppling och en tidigare konsult kan ha kvar en aktiv virtuell arbetsplats. Förmågan *Slutanvändarmiljö och klientplattform* erbjuder därför säkra, användbara och förvaltade tekniska arbetsmiljöer där människor når organisationens digitala tjänster. Det handlar om hela klientens livscykel, inte bara om att dela ut datorer.

## Vad den gemensamma förmågan behöver erbjuda

### Enhetshantering och klientprofiler

Gemensamma tjänster för enhetshantering, ofta kallade UEM eller MDM, kan registrera och konfigurera datorer, mobiler och surfplattor, följa operativsystemsversioner och kryptering samt ge information om efterlevnad av fastställda klientkrav. En tjänsteprofil behöver beskriva vad som gäller för exempelvis en organisationsägd dator, en delad terminal, en fältsurfplatta eller en privatägd telefon. Alla kan inte och bör inte hanteras på samma sätt.

För privatägda enheter kan organisationen ibland hantera en arbetsprofil eller vissa arbetsappar utan att administrera hela telefonen. Det tekniska stödet och integritetshänsynen begränsar vad som är möjligt. På delade terminaler behöver användarbyten provas så att dokument, åtkomsttoken och webbsessioner inte följer med till nästa person. Specialutrustning kan kräva särskilda uppgraderings- och skyddsprofiler när vanliga klientagenter inte stöds.

### Klientprogram, uppdateringar och virtuella arbetsplatser

Applikationsdistribution omfattar paketering, kontrollerad installation, versionsuppdateringar och utfasning av program som körs på användarens enhet. Det är inte samma sak som att bygga och leverera en webbtjänst. Utrullning till begränsade pilotgrupper, möjlighet att stoppa en felaktig uppdatering och prövade återhämtningsvägar behövs när en klientuppdatering kan störa arbetet. En nedgradering är inte alltid säker om dataformat eller beroenden redan ändrats.

Virtuella skrivbord och förvaltade fjärrarbetsplatser kan vara användbara för särskilda klientprogram, tidsbegränsade uppdrag och miljöer där lokal datalagring behöver begränsas. De är inte nödvändiga för varje webbaserad tjänst och ger inte automatiskt fullständig isolering: användare kan fortfarande ha möjlighet att kopiera, skriva ut eller exportera information. Värdet behöver bedömas utifrån den verkliga arbetsuppgiften.

### Skydd, åtkomst och fungerande användning

Klientplattformen ska se till att relevanta skyddskontroller är installerade, aktiva och fungerar på de enheter som omfattas. Den behöver erbjuda hanterbara profiler och rapportera när skydd eller uppdateringar fallerar. Hotanalys och säkerhetsincidenter hanteras tillsammans med *Cybersäkerhet och tekniskt skydd*. Autentisering, konton och sessioner hör till *Identitet och tillit*; en klient som uppfyller enhetspolicyn ger inte i sig användaren rätt att öppna ett visst ärende.

En förlorad mobil visar skillnaden mellan teknisk åtgärd och faktiskt resultat. Ett begärt fjärrraderingskommando kan utebli om telefonen aldrig ansluts igen. Organisationen kan därför behöva stoppa åtkomst separat och bedöma vilka uppgifter som kan finnas kvar offline. På motsvarande sätt behöver en avslutad konsults virtuella arbetsplats, sessioner och temporära filer hanteras som en sammanhängande avslutsprocess.

Klienttjänsten behöver också mäta mer än installationsgrad: kan medarbetaren slutföra sitt arbete efter en uppdatering, även med hjälpmedel, särskild kringutrustning eller perioder utan uppkoppling? Gränssnittets utformning och tillgänglighet hör till *Interaktion, presentation och kanaler*, men klientplattformen måste ge fungerande webbläsare, operativsystem och hjälpmedelsstöd.

## Generation 3 – en förvaltad klienttjänst som inte kräver handpåläggning

I generation 2 kan många typer av enheter och klientprogram finnas samtidigt som nya installationer, programuppdateringar och åtkomstprofiler fortfarande kräver centrala specialistärenden. Grundläggande inventering, säkerhetsuppdateringar och enhetsskydd måste fungera redan här. En ny portal är inte en lösning om samma manuella arbete fortfarande ligger bakom den.

I generation 3 erbjuder klientplattformsteamet standardiserade profiler och automatiserade tjänster för tilldelning, uppdatering, felsökning och avveckling. Behöriga användare eller stödfunktioner kan få en lämplig arbetsmiljö utan en specialbeställning för varje normalfall. Professionella utvecklingsteam kan distribuera och uppdatera sina klientprogram genom dokumenterade, godkända distributionsvägar utan att klientdriften manuellt paketerar varje version. Plattformsteamet förvaltar de gemensamma klienttjänsterna och deras skydd; produktteamet ansvarar för att den egna applikationen fungerar på stödda klienter.

Självbetjäningen kräver testprofiler, representativa enheter, pilotutrullning, tydliga ansvar och fungerande reservvägar. Om en felaktig central policy låser ute användarna måste det finnas en prövad möjlighet att återfå kontrollen. Inte heller behöver varje organisation köpa alla tänkbara klientplattformstjänster: behovet av virtuell arbetsplats eller omfattande mobilhantering styrs av klienter, användning och risk.

## Generation 4 – arbetsmiljön stödjer verksamhetens eget skapande

När verksamhetsmedarbetare själva skapar formulär, appar, automationer och AI-assistenter behöver dessa kunna användas i godkända klientmiljöer. En medarbetare som skapar en enkel intern app ska kunna prova den på sin vanliga, förvaltade arbetsdator och sedan göra den tillgänglig för kollegor via en godkänd kanal, utan separat beställning av klientinstallation. Om en app exempelvis behöver användas på fältsurfplattor ska medarbetaren kunna välja en godkänd användningsprofil och prova hur den fungerar vid begränsad uppkoppling; klientplattformen tillhandahåller och säkrar enheterna och distributionen, inte appens offlinefunktion. Andra lösningar kan behöva en hanterad mobilapp eller en begränsad virtuell arbetsplats. Klientförmågan ska göra lämpliga åtkomst- och distributionsprofiler tillgängliga, inte besluta hur appen byggs.

För verksamhetsskapade appar behöver klientplattformen också skilja mellan olika sätt att köra kod. En webbapp eller PWA använder normalt webbläsarens avgränsade rättigheter, en low-code-app körs inom sin förvaltade plattform och ett lokalt installerat program kan behöva särskild distributionskontroll och begränsade enhetsrättigheter. Att en app skapats med AI innebär inte att genererad kod fritt bör få köras med användarens fulla lokala behörigheter. Även webbappar behöver säkerhetsprövning; webbläsarens isolering eliminerar inte risker för exempelvis informationsläckage eller olämpliga anrop.

För AI-assistenter kan klientplattformen begränsa lokal filåtkomst och skydda arbetsprofiler och sessioner. Verksamhetsmandat prövas däremot av de tjänster som äger informationen. Vid avveckling behöver klientdistribution, lokala data och sessioner hanteras; redan exporterade kopior kan inte automatiskt återkallas.

För generation 4 blir målet därför inte att varje medarbetare ska administrera sin enhet eller sina appar. Målet är en säker, begriplig digital arbetsplats där godkända verksamhetsskapade lösningar kan provas, användas och förändras utan onödiga klienttekniska hinder. Den generella skapande- och publiceringsvägen erbjuds genom *Utveckling och teknisk leverans*, medan klientplattformen ansvarar för den tekniska miljö där användaren faktiskt möter lösningen.
