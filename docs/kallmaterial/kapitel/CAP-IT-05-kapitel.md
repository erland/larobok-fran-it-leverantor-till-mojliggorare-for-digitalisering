# CAP-IT-05 – Analys, sökning och intelligent informationsbearbetning

Analys hjälper en organisation att förstå vad som har hänt, vad som händer och vilka handlingsalternativ som kan vara rimliga. Sökning hjälper människor och system att hitta information. Intelligenta metoder kan klassificera, uppskatta, extrahera eller sammanfatta innehåll. Men ingen av dessa tekniska förmågor ersätter frågan om **vad uppgifterna betyder, vem som äger dem och när resultatet är tillräckligt tillförlitligt för att användas**.

Det här kapitlet beskriver fyra generationer av IT. Generationerna är analytiska idealtyper, inte obligatoriska tekniksteg. En organisation kan ha avancerad analys redan i generation 1 och ett enkelt, välfungerande rapportbehov i generation 4. Den huvudsakliga utgångspunkten är generation 2: många tjänster och informationskällor men ofta splittrade analysflöden. Frågan är dels hur den situationen kan bli tillförlitlig, dels när återkommande behov motiverar plattformstjänster i generation 3. Generation 4 behandlas som ett möjligt framtidsscenario, inte som ett säkert utfall.

Kapitlets begrepp är viktiga. **Operativa data** beskriver vad verksamhetssystemen för närvarande vet. **Analytiska data** är en avsiktligt bearbetad representation för frågor och jämförelser, ofta med annan uppdateringsfrekvens. **Sökindex** gör material möjligt att hitta, men är inte automatiskt en auktoritativ källa. **Måttdefinitioner** avgör vad exempelvis ett avslutat ärende faktiskt betyder. **AI-genererade slutsatser** är ytterligare ett tolkningsled och måste bedömas därefter.

## Kort tillbakablick: generation 1

I sammanhållna IT-stöd kunde rapportering och sökning ofta utvecklas nära de data och den verksamhetslogik som producerade dem. En databasfråga, ett schemalagt rapportjobb och ett sökfält kunde räcka långt. Lokala specialister kände verksamhetsbegreppen och anpassade rapporterna. Svagheterna var ofta beroende av personer och dokumentation: samma ord kunde betyda olika saker i olika system, och rapportuttag blev svåra att återupprepa när någon slutade.

**G1→G2** ökade antalet självständiga källor, API:er, datakopior och transformationer. Möjligheten att kombinera information växte, men ett svar krävde ibland en hel kedja av datauttag. Det som förr var en lokal rapportfråga blev en fråga om källans ägare, schemaversion, uppdateringsfördröjning, behörighet och gemensamma definitioner. Därmed uppstod ett generationsarv: analytiska lösningar kunde bli tekniskt distribuerade utan att ansvar, dataavtal eller kvalitetskontroller utvecklades lika snabbt.

## Generation 2 – många källor, motstridiga svar

### När blir förmågan viktig?

Ett ledningsteam får tre siffror för antalet avslutade ärenden för samma period. Ärendesystemet räknar beslut, ett rapportlager räknar senaste status och en söktjänst räknar dokument märkta ”avslutad”. Samtliga siffror kan vara korrekt beräknade enligt sina egna regler. Ingen av dem behöver ändå besvara ledningens fråga. En ny BI-produkt löser inte motsägelsen om organisationen saknar en gemensam definition av ärendetyp, avslut och period.

Första uppgiften är att identifiera **vilken fråga som faktiskt ska besvaras** och vilken informationskälla som får svara på den. Verksamheten behöver äga definitioner och acceptera eventuella skillnader mellan beslutsdatum, registreringsdatum och uppdateringsdatum. Den tekniska förmågan behöver kunna visa varifrån varje mått kommer, vilka transformationer som gjorts och vilken tidsmässig begränsning resultatet har. Dataägarskap och lagring hör i grunden till CAP-IT-04; CAP-IT-05 omsätter godkända källor till sökning och analys.

### Kvalitet behöver beskrivas per användning

