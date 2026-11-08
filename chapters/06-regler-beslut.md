# Regler och beslut

Två personer med samma förutsättningar ska inte få olika besked bara för att de använder olika kanaler. Ändå kan det ske när villkor för avgifter, ersättningar eller behörighet är inbyggda på olika sätt i flera IT-stöd. Förmågan *Regler och beslut* erbjuder stöd för att beskriva, testa, tillämpa och förvalta uttryckliga verksamhetsregler som har en egen betydelse och livscykel. Den ska inte ersätta all programlogik: en enkel och stabil beräkning kan vara tydligare i applikationens egen kod.

## Vad den gemensamma förmågan behöver erbjuda

### Regelmodellering och simulering

Tjänster för regelmodellering gör det möjligt att uttrycka exempelvis villkor, undantag och beräkningar som beslutstabeller eller andra begripliga modeller. Verksamheten ska kunna pröva hur en regel fungerar för normalfall, gränsfall, ofullständiga uppgifter och motstridiga villkor. Vid ändringar ska det gå att jämföra en föreslagen modell med den gällande och undersöka vilka utfall som skulle skilja sig. Sådan simulering visar effekter på provfallen, inte säkert alla konsekvenser i verklig användning.

### Besluts- och regelkörning

En regelkörning tar emot definierade uppgifter och lämnar ett resultat enligt en viss regelversion. När flera system behöver samma regel kan en förvaltad beslutstjänst minska risken för avvikande tolkningar. Tjänsten behöver ha tydliga kontrakt för indata, utdata och fel samt kunna hantera ändringar utan att konsumenterna oväntat får ett annat resultat. Regelkörningen kan vara en gemensam teknisk tjänst eller ligga hos det domänteam som äger funktionen; alla beslut behöver inte passera en central motor.

Det är viktigt att skilja mellan regelresultat och verksamhetsbeslut. Att en regelmotor räknar fram att en ansökan uppfyller ett villkor betyder inte nödvändigtvis att ansökan är beviljad. Ett sådant beslut kan kräva ytterligare kontroller, behörig beslutsfattare eller en rättsligt tillåten och formellt beslutad automatiserad beslutsprocess. Om personuppgifter används måste också tillämpliga dataskyddsregler prövas. GDPR:s artikel 22 ger ett särskilt skydd mot beslut som enbart grundas på automatiserad behandling och får rättsliga eller liknande betydande följder, med särskilda undantag och skyddsåtgärder. Bestämmelsen innebär varken ett generellt förbud mot all automatisering eller ett generellt tillstånd så snart någon människa finns med i arbetsflödet. Verksamheten äger regelns innebörd och beslutsmandat, även när tekniken utför beräkningen. [K011]

### Regelversioner och förklarbara resultat

En regel kan beslutas vid en tidpunkt, börja gälla vid en annan och användas när ett ärende avgörs vid en tredje. Därför behöver tjänsterna hålla reda på både regelversion och de verksamhetsmässiga villkor som avgör vilken version som ska tillämpas. Ett pågående ärende kan fortsätta enligt en äldre processversion men behöva prövas mot en nyare regel, eller tvärtom: valet följer beslutade giltighetsvillkor och kan inte härledas från processens version ensam. Övergångsbestämmelser kan exempelvis göra att en äldre regel fortfarande gäller för en ansökan som kom in innan en ändring.

För att kunna förklara ett tidigare beslut behöver det finnas tillräckligt underlag om använda regler, relevanta indata och externa uppgifter. Det är inte samma sak som att alltid kunna köra om beslutet och få ett identiskt resultat: data och beroenden kan ha ändrats eller inte längre få bevaras. Krav på spårbarhet och lagring behöver därför utformas efter informationens känslighet och tillämpliga bevarande- och gallringsregler.

## Generation 3 – utvecklingsteamen förvaltar sina regelmodeller

