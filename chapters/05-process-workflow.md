# Process, workflow och ärendehantering

När flera system och människor deltar i ett verksamhetsflöde räcker det inte att varje tekniskt anrop fungerar. En ansökan kan vänta på komplettering, ett beslut eller en kontroll i veckor. Någon behöver veta vilket steg som pågår, vem som ska agera och vad som händer om en tjänst inte svarar. Förmågan *Process, workflow och ärendehantering* ska erbjuda tekniskt stöd för sådana sammanhängande, ofta långlivade förlopp. Verksamheten ansvarar fortfarande för processen och dess beslut.

## Vad den gemensamma förmågan behöver erbjuda

### Workflow och beständiga processflöden

Workflowtjänster kan samordna en följd av steg med väntelägen, tidsfrister, återförsök och möjlighet att fortsätta efter avbrott. Det kan vara en uttrycklig processmotor eller ett enklare tekniskt stöd för en avgränsad process. Förmågan behöver kunna visa var en processinstans befinner sig och varför den väntar. Den ska även stödja kontrollerad felhantering, så att ett misslyckat eller uteblivet svar kan utredas och processinstansen inte lämnas i ett oklart läge. Att ett integrationsanrop har kvitterats betyder inte nödvändigtvis att verksamhetssteget är slutfört.

Alla processer behöver inte en workflowmotor. En kort och välavgränsad uppgift kan ofta hanteras säkrare med vanlig applikationslogik och en tydlig tillståndsmodell. En gemensam tjänst är motiverad när återkommande behov av exempelvis väntelägen och återupptagning gör lokala speciallösningar svåra att förvalta.

### Ärendekontext och mänskliga arbetsuppgifter

En case management-tjänst kan hålla samman teknisk ärendekontext, aktiviteter och historik även när arbetets ordning varierar. Den är inte automatiskt organisationens fullständiga ärendesystem eller den auktoritativa källan till alla ärendeuppgifter. Det måste vara tydligt vilket system som äger ett ärendes faktiska status och innehåll.

Tjänster för mänskliga arbetsuppgifter kan erbjuda arbetsköer, tilldelning, övertagande, tidsgränser och eskalering. Att en uppgift ligger i en handläggares kö innebär dock inte att personen har rätt att fatta beslutet. Verksamhetssystemet behöver tillämpa sina behörighetsregler med stöd av *Identitet och tillit*.

### Notifikationer och uppföljning

Processförmågan kan utlösa påminnelser och aviseringar vid exempelvis en tidsfrist eller en ny arbetsuppgift. Själva utskicket och kanalanpassningen kan erbjudas genom *Interaktion, presentation och kanaler*, med stöd för mottagare, leveransförsök och fel. Det funktionella syftet skiljer sig från integrationsförmågans köer och systemhändelser: en notifiering uppmärksammar en människa, medan en integrationshändelse förmedlar information mellan system. Samma tekniska leveranstjänst kan ibland användas bakom båda. En skickad notifiering bevisar varken att mottagaren tagit del av den eller att arbetsuppgiften slutförts. Särskilda rättsliga krav på delgivning behöver hanteras för sig.

### Tillstånd, ändringar och avvikelser

För långlivade processer behövs stöd för att identifiera en viss processinstans, koppla inkommande svar till rätt steg och hantera dubbletter, sena händelser och tidsgränser. Integrationsplattformens leverans- och återförsöksmekanismer avgör inte om ett processsteg ska köras på nytt. När två handläggare försöker ändra samma ärende samtidigt kan till exempel versionskontroll förhindra att den ena ändringen tyst skriver över den andra. Vilka övergångar som är giltiga och hur en konflikt ska lösas bestäms av verksamhetens regler. När samma villkor används i flera flöden kan det utvärderas av en tjänst för *Regler och beslut*, men processförmågan ansvarar för att tillämpa resultatet på rätt instans och steg.

Återförsök och avbrott kräver samma tydlighet. En genomförd betalning eller ett skickat beslut kan inte göras ogjort bara genom att en teknisk process återställs. Verksamhetsansvariga behöver definiera när en rättelse, kompenserande åtgärd eller mänsklig avstämning krävs. *Integration och informationsutbyte* tillhandahåller transport, kontrakt och teknisk anropsspårbarhet; processförmågan håller samman processinstansens steg, väntelägen och status. Verksamhetssystemet äger fortfarande beslut och auktoritativa ärendeuppgifter.

## Generation 3 – utvecklingsteamen tar ansvar för sina processlösningar

I generation 2 är det vanligt att ett centralt specialistteam både förvaltar en gemensam ärendehanteringsplattform och konfigurerar nya ärendeflöden, formulär och förändringar åt flera verksamhetsområden. Andra utvecklingsteam kan då behöva beställa även normala justeringar. När antalet processlösningar växer blir det centrala teamet lätt en flaskhals, trots att plattformen redan är gemensam.