”God datakvalitet” är ingen enda egenskap. En inventeringsrapport kan klara några minuters fördröjning medan ett operativt larm inte gör det. En trendanalys kan tolerera uppskattningar där ett individuellt beslut kräver kontrollerade, fullständiga uppgifter. Bedöm därför aktualitet, fullständighet, riktighet, begriplighet, jämförbarhet och relevanta felgränser för varje viktig användning. En lyckad laddning till ett datalager bevisar bara att en teknisk överföring skett – inte att måttet betyder rätt sak.

Analytiska pipelines behöver dokumenterade transformeringar och kontroller före publicering. Relevanta prov kan vara att ändra ett källschema, tillföra sena händelser, hitta dubbletter, återspela en period och jämföra summeringar med godkända primärkällor. En datakvalitetskontroll som endast mäter om ett fält är ifyllt kan missa att värdet har fel enhet eller betydelse. Rätt kontroller utformas med användarna av analysen och dem som förvaltar källinformationen.

**Historisk reproducerbarhet** behöver avgränsas. Man kan ofta förklara med vilka källversioner, måttdefinitioner och transformeringar en publicerad rapport framställdes. Det betyder inte att man alltid kan återskapa exakt samma resultat om gamla data aldrig sparades, externa tjänster förändrats eller rättslig gallring har genomförts. För kritiska rapporter behöver organisationen i förväg välja vad som ska bevaras, på vilken nivå och hur länge.

### Sena händelser, rättelser och förändrade mått

En rapport kan förändras trots att dess publicerade måttdefinition är oförändrad. Uppgifter kan registreras sent, en källa kan korrigera ett tidigare fel och en dataladdning kan köras om. Därför behöver verksamheten skilja mellan **händelsetid** (när något inträffade), **registreringstid** (när systemet fick veta det) och **rapportens beräkningstid** (vilken informationsversion som användes). En summering för föregående månad behöver inte vara slutgiltig bara för att kalendern har bytt månad.

Välj uttryckligen om en rapport ska visa *vad vi visste då*, *vad vi vet nu om samma period* eller *vad som gällde enligt den då aktuella definitionen*. Alla tre kan vara legitima men besvarar olika frågor. En definierad rättelsepolicy anger när siffror får räknas om, vilka användare som ska informeras och hur äldre publicerade utfall kan förklaras. Om ett mått ändras kan det vara bättre att publicera en ny versionsmärkt tidsserie än att i tysthet skriva om den gamla.

Det behövs också mätningar av datakedjans **färskhet, fullständighet och fördröjning**. Ett körningsjobb som är grönt kan ändå ha tappat en undergrupp av poster. Prova därför både kända fel och en avsiktlig försening, följ vad som upptäcks, vem som får larm och hur felet rättas. Tjänsten som transporterar data kan mäta leveransfullständighet, medan verksamheten normalt måste bedöma uppgifternas innehållsliga riktighet. Den skillnaden är viktig när gemensamma plattformstjänster får egna serviceåtaganden.

### Sökbarhet är inte liktydigt med korrekt eller tillåten information

Ett index är en kopia eller representation av källmaterial som kan ha en egen uppdateringsfördröjning. Om ett dokument får skärpt sekretess eller en användares rättigheter återkallas behöver söktjänsten förhindra otillåten läsning, även när indexet inte hunnit uppdateras. Skyddet måste även gälla träffrubriker, utdrag, förhandsvisningar, cachelagrade resultat och sammanställningar: själva förekomsten av en träff kan ibland röja information. Detta kan kräva behörighetsprövning vid förfrågan, kontroll mot ett aktuellt behörighetsunderlag eller ett likvärdigt verifierat förfarande; ett föråldrat behörighetsfält i indexet är inte ett tillräckligt skydd. Identitet och behörighetsregler hanteras tillsammans med CAP-IT-07 och CAP-IT-12, men söktjänsten måste kunna verkställa de relevanta kontrollerna i sin faktiska åtkomstkedja.

En sökträff som är relevant för sökordet kan vara fel version, fel person eller fel sammanhang. Därför behöver sökresultat visa källans identitet, status, aktualitet och – när det är relevant – varför träffen återfanns. Sökprecision och täckning kan testas med representativa frågor, inklusive negativa exempel och synonymer. Det är inte ett generellt krav att semantisk sökning används; välavgränsad nyckelords- och filtersökning kan vara bättre när begreppen är exakta.

