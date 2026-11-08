# Datahantering och informationslagring

De flesta IT-stöd behöver lagra information. Kraven skiljer sig däremot kraftigt: ett ärendesystem behöver tillförlitliga transaktioner, en dokumenttjänst behöver hantera filer, och en gemensam analysmiljö behöver kunna kombinera stora datamängder. Förmågan *Datahantering och informationslagring* ska därför erbjuda förvaltade databas-, lagrings- och datahanteringstjänster anpassade till olika behov, inte en enda teknik för all information.

Förmågan omfattar både IT-stödens egna data och dataplattformar för gemensam användning. En välskött databas löser inte frågor om vem som äger informationen, vilka uppgifter som är auktoritativa eller hur kopior ska hållas förenliga. Plattformarna behöver göra överenskomna ansvar och regler möjliga att följa i praktiken.

## Förvaltad datalagring för IT-stöd

Det grundläggande erbjudandet är ett begränsat och väl underhållet urval av datatjänster, där användningskraven avgör valet. Några viktiga kategorier är:

| Kategori | Typiska behov och avvägningar |
|---|---|
| Relationsdatabaser | Transaktioner, tydliga samband och integritetsregler; ofta ett bra förstahandsval för verksamhetssystem. |
| Dokumentdatabaser | Flexibla, sammansatta informationsobjekt och varierande struktur. |
| Nyckelvärdesdatabaser och cache | Snabba uppslag och tillfälliga data; en cache ersätter normalt inte en auktoritativ datakälla. |
| Grafdatabaser | Frågor som bygger på många och komplexa relationer mellan objekt. |
| Tidsseriedatabaser | Stora flöden av tidsstämplade mätvärden och händelser. |
| Fil- och objektlagring | Dokument, bilder, bilagor och större binära informationsmängder; inte en databasmodell i samma mening som kategorierna ovan. |

Kategorierna är ett sätt att värdera behov, inte en inköpslista. En produkt kan stödja flera datamodeller; exempelvis kan en relationsdatabas även hantera JSON. Specialiserade alternativ bör väljas när kraven motiverar både nyttan och den ökade förvaltningsbördan.

Det gemensamma erbjudandet behöver ange vad varje tjänst faktiskt garanterar och stödjer: transaktions- och konsistensegenskaper, kapacitet, svarstider, dataskydd, tillgänglighet, återställning, versionsstöd, åtkomstkontroll och kostnader. Det bör finnas standardprofiler för vanliga behov och en kontrollerad väg för specialfall. Lagringen under tjänsten – exempelvis block-, fil- eller objektlagring – väljs efter arbetslast och återställningskrav, inte efter vilken generation organisationen eftersträvar.

Utvecklingsteam behöver kunna se belastning, fel och kostnader, ändra sina tillåtna inställningar och hantera schema- och datamigreringar. Datatjänsten ska ge stöd för säkerhetskopiering och återställning i samverkan med *Driftbarhet och motståndskraft*. En återläst databas är dock inte automatiskt förenlig med andra tjänsters samtidiga tillstånd. Det behöver finnas tydliga informationsgränser: delad databasplattform behöver inte betyda delat skrivansvar eller att team får ändra varandras tabeller.

## Dataplattformar för gemensam och analytisk användning

För data som ska kombineras, bearbetas eller historiseras från flera källor kan organisationen erbjuda Data Warehouse, Data Lake eller Lakehouse. Valet beror på datatyper, volym, beräkningsbehov, aktualitet, befintliga investeringar och ekonomi. Flera sådana miljöer behöver inte finnas om en förvaltad lösning uppfyller kraven.

Tjänsteerbjudandet omfattar även kontrollerad inhämtning, ETL/ELT-verktyg, pipelinekörning, schemaläggning, felhantering, kvalitetskontroller, metadata, datakatalog, spårbarhet till källor och publicering av dokumenterade datamängder. ETL och ELT är två ordningar för extraktion, transformation och laddning; de kan stödjas av samma produkt. Publicerade datamängder behöver tydliga kvalitets- och uppdateringsvillkor så att andra team kan använda dem utan att först sätta sig in i varje källsystems struktur.

