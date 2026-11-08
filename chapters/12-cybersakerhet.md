# Cybersäkerhet och tekniskt skydd

När IT-stöd består av många tjänster räcker det inte att skydda servrar och nätverksgränser. Organisationen behöver kunna upptäcka vilka applikationer och beroenden som är exponerade, begränsa angrepp och hantera säkerhetsbrister under hela tjänstens livslängd. Förmågan *Cybersäkerhet och tekniskt skydd* ska därför erbjuda gemensamma skydds-, kontroll- och detektionstjänster som fungerar i flera tekniska miljöer. Den ersätter inte verksamhetens riskansvar eller produktteamens ansvar att åtgärda brister.

## Vad det gemensamma erbjudandet behöver omfatta

### Skydd av arbetslaster, applikationer och information

Det behövs anpassningsbara skydd för klienter, servrar, containrar, applikationer och externa gränssnitt. Det kan innefatta skydd mot skadlig kod och intrång, säker konfiguration, granskning av skadligt innehåll i applikationsanrop och skydd mot otillåten informationsöverföring. Det är andra kontroller än nätverksförmågans segmentering och tekniska trafikregler. Kryptering och säkra kryptografiska funktioner behöver vara tillgängliga där skyddsvärde och tillämpning motiverar det. Alla tjänster behöver däremot inte en separat webbapplikationsbrandvägg, DLP-lösning eller hårdvarubaserad nyckelhantering.

Förmågan behöver kunna erbjuda godkända skyddsprofiler utifrån exempelvis informationens känslighet, exponering och verksamhetskonsekvens. En profil ska ha tydligt innehåll, kända begränsningar och en ansvarig för uppdatering och undantag. Nätsegmentering och grundläggande konnektivitet erbjuds av *Nätverk och konnektivitet*, medan *Identitet och tillit* tillhandahåller identiteter, tillitsrelationer och behörighetsmekanismer.

### Tillgångsöverblick, sårbarheter och exponering

Organisationen behöver en tillförlitlig bild av tjänster, programvaruberoenden, konfigurationer och exponerade gränssnitt. Gemensamma tjänster för inventering, sårbarhetsskanning och exponeringsanalys ska kunna koppla fynd till rätt produktteam och ge underlag för prioritering. Allvarlighetsvärden behöver vägas samman med faktisk exponering, känd exploatering och verksamhetens konsekvenser.

Förmågan ska även stödja spårbar åtgärd, tidsbundna undantag och omtest. Antalet utförda skanningar är mindre relevant än om riskfyllda brister upptäcks och åtgärdas. Inventeringen måste omfatta verkliga arbetslaster, även när de är kortlivade eller ligger i förvaltade molntjänster.

### Säkerhetsdetektion och incidentstöd

Det behövs gemensamma möjligheter att samla och analysera säkerhetsrelevanta händelser, upptäcka misstänkt beteende, korrelera signaler och stödja utredning och begränsning av angrepp. Ett säkerhetslarm ska kunna knytas till en tjänst, ägare och möjlig påverkan. Detektion behöver regelbundet prövas så att både missade angrepp och falsklarm blir synliga.

*Driftbarhet och motståndskraft* erbjuder generell logginsamling, övervakning och återhämtning. Säkerhetsförmågan kan använda samma tekniska signaler men ansvarar för hotinriktad analys, skyddsåtgärder och stöd till cybersäkerhetsincidenter. Vid misstänkta intrång behöver säkerhet, drift och berörda produktteam kunna samordna isolering, säkring av utredningsunderlag och säker återstart. Gemensamma incidentvägar behövs när tekniska fel och angrepp överlappar; det räcker inte att säkerhetslarmet når rätt mottagare.

### Säkerhetskontroller i utveckling och leverans

Kod, programvaruberoenden, byggartefakter, hemligheter och infrastrukturdefinitioner behöver kunna kontrolleras automatiskt. Tjänsteerbjudandet omfattar skanning, policykontroller, återkoppling om fynd och kontrollerbara undantag. *Utveckling och teknisk leverans* integrerar dessa kontroller i bygg-, test- och publiceringsflöden; säkerhetsförmågan ansvarar för de gemensamma skyddsreglerna, specialiserade kontrolltjänster och uppföljning av deras effekt. Automatiska fynd ersätter inte produktteamets ansvar för säker applikationsdesign och rättning. [K001]

## Generation 3 – skydd som en del av plattformarnas standarderbjudande

I generation 2 kan skydd och granskning bygga på centrala specialister som installerar säkerhetsprodukter, granskar varje release och handlägger undantag. I generation 3 behöver samma skydd i större utsträckning följa med när ett utvecklingsteam etablerar eller förändrar en tjänst: standardprofiler, versionerade säkerhetsregler, automatiska kontroller och återkoppling direkt till teamet.

Plattformsteam och säkerhetsfunktion ansvarar för säkra standardval, kontrolltjänsternas kvalitet och möjligheten att följa upp undantag. Produktteam kan själva se sina fynd, åtgärda brister och leverera normala förändringar utan att fastna i en manuell säkerhetskö. Säkerhetskraven blir därmed inte svagare; de blir mer konsekventa och kan följas upp under drift, inte bara före en driftsättning. Riskfyllda undantag kan fortfarande kräva särskild prövning.

## Generation 4 – riskanpassat skydd för verksamhetsskapade lösningar

När verksamheten själv kan skapa assistenter, automatiseringar och enklare applikationer behöver det godkända erbjudandet ge skydd utan att skaparen måste välja säkerhetsprodukter eller konfigurera varje kontroll. Skapandemiljön bör använda förvalda skyddsprofiler utifrån informationskänslighet, externa anslutningar, tänkbara åtgärder och lösningens betydelse. En personlig informationsassistent kan få en begränsad profil, medan en agent som ändrar ärenden eller skickar information externt behöver starkare kontroll och ibland professionell granskning.

AI-baserade lösningar tillför särskilda risker. Innehåll från dokument och webbsidor kan innehålla instruktioner som försöker styra en assistent fel; verktygsanrop kan ge större handlingsutrymme än avsett; in- och utdata kan sprida skyddsvärd information. Det gemensamma skyddserbjudandet behöver därför omfatta exempelvis granskning av verktygens risker, begränsning av informationsöverföring, säkerhetstester mot manipulation och möjlighet att upptäcka och stoppa misstänkt aktivitet. Dessa skydd minskar riskerna men kan inte garantera att en AI-modell aldrig påverkas av skadligt innehåll. [K004]

Säkerhetsförmågan erbjuder skydd mot manipulation och otillåten informationsspridning samt hotdetektion. Den utvärderar inte i sig AI-svarens verksamhetsmässiga kvalitet; den funktionen hör till *Analys, sökning och intelligent informationsbearbetning*. Ett säkerhetsstopp kan hindra nya anrop men inte återta redan utförda åtgärder.

Förmågan bör slutligen ge överblick över vilka verksamhetsskapade lösningar som omfattas av skydd, vilka avvikelser som finns och vem som ansvarar för dem. Huvudpoängen i generation 4 är inte att varje användare ska bli säkerhetsexpert, utan att det säkra normalfallet ska vara enkelt att välja och att avvikande risker upptäcks innan lösningarna får större räckvidd.