### AI och maskininlärning är användningsfallsstyrda

Prediktiva modeller kan hjälpa till att uppskatta belastning, prioritera granskning eller kategorisera stora materialmängder. Bild- och ljudanalys kan extrahera innehåll som annars kräver manuellt arbete. Generativ AI kan sammanfatta och förklara, men kan också producera övertygande fel. Dessa tekniker blir relevanta utifrån konkreta behov, inte enbart därför att organisationen tillhör generation 2 eller senare.

För en prediktionsmodell behöver man bedöma datans representativitet, felkostnader, osäkerhet, förändringar över tid och vem som får agera på resultatet. Träningsdata och utvärderingsdata ska hållas åtskilda på ett sätt som motsvarar den avsedda framtida användningen. Vid tidsberoende prediktioner ska varje indatafält bara innehålla sådant som faktiskt var känt vid prediktionstidpunkten; annars kan **framtidsläckage** ge missvisande hög kvalitet. Även dubbelregistrerade individer och nära kopior mellan tränings- och testmängd kan göra resultaten överoptimistiska. En förbättring av ett tekniskt modellmått är inte nödvändigtvis en förbättring av verksamhetsutfallet. En modell som har hög träffsäkerhet i efterhand kan ändå vara olämplig för användning där falska positiva resultat har stor konsekvens.

För generativa AI-tjänster behöver uppgiften och risknivån avgöra kraven. Ett internt utkast till sammanfattning kan granskas innan publicering. En lösning som föreslår åtgärder i ett personärende kräver starkare kontroll av källor, fel, känsliga uppgifter och mandat. Den generativa modellens text är aldrig i sig bevis på att en åtgärd är tillåten. Beslut och verksamhetsregler hör till CAP-IT-03 och CAP-IT-02, agenternas verktyg och leveranskedja till angränsande förmågor.

### AI-kvalitet, källsäkerhet och förändringar över tid

En lösning som använder retrieval-augmented generation (RAG) har flera separata felkällor. Sökningen kan hämta fel dokument eller fel version; språkmodellen kan tolka ett korrekt dokument fel; och en korrekt sammanfattning kan ändå vara olämplig som underlag för ett visst verksamhetsbeslut. **Källhänvisningar är spårbarhetshjälp, inte bevis för att påståendet följer av källan.** Verifiera både att de uppgivna källorna stöder påståendena och att systemet kan avstå från ett svar när underlag saknas.

Dokument och sökresultat är dessutom **obetrodd indata**. En angripare kan placera instruktioner i ett dokument för att påverka modellens svar eller verktygsanrop. Kontroller behövs därför för otillåten informationsåtkomst, prompt injection, manipulation av indexinnehåll och osäker vidareanvändning av modellutdata. Det räcker inte att lägga in en instruktion om att modellen ska ignorera skadligt innehåll. Behörighetskontroller måste verkställas av betrodda komponenter, och riskfyllda åtgärder behöver separata tillstånds- och mandatkontroller.

Utvärderingen bör innehålla en representativ uppsättning verkliga frågor, svåra gränsfall, obehöriga källor och föråldrade dokument. För varje testfall kan man pröva retrieval-relevans, svarskorrekthet, källstöd, informationsskydd och konsekvens för användaren separat. Följ också förändringar vid nya modellversioner, nya promptmallar, ändrat index och förändrad datamängd. En förbättring i ett sammanvägt AI-mått får inte dölja att särskilt riskfyllda fall blivit sämre.

### Ett diagnostiskt exempel: tre rapporter och en AI-sammanfattning

Anta att en avdelningschef frågar hur lång handläggningstiden har varit under året. Det lokala ärendesystemet räknar från registrering till beslut. BI-rapporten räknar från komplett ansökan till expedition. En AI-assistent hittar den äldre BI-rapporten och skriver självsäkert att handläggningstiden har förbättrats. Sökningen har returnerat en relevant rapport – men källan är inaktuell och måttet skiljer sig från det chefen efterfrågade.

