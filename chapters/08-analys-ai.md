# Analys, sökning och intelligent informationsbearbetning

Denna gemensamma IT-förmåga ska erbjuda återanvändbara tjänster för sökning, analys och BI samt AI. De tre områdena har olika uppgifter: sökning återfinner information, analys beräknar och presenterar data, medan AI exempelvis kan klassificera, förutsäga, tolka eller generera innehåll. De kan kombineras i en lösning, men behöver inte använda samma plattform eller förvaltas som ett enda tekniskt system.

Förmågan ska erbjuda användbara tjänster med dokumenterade gränssnitt och tydligt förvaltningsansvar. Säkerhet, identitet, datalagring och integration tillhandahålls delvis av andra gemensamma förmågor; här beskrivs vad som specifikt behövs för sökning, BI och AI.

## Sökning och informationsåtervinning

En gemensam sökförmåga bör erbjuda indexering, sök-API:er och relevansfunktioner för dokument, ärenden och andra informationsmängder. Det innefattar anslutning till godkända informationskällor, tolkning av format och metadata samt uppdatering eller borttagning av indexerat innehåll. Indexering skapar en sökbar representation av källinformationen; den ersätter inte dataplattformens ETL/ELT-flöden för att bygga förvaltade datamängder. Team behöver kunna skapa och konfigurera sökindex utan att administrera sökmotorernas underliggande infrastruktur.

Beroende på behov kan tjänsten erbjuda filtrering, nyckelordssökning och semantisk eller vektorbaserad sökning. Mätning av träffkvalitet och svarstider behövs för felsökning och förbättring.

Behörighet är en del av söktjänstens kontrakt. Index, träfflistor, utdrag och cache får inte exponera information användaren saknar rätt till. Sökförmågan behöver därför stödja behörighetsfiltrering och uppdaterade åtkomsträttigheter i samverkan med identitets- och datatjänsterna.

## Analys, BI och rapporttjänster

Den gemensamma analysförmågan bör erbjuda fråge- och beräkningstjänster, anslutningar till datakällor, semantiska modeller, måttdefinitioner samt verktyg för visualisering och rapportering. Till detta hör rapportpublicering, schemalagda uppdateringar, distribution, behörighetsstyrning och uppföljning av användning och fel. Team ska kunna sätta upp en rapportlösning eller analysmiljö utan att själva etablera och drifta en BI-plattform.

Tjänsterna ska stödja återanvändning av godkända mått och begrepp. Plattformen tillhandahåller stöd för semantiska modeller, versionshantering och publiceringskontroller. Verksamheten fastställer måttens betydelse och ansvarar för deras riktighet, medan rapportägaren ansvarar för presentation och användning. Dataplattformen ansvarar separat för att publicerade datamängder uppfyller överenskomna leverans- och kvalitetsvillkor.

Erbjudandet behöver stödja såväl gemensam uppföljning och självbetjänad BI som reglerad rapportering och operativa rapporter nära verksamhetssystemen. Krav på aktualitet, spårbarhet och publiceringskontroll skiljer sig åt. All rapportering ska inte behöva passera ett centralt datalager.

Förmågan använder förvaltade datamängder från *Datahantering och informationslagring* och erbjuder själv frågetjänster, semantiska analysmått och rapportpublicering. Tekniken kan vara gemensam utan att informations- och analysansvaret sammanfaller.

## AI och intelligent informationsbearbetning

AI har länge använts för exempelvis klassificering och prognoser. Generativ AI med språkmodeller, assistenter och agenter ställer ytterligare krav. Erbjudandet behöver därför stödja både traditionell maskininlärning och generativ AI, utan att allt måste samlas i en produkt.

Modeller som förvaltad tjänst. Förmågan bör erbjuda godkänd modellåtkomst via API eller AI-gateway, med modellval, versioner, kvoter, kostnadsuppföljning och regler för data till externa leverantörer. För maskininlärning kan även modellregister och modellövervakning behövas. Gemensam åtkomst kräver inte att IT tränar eller driver egna språkmodeller. Tillämpliga rättsliga krav måste bedömas för den konkreta användningen, inklusive vem som tillhandahåller respektive använder AI-systemet och vilken riskklassning som gäller. EU:s AI-förordning införs stegvis; att en lösning använder generativ AI säger i sig inte vilka särskilda krav för högrisk-AI som gäller. [K012]