I generation 2 kan ett centralt specialistteam både sköta en gemensam beslutsplattform och implementera eller publicera regler åt flera verksamhetsområden. Även enkla regeländringar kan då behöva beställas och genomföras centralt. Samtidigt kan andra regler finnas kopierade i olika applikationer, vilket gör likvärdiga beslut svårare att säkerställa.

I generation 3 förändras erbjudandet. Plattformsteamet tillhandahåller förvaltade funktioner för modellering, test, körning, versionshantering och publicering, medan respektive professionellt utvecklingsteam själv kan skapa, konfigurera, testa, leverera och förvalta sina regelmodeller. Teamet behöver avgränsade arbetsytor, åtkomst till godkända testdata, automatiska kontroller och möjlighet att tekniskt publicera en version som verksamhetens regelägare godkänt, utan att ett centralt team utför varje steg. Rätten att driftsätta en modell och befogenheten att godkänna dess verksamhetsinnehåll är olika. Plattformsteamet ansvarar för tjänsternas säkerhet, isolering, robusthet och uppgraderingar; verksamhetens regelägare ansvarar för innehåll, giltighet och godkännande.

Gemensamma tjänster är inte alltid det bästa alternativet. Om en regel bara används i ett system och är nära knuten till dess domänlogik kan ett vältestat lokalt genomförande vara lämpligare. Självbetjäning handlar därför om att teamet kan välja och använda ett godkänt erbjudande, inte om att alla regler måste flyttas till en enda regelmotor. En gemensam plattform behöver också kunna isolera teamens modeller så att en ändring eller ett fel inte påverkar andra verksamheter.

## Generation 4 – verksamheten utformar och förändrar regler

I generation 4 bör verksamhetsmedarbetare själva kunna formulera, prova, publicera, följa upp och vidareutveckla många av sina verksamhetsregler inom givna ramar. En visuell miljö kan låta en regelägare ändra villkor eller beslutstabeller, simulera ett urval av syntetiska eller behörigt hanterade historiska fall i en isolerad testmiljö, granska skillnaden mot gällande version och sedan publicera en godkänd ändring. Ett simuleringstest får inte skriva beslut eller ändra ärenden i produktion. AI kan hjälpa till att föreslå modeller och testfall, men förslagen måste granskas; de kan missa undantag eller misstolka verksamhetsbegrepp.

För enkla interna klassificeringar och avgränsade styrregler kan en behörig verksamhetsmedarbetare ofta hantera hela livscykeln själv, med tydligt ansvar för regelns innehåll och tillämpning. När regler påverkar rättigheter, skyldigheter, ersättning eller andra betydande beslut behövs starkare kontroller. Publicering kan då kräva särskild attest, oberoende tester och en tydlig beslutsansvarig. Ett AI-genererat förslag får inte kringgå dessa kontroller, och en språkmodells svar ska inte förväxlas med ett deterministiskt regelresultat. Inte heller innebär en tekniskt publicerad modell att den som använder modellen har mandat att fatta beslut.

Den gemensamma förmågan behöver därför göra både regelns innehåll och publiceringsvägen begripliga för verksamheten. Den ska stödja att felaktiga versioner kan stoppas för framtida användning och att berörda tidigare beslut kan identifieras för eventuell rättelse eller omprövning. Att växla tillbaka till en äldre regelversion gör inte redan verkställda beslut ogjorda.

## Gränserna mot andra förmågor

Ett ärendeflöde kan använda ett regelresultat för att välja nästa steg, men det är regelförmågan som hanterar regelns innehåll, giltighet och version. Processförmågan håller reda på ärendets steg och tillstånd. Beslutsmandat prövas av behörig verksamhetsfunktion; det följer inte automatiskt av regelresultatet.

Förflyttningen mellan generationerna är därmed inte att alla beslut centraliseras. Det är att reglernas innehåll, ändringar och konsekvenser blir begripliga och hanterbara: först för självständiga utvecklingsteam och därefter, när beslutens risk tillåter det, för verksamheten själv.