Prova kedjan stegvis. Välj en definierad population ärenden. Dokumentera begreppet handläggningstid och dess tidsregler. Kontrollera händelsetid, registreringstid, källans uttagsdatum, teknisk transformering och hur sent registrerade händelser hanteras. Jämför rapporterna på samma underlag och följ varje skillnad till en explicit beräkningsregel. Kontrollera därefter att söktjänsten prioriterar rätt version och att AI-svaret skiljer mellan verifierade uppgifter, osäkerhet och en egen sammanfattning. Prova även ett dokument som användaren saknar behörighet till.

Om skillnaden uppstår i måttdefinitionerna är det i första hand ett ägarskaps- och datakontraktsproblem. Om sökindexet inte kan uppdateras eller respektera rättigheter kan det vara ett teknik- eller integrationsproblem. Om AI-modellen fabricerar jämförelsen är det ett utvärderings- och användningsproblem. Ett plattformsbyte utan denna diagnos kan låsa in felen i en större lösning.

### Två skilda förbättringsspår i generation 2

**Spår A – lös kvarvarande generationsarv.** Peka ut auktoritativa källor, besluta om måttens innebörd, versionshantera transformationer, klassificera känsliga data och införa kvalitetskontroller. Se till att sökindex, rapporter och modeller skyddar information enligt dess faktiska åtkomstregler. Testa fel, sena uppdateringar och historiska förklaringar. Dessa grundkrav bör fungera även om ingen ny gemensam plattform införs.

**Spår B – undersök var gemensamma plattformstjänster behövs.** Samla evidens för hur många team som bygger egna dataladdningar, sökindex, BI-uppsättningar, modellservingmiljöer eller AI-gateways. Mät repetitionsgrad, väntetid, säkerhetsbrister, drift- och uppgraderingsarbete. När flera team har likartade behov kan ett förvaltat erbjudande bli attraktivt. Om behovet är unikt, kortlivat eller bäst hanteras nära en domän behöver plattformen inte centraliseras.

Fungerande generation 2 visar sig genom att en kritisk rapport går att förklara, en datakvalitetsbrist upptäcks före publicering, sökning respekterar behörighet och en AI-modells fel får konsekvenser som hanteras. Det är inte bevis på plattformsbehov att det finns många databaser eller modeller: motiveringen behöver visa faktisk upprepning eller förvaltningsrisk.

## Generation 3 – självbetjänade analys- och AI-tjänster

En gemensam analysplattform kan ge standardiserade arbetsytor, säker åtkomst till godkända dataset, pålitliga datapipelines, rapportpublicering, sökindex och tjänster för modellträning eller inferens. Den blir meningsfull när organisationen har **återkommande** behov där konsumenterna kan utföra standarduppgifter utan en serie specialistbeställningar. Självbetjäning omfattar mer än att skapa en ny instans: datakälla ska anslutas, ändringar och kostnader kunna följas, säkerhet och datakvalitet kontrolleras, uppgraderingar genomföras och resurser avvecklas.

Plattformsteamet äger den tekniska tjänstens produkt: gränssnitt, dokumentation, övervakning, livscykel, kostnad, användarstöd och standardprofiler. Verksamhetens informationsägare behåller ansvar för betydelsen av data, legitima användningar, klassificering och godkännande av centrala mått. Analytiker och produktteam ansvarar för analysernas syfte och rimlighet. En plattformsförvaltare kan garantera att en rapportmotor kör ett angivet uttryck; den kan inte garantera att uttrycket är rätt verksamhetsdefinition.

### Plattformens omfattning måste väljas, inte antas

Ett gemensamt BI-erbjudande kan vara viktigt där många grupper återanvänder rapporter. Ett semantiskt måttlager tillför värde om samma begrepp används över flera produkter och kanaler. Grafdatabaser och geospatiala tjänster behövs bara där relations- eller platsfrågor motiverar dem. ML-träning och acceleratorer behövs inte enbart för att organisationen använder en extern generativ modell via API. En gemensam LLM-gateway kan vara relevant för säkerhet, kvoter, modellval och kostnadskontroll, men innebär inte att egen modellträning måste införas.

Gör därför en separat bedömning för varje tjänst av (1) **funktionskritikalitet** i faktiskt användningsfall, (2) **nyttan av gemensam förvaltning**, och (3) **behovet av automatisering**. Hög risk i en specifik analys innebär inte att alla 16 tjänster ska införas centralt. Om en förmåga bara används av ett team kan en välstyrd lokal eller förvaltad extern tjänst vara bäst.