Dataplattformen kan använda *Integration och informationsutbyte* för transport från källsystem, men ansvarar själv för transformation, kvalitet, historisering och förvaltade datamängder. Sökindex, semantiska analysmått och AI-tjänster erbjuds inom *Analys, sökning och intelligent informationsbearbetning*. En gemensam produkt kan rymma flera av dessa funktioner.

Verksamheten ansvarar för datamängdernas innebörd, kvalitet i sitt sammanhang och tillåtna användning. Dataplattformsteamet erbjuder mekanismer för att registrera ansvar, kontrollera kvalitet och verkställa överenskomna regler. En katalogpost är inte en garanti för att en datamängd är korrekt eller får användas för nya ändamål.

## Generation 3 – från centralt utförande till självbetjänade datatjänster

För operativa databaser innebär generation 3 att utvecklingsteam själva kan etablera, driftsätta, övervaka, förändra och avveckla godkända datatjänster. Plattformsteamet ansvarar för det gemensamma erbjudandets robusthet, uppgraderingar och säkra standarder; produktteamet ansvarar för datamodellen och tjänstens informationshantering. Självbetjäningen måste omfatta den normala livscykeln, inte bara en beställningsportal.

För analytiska data kan förflyttningen vara lika viktig. I en generation 2-miljö sköter ett separat data warehouse-team ibland varje ny datakälla och varje ETL-flöde: från koppling och transformation till driftsättning, felsökning och senare förändringar. Teamet kan vara mycket kompetent men blir en obligatorisk kö för alla nya behov.

I generation 3 blir det centrala teamets främsta erbjudande i stället en självbetjänad dataplattform: godkända anslutningar och mallar, pipelineverktyg, automatiserad körning, versionshantering, testning, loggar, kostnadsuppföljning och publiceringsregler. Behöriga data- och utvecklingsteam kan själva skapa och förvalta standardiserade dataflöden, medan plattformsteamet förvaltar körmiljön, gemensamma skydd och specialiserat stöd. Ett centralt team kan fortfarande förvalta gemensamma datamodeller eller särskilt komplexa flöden. Målet är att undvika obligatoriskt centralt utförande av varje normal förändring, inte att fördela specialistarbete på alla team.

## Generation 4 – lagring utifrån verksamhetens behov

När medarbetare själva skapar rapporter, AI-assistenter och mindre applikationer behöver de i första hand tillgång till godkända, beskrivna datamängder. Dataförmågan publicerar användningsvillkor, kvalitet och aktualitet; *Integration och informationsutbyte* kan tillhandahålla den godkända anslutningen och *Utveckling och teknisk leverans* den miljö där lösningen byggs och delas. En rapport eller assistent behöver inte automatiskt egen datalagring. Datamängdernas källa, ansvarig, aktualitet och användningsvillkor ska framgå; direktåtkomst till produktionsdatabaser eller fristående kopior av känslig information ska inte vara standardvägen.

För lösningar som behöver lagra egna data bör verksamheten inte förväntas välja databastyp eller underliggande infrastruktur. I stället behöver förmågan erbjuda behovsstyrd självbetjäning. Medarbetaren, eller den godkända AI-stödda utvecklingsmiljön, beskriver vilken information som ska hanteras, hur den används och vilka krav som gäller exempelvis känslighet, datamängd, svarstid, tillgänglighet och bevarande. Erbjudandet översätter dessa behov till en rekommenderad eller automatiskt tilldelad lagringstjänst inom organisationens godkända tjänsteprofiler. AI kan stödja behovsbeskrivningen, men får inte självständigt fastställa informationsklassning eller kritiska skyddskrav.

För enklare lösningar kan lagringsprofilens etablering, kapacitetsgränser, kostnadsuppföljning och avveckling automatiseras. Krav som överskrider godkända profiler behöver specialistbedömning; lösningens generella överlåtelse och publicering hanteras i den gemensamma leveransvägen.

Nya databaskategorier är alltså inget generationskrav. Skillnaden är att lagring kan tilldelas efter uttryckta behov, med stöd av förmågorna *Identitet och tillit* och *Cybersäkerhet och tekniskt skydd* för behörighet och skydd.