I generation 3 ändras erbjudandet: plattformsteamet tillhandahåller en förvaltad, självbetjänad processtjänst där respektive professionellt utvecklingsteam själv kan utforma, konfigurera, testa, driftsätta, följa upp, ändra och avveckla sina processlösningar. Det gäller exempelvis ärendeflöden, användning och sammansättning av formulär, arbetsuppgifter och godkända integrationer. Formulärkomponenter och deras klientbeteende erbjuds genom *Interaktion, presentation och kanaler*; processtjänsten knyter insamlingen till rätt steg och ärende. För att självbetjäningen ska fungera behöver erbjudandet ge teamen avgränsade konfigurationsytor, rättigheter till egna flöden, återanvändbara komponenter, testdata och en kontrollerad väg från test till produktion. Normal konfiguration och publicering ska kunna ske utan en central genomförandekö; gemensamma ändringar kan fortfarande kräva samordning. Teamet ansvarar för sin lösnings funktion och förvaltning; verksamhetens processägare ansvarar fortsatt för processens innehåll och beslut.

Självbetjäning förutsätter en plattform som kan skilja teamägda flöden från gemensamma datamodeller, säkerhetsinställningar och återanvända komponenter. Om en befintlig plattform inte kan isolera dessa förändringar är full självbetjäning inte säkert möjlig utan ytterligare anpassning eller en annan ansvarsfördelning. Plattformsteamet ansvarar för gemensamma funktioner, isolering, säkerhet, robusthet, uppgraderingar och plattformens tekniska livscykel. Förändringar som påverkar flera verksamhetsområden behöver samordnas med berörda processägare. Plattformens uppgift förskjuts därmed från att själv bygga varje flöde till att möjliggöra teamens självständiga leveranser.

För långlivade processer är versionshantering särskilt viktig. Ett ärende kan ha startats enligt en äldre processversion och fortfarande vara aktivt när ett nytt flöde driftsätts. Processversionen och den regelversion som ska gälla för ärendet är skilda frågor; båda behöver kunna identifieras där det påverkar utfallet. Processtjänsten behöver därför stödja kontrollerad samexistens mellan versioner och, där tekniken medger det, prövad övergång för pågående instanser. En ny version får inte förutsättas ersätta alla pågående flöden utan risk för förlorade uppgifter eller dubbla åtgärder.

## Generation 4 – verksamheten skapar och förvaltar sina egna flöden

I generation 4 ska verksamhetsmedarbetare kunna utforma, prova, publicera och vidareutveckla många av sina ärende- och arbetsflöden utan att varje förändring kräver ett utvecklingsteam. En godkänd visuell eller AI-stödd skapandemiljö kan låta dem beskriva arbetsuppgifter, formulär, ansvariga roller, väntelägen, beslutspunkter och automatiserade moment. Det kan vara en förvaltad low-code- eller SaaS-tjänst; en separat intern workflowmotor är inte alltid nödvändig.

Erbjudandet behöver omfatta hela den verksamhetsnära livscykeln. Medarbetaren ska kunna simulera och testa olika ärendeförlopp, inklusive undantag och uteblivna svar, innan flödet delas. Provningen behöver använda testuppgifter eller kontrollerade testanslutningar, så att ett försök inte oavsiktligt ändrar riktiga ärenden eller utlöser externa åtgärder. Därefter ska det gå att publicera till en avgränsad användargrupp, följa ärendestatus och avvikelser, prova ändringar och införa nya versioner. När pågående ärenden berörs behöver det finnas stöd för att låta äldre versioner leva kvar eller genomföra en kontrollerad övergång. Det ska också gå att stoppa och avveckla flöden utan att ärenden lämnas utan ägare.

Byggstenar som ”begär komplettering”, ”vänta på godkännande” och ”påminn ansvarig” döljer tekniken bakom flödet. Processen kan använda godkända verksamhetsfunktioner från *Integration och informationsutbyte* och regelresultat från *Regler och beslut*. Processägaren bestämmer vilka steg som får automatiseras; publiceringsrätt är inte liktydigt med beslutsmandat.

Verksamheten bör kunna förvalta enkla interna flöden själv, medan kritiska flöden kan kräva specialiststöd. Processägaren svarar för innehåll, automatiseringsgränser och avvikelser. Processförmågan erbjuder modellering, provning av flödeslogik, instanshantering och uppföljning; den övergripande publiceringsmodellen beskrivs i *Utveckling och teknisk leverans*.

Den avgörande förflyttningen är alltså inte från programmering till en viss processmotor. Den är från svåröverskådliga överlämningar till processer som kan följas, fortsätta efter fel och förändras med tydligt ansvar – först för professionella team och sedan, inom lämpliga gränser, för verksamheten själv.