### Drift, kostnader och uppgraderingar hör till erbjudandet

En analysplattform behöver skydd mot okontrollerade kostnadstoppar från stora frågor, indexbyggen och modellkörningar. Kvoter och förbrukningsmätning kan kombineras med kapacitetsprofiler för olika användningar. Säkerhetsgränser ska omfatta både lagrade analyskopior och interaktiva frågor. En sökplattform kan vara robust medan ett enda alltför brett index ändå ger informationsläckage; varje konsument behöver därför pröva åtkomst och livscykel.

Förutsägbar uppgradering är lika viktig som snabb provisionering. Låt två verkliga konsumenter uppgradera en delad pipeline, sökmotor eller rapportkomponent. Kontrollera versionskontrakt, resultatens innebörd, bakåtkompatibilitet, mätetal och plan för avveckling. Ett semantiskt måttlager behöver hantera förändrade måttdefinitioner med uttryckliga giltighetsperioder, inte tyst ändra vad äldre rapporter betyder.

### Verklig självbetjäning kräver gränser för kostnad och åtkomst

En analysplattform kan bli en gemensam risk om självbetjäning innebär obegränsade frågor, oförutsägbara modellkostnader eller att data kopieras till nya arbetsytor utan livscykel. Godkända standardprofiler behöver därför begränsningar för informationsklass, region/leverantör där detta är relevant, beräkningsbudget, datalagring och livslängd. Prova vad som händer när en användare förbrukar sin kvot, när källans åtkomst återkallas och när en analysarbetsyta avslutas.

Förändringar ska kunna rullas ut hos verkliga konsumenter med kända mått på kvalitet, prestanda och kostnad. **Återgång till en tidigare modell eller pipeline återställer inte automatiskt redan publicerade rapporter, skickade AI-svar eller genomförda verksamhetsåtgärder.** Sådana konsekvenser kräver egna rutiner för rättelse, kommunikation och vid behov omprövning.

### När teknikvalet faktiskt är fel

Det är möjligt att en sökmotor saknar nödvändiga behörighetskontroller, en analysdatabas inte kan uppfylla rimliga svarstider eller en modellserver inte klarar tillåtna versionerings- och säkerhetskrav. Men andra vanliga orsaker är dåliga frågor, fel indexering, bristfälliga transformeringar, otillräcklig kapacitetsplanering eller otydligt ansvar. Undersök först ett reproducerbart användningsfall och grundorsaken. Jämför sedan fyra handlingsalternativ: **behålla**, **komplettera**, **ändra användning/ansvar**, och **ersätta**. En stor central plattform kan bli dyrare och svårare att förändra än flera avgränsade tjänster om användningarna inte har tillräckligt mycket gemensamt.

Mät framgång i både verksamhetsutfall och plattformsekonomi: färre motstridiga mått, snabbare tillgång till godkända analyser, återanvändning av kvalitetssäkrade datakontrakt, kortare ledtid till ändring och kontrollerad kostnad. Antalet dashboards, modeller eller GPU:er är inte i sig ett kvalitetsmått.

## Generation 4 – verksamhetsnära informationsbearbetning med kontroller

I ett möjligt framtidsscenario kan verksamhetsnära medarbetare fråga sina data med naturligt språk, skapa analyser och använda AI för att sammanfatta kunskapsmaterial utan att varje fråga blir ett utvecklingsprojekt. Detta förutsätter inte att alla lösningar är generativa. Väl definierade rapportmått, klassisk sökning och traditionell maskininlärning kan fortfarande vara bättre för många behov.

När en AI-assistent använder retrieval eller *grounding* hämtar den information från utvalda källor och försöker förankra svaret i dessa. Det ger möjligheter till källhänvisning och aktualitet, men är ingen garanti för sanningshalt. En modell kan misstolka en korrekt källa, välja fel avsnitt eller sammanföra uppgifter som inte får användas tillsammans. Källhänvisningen behöver därför gå att öppna och kontrolleras mot rätt version, åtkomst och den aktuella frågan. Här skiljer man **retrievalkvalitet** (hämtades rätt material?), **svarskvalitet** (blev slutsatsen korrekt?) och **verksamhetslämplighet** (får svaret användas för detta ändamål?).