Kunskap och kontext till AI. Godkända kunskapsanslutningar, indexering och behörighetsstyrd hämtning gör det möjligt att ge modeller relevant underlag. Vid *retrieval-augmented generation* (RAG) återanvänds söktjänsten för att hämta underlag till en generativ modell. Sökresultat och modellens svar behöver kunna kontrolleras var för sig; modellåtkomst ger inte rätt till alla dokument.

Assistenter, verktyg och agenter. Förmågan bör erbjuda återanvändbara instruktioner, skills och tjänster för att konfigurera och köra AI-assistenter och agenter. De kan använda godkända verktyg från *Integration och informationsutbyte*; verktygens faktiska åtkomst måste kontrolleras utanför modellens instruktioner. AI-förmågan erbjuder beteendeutvärdering, inte egna alternativa verksamhetsmandat.

Utvärdering och driftbarhet. Gemensamma tjänster bör stödja testfall, utvärdering av svar och verktygsanrop, jämförelser mellan modell- och promptversioner samt uppföljning av kvalitet, fel och kostnader. Spårning ska vara användbar utan onödig lagring av känsligt innehåll. Risker som *prompt injection*, felaktiga svar och otillåtna agentåtgärder kräver tekniska kontroller och löpande tester. Verktygsbehörigheter, isolering och godkända anslutningar minskar konsekvenserna men eliminerar inte risken att en modell följer instruktioner i obetrott material. Särskilt åtgärder med stora eller svåråterkalleliga följder behöver begränsningar, verifierbara villkor och vid behov mänsklig prövning. [K003, K004]

## Generation 3 – självbetjäning för utvecklingsteam

I generation 3 är sökindex, BI-miljöer och AI-tjänster förvaltade interna produkter med dokumenterade gränssnitt, automatiserad etablering, mätvärden och stöd för förändring och avveckling. Ett utvecklingsteam ska till exempel kunna skapa ett sökindex, ansluta en godkänd datamängd eller använda en modell, övervaka lösningens beteende och felsöka den utan att plattformsteamet behöver utföra varje normalt arbetsmoment.

Plattformsteamet ansvarar för att de gemensamma tjänsterna fungerar och utvecklas. Utvecklingsteamet ansvarar för hur de används i den egna sökfunktionen, rapporten eller AI-applikationen. Det som tillkommer jämfört med en traditionell central teknikmiljö är ett erbjudande utformat för andras självständiga livscykelansvar, inte bara en snabbare beställningsväg.

## Generation 4 – självbetjäning för verksamhetens egna lösningar

I generation 4 behöver sök-, BI- och AI-funktioner kunna erbjudas även genom verktyg som verksamheten kan använda utan professionell programmering: rapportbyggare med godkända mått, sökbara kunskapssamlingar och assistentbyggare med styrda dokumentanslutningar och skills. De återanvänder normalt förvaltade data och sökindex. Skapande- och publiceringsmiljön behöver samverka med *Utveckling och teknisk leverans*, medan godkända verksamhetsåtgärder och anslutningar kommer från *Integration och informationsutbyte*. Förmågan ska särskilt ge stöd för att:

- Konfigurera sök-, rapport- eller AI-beteende och ansluta godkända informationskällor utan att administrera plattformstekniken.
- Bedöma sökträffar, rapportresultat och AI-svar med lämpliga tester, inklusive felaktiga svar och otillåtna verktygsanrop.
- Följa kvalitet, användning och kostnader för den skapade sök-, BI- eller AI-funktionen över tid.

För en verksamhetsskapad assistent erbjuder denna förmåga dokumentindex, modellåtkomst och AI-specifik utvärdering. Allmän publicering och förvaltning av lösningen hanteras i den gemensamma leveransvägen, medan åtgärder i verksamhetssystem använder godkända integrationsfunktioner.
