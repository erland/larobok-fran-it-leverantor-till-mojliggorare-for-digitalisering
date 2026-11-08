# Nätverk och konnektivitet

När ett stort IT-stöd delas upp i mindre tjänster blir kommunikationen mellan dem en förutsättning för att verksamhetsflödet ska fungera. Det kan handla om anrop mellan applikationer, anslutning till datatjänster, trafik mellan driftmiljöer eller kommunikation med externa organisationer. Förmågan *Nätverk och konnektivitet* ska erbjuda säkra, tillgängliga och hanterbara tekniska kommunikationsvägar. Den ansvarar för teknisk nåbarhet och trafikpolicy – inte för API-anropets verksamhetsinnehåll eller beslutet om en verksamhetsåtgärd får utföras.

## Vad det gemensamma erbjudandet behöver omfatta

### Grundläggande anslutning och trafikvägar

Organisationen behöver tjänster för namnuppslagning och adressering, exempelvis DNS och IP-adresshantering, samt för anslutning inom och mellan applikationsplattformar, datacenter och molnmiljöer. Där verksamheten behöver det tillkommer lokala och trådlösa nät, anslutningar mellan platser, internetanslutning och säker fjärråtkomst. Varje organisation behöver inte driva alla dessa tjänster själv; en del kan ingå i en förvaltad moln- eller drifttjänst.

För applikationer behövs ofta kontrollerad inkommande trafik, lastbalansering och tydliga vägar till interna och externa beroenden. Erbjudandet ska ange vilka typer av anslutningar som stöds, deras kapacitet, fördröjning, tillgänglighet och ansvar för förändringar. Nätverksredundans kan minska störningar men kan inte ensam garantera att ett helt verksamhetsflöde fungerar vid fel.

### Segmentering, trafikpolicy och externa anslutningar

Förmågan behöver erbjuda lämplig nätsegmentering, trafikbegränsning och spårbara regler för vilka tekniska kommunikationsrelationer som tillåts. Det kan omfatta brandväggar, plattformsnära nätpolicyer, begränsning av utgående trafik och säkra tekniska vägar till externa parter. En anslutning ska ha ett identifierbart ändamål och en ansvarig, och den ska kunna ändras eller avvecklas när behovet upphör.

En tillåten trafikväg betyder inte att ett API-anrop är autentiserat eller att en viss verksamhetsåtgärd får utföras. *Identitet och tillit* erbjuder identiteter och tekniskt behörighetsstöd; *Integration och informationsutbyte* erbjuder API-gränssnitt och tekniska anropskontroller; *Cybersäkerhet och tekniskt skydd* erbjuder kompletterande skydd av exempelvis innehållet i anrop. Mottagande verksamhetssystem verkställer sina egna åtgärdsregler. Varken brandväggar eller API-gatewayer ersätter den kontrollen. [K007]

### Felsökning och livscykel för anslutningar

Nätverksförmågan ska göra det möjligt att följa viktiga kommunikationsberoenden, utreda nekad trafik och upptäcka kapacitets- eller anslutningsproblem. Den visar varför en anslutning inte fungerar; integrations- och driftbarhetstjänster behövs för att följa ett anrop eller verksamhetsflöde genom flera system. Det kräver ägarskap för namnposter, regler och externa förbindelser samt tillräcklig insyn i förändringar och relevanta trafikuppgifter. All trafik behöver inte loggas i detalj; insynen ska anpassas till felsökningsbehov, skydd och integritet.

En användbar anslutningstjänst omfattar även test före förändring, möjlighet att återställa felaktiga nätpolicyer och städning när en arbetslast tas bort. En regel som får ligga kvar efter avveckling kan skapa risk även om den ursprungliga anslutningen fungerade korrekt. Där flera tekniska miljöer ingår måste det vara tydligt var felsökningen börjar och vem som samordnar den.

I generation 1 kunde ett begränsat antal stora system göra zonindelning och relativt sällsynta nätändringar hanterbara. I generation 2 kan ett ärendeflöde i stället passera webbgränssnitt, flera tjänster, databaser och externa anslutningar. Om varje förändring kräver separata ärenden om brandvägg, DNS och lastbalansering växer ledtiderna. Ibland leder det till alltför breda nätzoner eller regler som ingen längre vet varför de behövs.

Det första steget är ändå inte nödvändigtvis en ny nätverksplattform. Organisationen behöver först få ordning på ägare, beroenden, regeländringar, felsökning och avveckling. Fler tjänster innebär heller inte automatiskt lika många nya brandväggsregler: behovet beror på topologi och var säkerhetsgränser faktiskt går.

## Generation 3 – konnektivitet som självbetjänad plattformstjänst

I generation 3 kan professionella utvecklingsteam själva begära eller deklarera godkända nätrelationer, till exempel att en applikation ska exponeras internt, nå en databastjänst eller ansluta till ett API. Nätverksplattformen kontrollerar begäran mot standardprofiler och etablerar i normalfallet DNS, trafikpolicy och relevanta anslutningar automatiskt. Teamet får begriplig återkoppling om tillåtna och nekade flöden utan att administrera den gemensamma infrastrukturen.

Självbetjäningen måste också fungera vid ändringar, felsökning och avveckling. Annars har organisationen bara ersatt en blankett med en portal som skickar ärendet vidare. Nätverksteamet ansvarar för förvaltade nätprodukter, policyernas kvalitet, kapacitet och undantagsvägar; produktteamet ansvarar för att ange vilka beroenden dess tjänst faktiskt behöver. Särskilt skyddsvärda förbindelser och ovanliga trafikmönster kan fortsatt behöva specialistprövning. Tekniker som service mesh kan vara användbara i vissa miljöer men är inget generellt krav för denna generationsförflyttning.

## Generation 4 – riskstyrda anslutningar utan nätverkskunskap hos skaparen

En verksamhetsmedarbetare som skapar en assistent, automation eller mindre applikation ska normalt inte behöva beställa portar, välja nätverkszoner eller konfigurera DNS. Den godkända skapandemiljön kan i stället förmedla vilka godkända tjänster lösningen behöver nå och vilka informations- och riskkrav som gäller. Nätverksförmågan kan då erbjuda en begränsad anslutningsprofil med godkända externa destinationer, tydligt ägarskap och automatisk avveckling. När en anslutning helt ingår i en extern molntjänst behöver motsvarande begränsningar i stället säkerställas genom leverantörens kontroller och tjänstevillkor; den interna nätplattformen styr inte automatiskt trafiken där.

En assistent som bara läser information via en redan godkänd molntjänst kan använda anslutningar som ingår där och behöver inte få ett eget internt nät. En automation som kommunicerar med ett känsligt verksamhetssystem eller skickar data externt kan däremot behöva snävare trafikbegränsning och särskild prövning. Nätprofilen kan begränsa vart trafiken går, men kan inte ensam avgöra om en agent har rätt att läsa en viss uppgift eller utföra en åtgärd. Att stoppa nättrafik hindrar inte heller automatiskt redan genomförda externa handlingar.

Erbjudandet gör anslutningsprofiler användbara både för professionella team och för verksamhetsskapade lösningar, utan att nätverksförmågan tar över ansvar för informationens innehåll eller tillåtna verksamhetsåtgärder.