Autentisering och behörighet måste verkställas av betrodda kontroller, inte av en instruktion i AI-modellens prompt. För begränsade uppgifter kan assistenten endast föreslå svar och låta en människa besluta. För verksamhetspåverkande handlingar behövs tydligt mandat, avgränsade verktyg, spårbarhet, förhandskontroller och möjlighet att stoppa framtida åtgärder. Återkallelse av rättigheter gör inte nödvändigtvis redan genomförda åtgärder ogjorda. AI-säkerhet och agentåtkomst kräver därför samverkan med CAP-IT-07, CAP-IT-12 och CAP-IT-10.

Modeller och kunskapskällor förändras över tid. Kontrollerad publicering behöver omfatta utvärdering före och efter modellbyte, kända felklasser, testfall för känsliga uppgifter, kostnadsbegränsningar, återställningsstrategier och tydligt ägarskap. En eval som säger att modellsvaret liknar ett förväntat svar är inte ensam ett tillräckligt bevis på säkerhet eller saklighet. Mänsklig granskning behövs där följderna motiverar den, men den måste organiseras så att granskaren faktiskt får nödvändig information och befogenhet att stoppa resultatet.

Organisationen bör även kunna avveckla tillfälliga analyser och AI-arbetsytor, återkalla åtkomst, följa informationskopior och kontrollera att resultat inte ligger kvar oavsiktligt. Funktioner som inte kan bära nödvändiga skydd eller som är oproportionerligt dyra bör inte erbjudas bara för att de går att skapa snabbt.

## De 16 plattformstjänsterna – uppgifter och prövning

De följande tjänsterna är **möjliga stödjande erbjudanden**, inte en lista över obligatoriska produkter i varje generation. Kopplingarna till plattformar följer källmodellen.

### PLS-015 – BI och rapportering (PLT-013)

Ger visualisering och återkommande rapportering från godkända källor. Prova att två enheter beräknar samma mått för samma urval och kan förklara skillnader. Plattformen äger rapporttekniken, inte måttets verksamhetsbetydelse. Kontrollera publicering, behörighet, versionsändring och rättelse av felaktiga rapporter.

### PLS-098 – Semantiskt data- och måttlager (PLT-013)

Ger återanvändbara måttdefinitioner och dimensioner när flera konsumenter har likartade behov. Prova ett mått som byter definition vid ett angivet datum; äldre rapporter ska kunna tolkas korrekt och ändringen vara möjlig att följa. Där måtten är få och stabila kan gemensamt dokumenterade definitioner räcka utan separat semantiskt lager. En gemensam teknik löser inte oenighet om begrepp utan verksamhetens godkännande.

### PLS-064 – Analytisk datahantering (PLT-020)

Tillhandahåller lagring och beräkningsstöd för analytiska dataset. Testa sena data, stora uttag, skydd av analyskopior och faktiska prestanda vid representativ last. Den ersätter inte det auktoritativa verksamhetsregistret och tar inte över informationsägarskapet.

### PLS-065 – Dataflöden och datapipelines (PLT-020)

Ger kontrollerad inläsning och transformation. Prova schemaändring, omkörning, dubbletter och data som anländer i fel ordning. Kontrollera att pipeline kan beskriva källversion och transformering; den ansvarar inte för den operativa integrationsprocessen i CAP-IT-06.

### PLS-082 – Datakvalitet och datavalidering (PLT-021)

Ger profilering, kontroller och uppföljning av analytiska dataset. Prova saknade värden, orimliga enheter, sena uppgifter och felaktiga kodlistor. En lyckad schema-validering garanterar inte rätt verksamhetsinnehåll.

### PLS-014 – Sökning och indexering (PLT-014)

Gör godkända källor sökbara med relevansrankning och indexlivscykel. Prova relevans och täckning med kända frågor, men också spärrad åtkomst efter återkallelse, borttagna dokument och föråldrade index. Sökning är inte en verifierad AI-slutsats.

### PLS-018 – Kunskapsretrieval och grounding (PLT-014)

Ger kontrollerad hämtning av underlag för AI-svar. Prova att svar hänvisar till rätt källversion, att en obehörig källa inte läcker via retrieval och att ett relevant men missvisande dokument inte okritiskt accepteras. Grounding är ett stöd för granskning, inte bevis på sanningshalt.

### PLS-017 – Förvaltad LLM-tjänst (PLT-004)

Ger styrd tillgång till tillåtna språkmodeller genom exempelvis gateway och kvoter. Prova kostnadsgränser, modellbyte, hantering av personuppgifter och att ändrade modellversioner upptäcks i utvärdering. Tjänsten äger inte agentorkestrering eller godkännande av verksamhetsbeslut. Ingen egen modellträning behövs för att konsumera en sådan tjänst.

### PLS-019 – Modellutvärdering och AI-regressionstest (PLT-004)

Ger kvalitetstester och uppföljning av relevanta modeller och AI-kedjor. Prova mätningar före/efter modellbyte, representativa felklasser, osäkerhet och hur dåliga utfall stoppas. Användningsfallet avgör om avancerad AI-utvärdering behövs; vanliga rapporter ska inte bedömas med språkmodellmått.

### PLS-016 – Modellserving och ML-inferens (PLT-004)

Ger styrd konsumtion av prediktiva modeller. Prova versionsspårbarhet, svarstider, felhantering och modellens beteende vid förändrad indata. Teknisk tillgänglighet garanterar inte prediktionens verksamhetsmässiga kvalitet.

### PLS-096 – ML-träning och modellfinjustering (PLT-004)

Ger träningsjobb och modelllivscykel för verksamheter som utvecklar eller anpassar modeller. Prova resurstilldelning, reproducerbar experimentbeskrivning, tillåten datatillgång och budgetgränser. Den är inte ett generellt krav för att använda AI-modeller från en extern leverantör.

### PLS-099 – ML feature- och dataserving (PLT-004)

Ger tidskorrekta och återanvändbara indata för modellträning och inferens. Prova att en feature bara använder data som var kända vid prediktionstidpunkten och att träning och drift hanterar samma definition. Det är inte samma sak som ett allmänt semantiskt måttlager.

### PLS-083 – Förvaltad grafdatabas (PLT-003)

Ger lagring och frågor för relationstäta användningsfall. Prova en verklig nätverks- eller beroendefråga och jämför prestanda, förståelighet och förvaltningskostnad med alternativ. Grafdatabas är inget generellt AI- eller generationskrav.

### PLS-074 – Geospatial informations- och karttjänst (PLT-015)

Ger geokodning, kartlager och spatiala analyser där platsinformation behövs. Prova precision, licensvillkor, källstatus och skydd av känsliga positioner. Verksamheten äger platsinformationens betydelse, även om karttjänsten förvaltas centralt.

### PLS-090 – Mediaanalys och innehållsextraktion (PLT-036)

Ger exempelvis tal-till-text, OCR och extraktion av metadata. Prova kvalitet på representativa dialekter, språk, dokumenttyper och bildkvaliteter; dokumentera osäkra resultat, skevheter mellan grupper och möjligheten att korrigera dem. Mät också hur många fel som kräver mänsklig kontroll. Extraktion är inte i sig ett formellt beslut eller en godkänd arkivregistrering.

### PLS-088 – Mediebearbetning och transkodning (PLT-016)

Omvandlar medieformat för faktisk användning. Prova att tidkod, bild- eller ljudkvalitet och relevanta metadata bevaras på överenskommen nivå, att original kan skyddas och att felaktigt resultat upptäcks. Transkodning är inte innehållsförståelse och behövs bara där det finns medieflöden.

## Förflyttningarna mellan generationerna

**G1→G2 – fler källor och tydligare gränser.** Lokala rapporter och sökfunktioner behöver fungera över tjänster, datakopior och ändrade kontrakt. Det gör ägarskap, kvalitetskontroll, versioner och behörighet viktigare. Förflyttningen kräver inte att all analys flyttas till ett enda datalager.

**G2→G3 – från upprepade projekt till förvaltade erbjudanden.** Åtgärda först felaktiga mått, osäkra index och otydligt informationsansvar. Identifiera sedan återkommande, likartade plattformsbehov och erbjud självbetjäning med säkerhet, uppgraderingar, kostnadsuppföljning och avveckling. Organisationens ansvar utvecklas från projektleveranser till produktförvaltade tekniska erbjudanden, utan att verksamhetens definitioner centraliseras till IT.

**G3→G4 – fler användare, samma krav på konsekvensansvar.** Godkända sök-, analys- och AI-byggblock gör det lättare att utveckla nära verksamheten. Men källor, datakvalitet, behörighet och granskningsnivå måste fortfarande kunna styras. Experiment med liten risk kan hanteras enklare än system som påverkar människors rättigheter eller stora ekonomiska värden.

## Diagnostiska prov och beslutsindikatorer

| Fråga | Praktiskt prov | Hur resultatet bör tolkas |
|---|---|---|
| Kan vi förklara ett viktigt nyckeltal? | Följ måttet från godkänd definition via källversion och händelsetid till två rapporter; prova en sen rättelse. | Oenighet om begrepp och omräkningsregler är G2-grundproblem, inte nödvändigtvis fel BI-verktyg. |
| Kan vi återskapa eller förklara en rapport? | Kontrollera källa, tidpunkt, version och transformation samt vad som faktiskt sparats. | Transparens är möjlig även när exakt återspelning inte kan garanteras. |
| Håller sökning rätt säkerhetsnivå? | Återkalla åtkomst, ändra källversion och försök läsa via gammalt index. | Brist kan ligga i sökplattform, integration eller policyverkställighet. |
| Fungerar datakvalitetskedjan? | Inför sent data, schemafel och felaktig måttenhet. | Testet visar om problemet upptäcks före publicering och får en ägare. |
| Behöver flera team samma erbjudande? | Jämför kopierade implementationer, kötid, säkerhetsfel och total förvaltningskostnad. | Gemensam plattform motiveras av upprepning och nytta, inte av generationsnamnet. |
| Klarar vi säker förändring? | Uppgradera pipeline, sökindex eller modell med två verkliga konsumenter. | Verifiera kompatibilitet, kostnad och avveckling, inte bara skapande. |
| Kan AI-resultat granskas? | Testa fel källa, otillåtet dokument, prompt injection i källa, modellbyte och ett trovärdigt men felaktigt svar. | Retrieval, källstöd, svarskvalitet, informationsskydd och beslut måste kontrolleras var för sig. |
| Är kostnaden rimlig? | Belasta typiska rapporter och modellfrågor; mät kvoter och faktiska kostnader. | Överkapacitet och inlåsning kan tala mot en bred gemensam plattform. |

Bedöm indikationer på **behov**, **fungerande stöd**, **olämplig teknik** och **mognad för nästa arbetssätt** separat. När ett verktyg inte fungerar: kontrollera först mätdefinition, datakontrakt, implementation, driftsättning, integration och ansvar. Ett produktbyte är först en av flera åtgärdskategorier.

## Avgränsningar, källor och osäkerhet

**Källmodell:** *Förmågeöversikt – tekniska IT-förmågor* (baseline v1.1), *Plattformsöversikt – konceptuella plattformar* och *Från systemdrift till digital självständighet*. De 16 PLS- och nio PLT-identiteterna och deras stödrelationer kommer från källmodellen. Exempel, tjänstetester och generationsbedömningar är kompletterande arkitekturanalys och ska inte läsas som en nulägesbedömning av en viss organisation.

**Kompletterande referenser:** [Google SRE – Data Processing Pipelines](https://sre.google/workbook/data-processing/); [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org/llm-top-10/); [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework); [NIST AI 600-1 – Generative AI Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence); [Google Cloud – Data Lineage](https://cloud.google.com/discover/what-is-data-lineage); [Microsoft Learn – RAG evaluators](https://learn.microsoft.com/en-us/azure/foundry/concepts/evaluation-evaluators/rag-evaluators). Leverantörsexemplen stödjer begreppen kring spårbarhet och separata evaldimensioner, inte ett krav på dessa leverantörers produkter. NIST AI RMF är frivillig vägledning; en pågående revision ska inte beskrivas som en färdig ny version. G4 är ett scenario med betydande osäkerhet.
