# Redaktionell canon – godkänd inriktning

1. Faktabok om IT:s roll som möjliggörare, inte produktkatalog.
2. G1/G2 introducerar behov och igenkänning; G3/G4 ges betydande utrymme.
3. G3 = förvaltade självbetjänade plattformsprodukter; G4 = bredare digital handlingskraft inom säkra gemensamma ramar.
4. G4 måste konkretisera AI-assistenter, agenter och AI-stödda verksamhetsskapade applikationer.
5. Förmåga ≠ plattform ≠ plattformstjänst ≠ IT-stöd.
6. Viktig funktion ≠ krav på central plattform; teknikbyte är aldrig automatiskt rätt.
7. Brister som måste åtgärdas i G2 skiljs från motiv att bygga G3-tjänster.
8. Verksamheten äger verksamhetsregler och informationsanvändning; IT och plattformsteam har tydliga tekniska och livscykelansvar.
9. Alla generationer kan samexistera; G4 ersätter inte professionellt utvecklade kärnsystem.
10. Hänvisa inte till någon namngiven myndighet; använd fiktiva och generiska verksamhetsexempel.
11. Gemensamma definitioner förklaras bara en gång; förmågekapitel måste tillföra unik nytta.
12. Dokumentera om ett påstående kommer från källmaterial, redaktionell analys eller extern verifiering.


## Redaktionell grundregel

G1 och G2 används främst för igenkänning. G3 och G4 ska konkretisera förflyttningen, inklusive AI-assistenter, agentautomation och AI-stödd applikationsutveckling. Teknik är ett medel, inte bokens huvudperson.

## Beslut r0010 – dataplattform respektive analys/BI

- CAP-IT-04 beskriver datans tekniska grund: warehouse, lake, lakehouse, datamängder, ingestion, transformation, lagring, metadata, datakvalitet och livscykel.
- CAP-IT-05 beskriver användningstjänster: fråge- och beräkningsfunktioner för analys, BI-plattform, semantiska mått, visualisering, rapportpublicering, sökning och AI. Frågemotorer och semantik kan finnas i samma produkt som lagringen: teknisk produktgräns är inte automatiskt förmågegräns.
- Informationsansvariga beslutar om begrepp och godkända mått; plattformsteam ansvarar för gemensamma tjänster; respektive rapport-/produktteam ansvarar för rapportens innehåll och kvalitet.
- Operativa rapporter ska inte tvingas genom centralt warehouse; val styrs av aktualitet, belastning, spårbarhet och konsistens.
- Kapitel 07 är ännu inte skrivet. Vid författande ska gränsen speglas där utan att BI-kapitlets beskrivning upprepas.

## Beslut r0011 – tre delområden inom CAP-IT-05

- CAP-IT-05 behålls som paraply men har tre avgränsade delområden: (1) sökning/informationsåtervinning; (2) analys, BI och rapporttjänster; (3) AI, inklusive äldre ML och nyare generativ AI/assistenter/agenter.
- Sökning hittar källinnehåll; BI beräknar och presenterar samband och mått; AI predikterar, klassificerar, tolkar eller genererar. Lösningar kan kombinera dem (t.ex. RAG) utan att förmågorna sammanfaller.
- G3: professionella team självständiga i hela livscykeln genom gemensamma plattformstjänster. G4: även verksamhetens medarbetare kan skapa/anpassa egna digitala hjälpmedel. Detta är **bokens syntes**, inte officiell CNCF-/Microsoft-generationsmodell.
- Historik: sökning/BI länge etablerade; även AI är äldre, medan brett tillgänglig generativ AI och AI-assisterat skapande är nyare.
- CAP-IT-04/CAP-IT-05-gränsen från r0010 gäller fortsatt; dataplattform och BI/AI kan samexistera i en produkt.
- Kapitel 07 ska inte upprepa detaljbeskrivningen av BI, sökning eller AI; hänvisa kort till deras konsumtion av datatjänster.

## Redaktionell tjänsteprincip – beslut r0012

- Förmågekapitel ska i första hand beskriva **vad den gemensamma IT-förmågan erbjuder**: konkreta återanvändbara tjänster, gränssnitt, egenskaper, livscykelstöd och ansvar.
- Därefter beskrivs kort hur erbjudandet skiljer sig mellan specialistförvaltad teknik i G2, självbetjänade tjänster för professionella team i G3 och tillgängliga byggverktyg för verksamheten i G4.
- Användningsexempel ska illustrera behov, inte ersätta tjänstebeskrivningen eller bli instruktioner för verksamhetens arbetsprocess.
- Beskriv CAP-IT-05 i tre separata delområden: sökning; analys/BI; AI (inklusive ML och generativ AI). RAG är ett samspel mellan sökning, datatjänster och AI, inte en sammanslagning av dem.
- CAP-IT-04 ansvarar primärt för warehouse, lake, lakehouse, datalagring, ingestion, transformation och metadata. CAP-IT-05 ansvarar för sök-, analys-/BI- och AI-funktionerna ovanpå; produktgränser och förmågegränser behöver inte sammanfalla.
- Ingen generell procentsats eller produktkatalog är ett mål i sig; prioritera konkretion och koncentration.

## Redaktionell generationsfördjupning – r0013

- G3 i förmågekapitel: konkret erbjudande för professionella teams hela livscykel, inklusive självbetjäning, felsökning och avveckling.
- G4: beskriv vad som måste tillkomma i **erbjudandet**, inte bara möjliga användningsfall. Använd skapandets livscykel: skapa, ansluta, prova, publicera/dela, förvalta/avveckla.
- Visa en kort jämförelse av samma behov i G3 respektive G4 där det klargör skillnaden; undvik att repetera kapitel 2:s motiv.
- Tjänster överlappar andra förmågor: identitet, integration, driftbarhet och säkerhet återanvänds, beskriv inte nya dubblerade plattformar.

## Redaktionell princip r0014
- Förmågekapitel: konkret, förmågespecifikt tjänsteerbjudande först; generationsskillnader kort och utifrån tillgänglighet och ägarskap. Undvik att upprepa hela skapandelivscykeln i både lista, exempel och slutsats.
- Separera datahantering (CAP-IT-04), BI/sök/AI (CAP-IT-05) och identitets-/integrationstjänster efter funktion och ansvar, inte leverantör eller produkt.

## Hänvisningar till andra förmågor i läsarmanuset (r0015)
- Skriv ut förmågans namn i löptexten i stället för interna CAP-IT-ID:n, exempelvis "förmågan *Datahantering och informationslagring*". Kursivera enbart förmågenamnet vid korshänvisningen.
- Vid upprepad hänvisning inom samma stycke, använd hellre "den förmågan" eller en kort, entydig benämning än att upprepa hela namnet.
- Förmågekoderna behålls i projektets YAML-modeller, underlagsregister, granskningsnoteringar och andra interna spårbarhetsfiler.
- Inför slutexport: kontrollera att inga CAP-IT-koder förekommer i exporterade manuskapitel, inklusive rubriker och bildtexter.

### Redaktionell förtydligande r0017 – datatjänster
Beskriv databas- och lagringsmodeller som möjliga tjänstekategorier, inte som obligatoriska produkter för en generation. Skilj mellan teknikval utifrån arbetslast och graden av självbetjäning. Beskriv ETL/ELT som dataplattformens inhämtning och bearbetning, och systemöverföringsmekanismer under *Integration och informationsutbyte*.

## Redaktionell typografiregel – r0018

- Använd rubriknivåer, styckeindelning och precisa formuleringar för struktur i löpande boktext. Undvik fetstil som retorisk betoning av ord, uttryck eller hela meningar.
- Förmågenamn i korshänvisningar skrivs fortsatt kursivt, enligt regeln från r0015. Kursiv stil används inte som allmän markör för viktiga resonemang.
- Tabeller, listor och textavsnitt ska fungera utan typografisk betoning. Vid behov används en kort underrubrik i stället för upprepad framhävning.
- Källmaterial, YAML-modeller och interna granskningsdokument berörs inte av typografiregeln.

### Redaktionell princip r0019 – behovsstyrd tjänstetilldelning
I generation 4 beskriver verksamheten informationsbehov och kvalitets-/skyddskrav; den gemensamma dataförmågan rekommenderar eller etablerar en godkänd lagringstjänst. Verksamheten ska inte förväntas välja databasteknik. Automatisering gäller normalfall, medan högre risk eller avvikande krav prövas av ansvariga specialister. Skilj alltid mellan verksamhetens behov, teknikrekommendation och formellt skyddsbeslut.

### Gränsdragning integration/data och G4-anslutningar – r0021
- Integration erbjuder systemutbyte: API, köer, händelser, fil, externa anslutningar och kontraktslivscykel.
- Datahantering erbjuder förvaltade datamängder, ETL/ELT, transformation och datapipelinekörning. Transportmekanism och databearbetning kan finnas i samma produkt men har olika funktionellt ansvar.
- Generation 3: standardiserade och självbetjänade integrationstjänster för professionella teams hela livscykel.
- Generation 4: begripliga, godkända funktioner och anslutningar utifrån verksamhetens avsikt; läsmandat skiljs från åtgärdsmandat, med betrodda kontroller.

### Beslut r0022 – gemensam skapandemiljö och tjänsternas ansvar
- *Utveckling och teknisk leverans* erbjuder i G4 godkända skapande-, test-, versions-, publicerings-, överlåtelse- och avvecklingsvägar för verksamhetsskapade lösningar. Förmågan har ännu inget färdigt bokkapitel: detta beslut ska prövas vid författandet.
- *Integration och informationsutbyte* erbjuder upptäckbara och godkända verksamhetsfunktioner/anslutningar, kontrakt, mandatbegränsning och spårbar systemåtkomst. Skapandemiljön återanvänder dem; integration är inte en parallell applikationsbyggare.
- *Analys, sökning och intelligent informationsbearbetning* erbjuder sök-, BI- och AI-funktionernas specifika byggblock, konfiguration, utvärdering och driftinsyn.
- *Datahantering och informationslagring* ansvarar för förvaltade datamängder, dataflöden och behovsstyrd lagring; publicerade datamängder är inte samma sak som en integrationsanslutning.
- Ägarskapet för verksamhetsbeslut och datans innebörd ligger kvar i verksamheten; behörighet och kontroll av agentåtgärder kan inte delegeras till AI-instruktioner.
- De fyra förmågorna kan paketeras i en och samma produkt eller portal. Beskriv funktionellt ansvar, inte produktgränser.

### Förmågegräns och tjänsteerbjudande r0023
- *Utveckling och teknisk leverans* ansvarar för utvecklings- och skapandemiljöer, kvalitetskontroller, versionshantering, bygg, test, godkänd publicering, överlåtelse och avveckling av lösningar.
- G3: gemensam utvecklarprodukt för hela professionella teams leveranslivscykel; automatiserad standardväg utan att plattformsteamet äger varje applikationskod.
- G4: kontrollerade skapandemiljöer för verksamhetsskapade lösningar med stöd för skapa, ansluta, prova, publicera och förvalta/avveckla; riskstyrt och behovsstyrt, inte en obligatorisk teknikprodukt.
- Körmiljö, datalagring, integrationsanslutningar, AI-modelltjänster, identitet, säkerhet och produktionsdriftbarhet förblir separata förmågor, även när de syns i en gemensam portal.

### Redaktionellt beslut r0024 – utvecklings- och leveransförmågan
- Utvecklingsplattformen tillhandahåller skapande-, test-, leverans- och ändringsvägar, men äger inte all körmiljö och driftövervakning.
- G3 mäts i utvecklingsteamens möjlighet att genomföra normal leveranslivscykel utan överlämningskö.
- G4 bygger på en begriplig skapandemiljö och riskanpassade publiceringsvägar: personligt experiment, delad lösning och skyddsvärd/kritisk lösning. Risk, inte skaparens yrkesroll, styr kontrollnivån.
- Verksamhetsskapade lösningar behöver kunna få nytt ägarskap och vid behov professionell förvaltning; tekniköverlämning garanterar inte att omarbetning är onödig.

### Redaktionell gräns r0025 – AI och publicering
- Analys-/AI-förmågan erbjuder AI-specifik testning och utvärdering; utvecklings- och leveransförmågan avgör hur utvärderingsresultaten används som kontroller i publiceringsflödet.
- En BI-tjänsts publicering av en rapport är inte samma sak som leverans av en verksamhetsapplikation.
- Utvecklingsplattformen kan samordna livscykelupplevelsen utan att äga datatjänster, integrationer, exekvering eller driftbarhet.
- G4-lösningens risknivå behöver kunna omprövas under dess livslängd; överlämning till professionell förvaltning kan kräva teknisk omarbetning.

### Körmiljö och ansvar – r0026
- Applikationsexekvering och körmiljö erbjuder teknisk exekvering och förvaltade arbetslastprofiler, inte byggkedja, applikationsfunktion eller allt operativt ansvar.
- G3 gör etablering, förändring, felsökning och avveckling av godkända arbetslaster självbetjänade för professionella team.
- G4 låter godkända skapandemiljöer beskriva exekveringsbehov som leder till val av körprofil; verksamhetsmedarbetaren ska normalt inte välja VM, container eller runtime.
- Inte alla verksamhetsskapade lösningar kräver egen körmiljö; godkänd SaaS kan tillhandahålla den.

### Redaktionell precisering r0027 – körmiljö/driftbarhet
- Körmiljöprofiler beskriver stödda arbetslaster, resursramar, tjänstenivåer och tekniskt plattformsansvar. De ger driftstatus och mätvärden till förmågan Driftbarhet och motståndskraft, men omfattar inte själv hela incident- och återhämtningsförmågan.
- G4:s behovsstyrda exekvering utgår från användning och risk; kontinuerlig och händelsestyrd körning är olika exempel. Risknivåbeslut och publiceringsvägar definieras inte på nytt i körmiljökapitlet.

### Redaktionell precisering r0028 – driftbarhet
- Körmiljöplattformen producerar driftssignaler och exekveringskontroller; driftbarhetsförmågan erbjuder gemensam analys, åtgärdbara larm, incidentstöd och prövad återhämtning.
- G3: självbetjänade driftbarhetstjänster för produktteam med bibehållet helhetsansvar vid tvärgående incidenter. G4: riskanpassat, begripligt standardstöd till verksamhetsskapade lösningar – inte driftteknikerkompetens som inträdeskrav.
- AI-beteendeutvärdering ligger i analys/AI, men avvikelser kan ge signaler till driftbarhet. Ändringar i externa system kan kräva avstämning/kompensation utöver teknisk återställning.

### Redaktionell precisering r0029 – körmodeller
- Körmiljöförmågan kan erbjuda VM/applikationsservrar, containerkörning, PaaS, serverlös/händelsestyrd körning, batch och specialiserad AI-exekvering. Kategorierna överlappar och är inga obligatoriska plattformsval.
- Körmiljöer bakom data-, AI- och integrationstjänster kan vara dolda för tjänstens konsument. Respektive specialistförmåga äger sin funktion, körmiljöförmågan de exekveringstjänster den faktiskt erbjuder.

### Ansvarsgräns r0030 – leverans, körning och driftbarhet
- Leveransplattformen möjliggör test, release och ändringar; den garanterar inte applikationens funktion eller återhämtning.
- Körmiljön erbjuder teknisk exekvering och signaler, men inte ensam verksamhetskontinuitet.
- Datatjänster kan sköta sin säkerhetskopiering; driftbarhetsförmågan behöver möjliggöra och verifiera återhämtning på tjänste- och flödesnivå.
- Kompensation för utförda verksamhetsåtgärder utformas av verksamhets- och applikationsansvariga med stöd av integrationens mekanismer.

### Ansvarsgräns r0031 – identitet och delegation
- Identitet och tillit erbjuder mänsklig autentisering, federation, arbetslastidentitet, hemligheter, certifikat samt gemensamt auktorisationsstöd. Det skyddade verksamhetssystemet måste verkställa sina verksamhetsrättigheter.
- Generation 4:s assistenter och agenter behöver avgränsade, spårbara mandat; inte nödvändigtvis ett permanent eget användarkonto per agent. Integrationsverktyg ger åtkomst till funktionerna men kringgår inte resursens kontroll.

### Gräns för processförmågan – r0037
- Processförmågan tillhandahåller beständiga flöden, ärendekontext, mänskliga uppgifter och notifiering; den äger inte verksamhetsbeslut, API-transporter eller identitetskontroller.
- G3 möjliggör självbetjäning och kontrollerad versionering av pågående instanser; G4 ger verksamhetsnära processbyggstenar genom godkända skapandemiljöer utan att tekniska kontrollgränser försvinner.

### Samgranskning process/integration – r0038
- Integration förmedlar meddelanden/anrop med tekniska leverans- och felhanteringstjänster; processförmågan samordnar processinstanser, väntan, steg och mänskliga uppgifter.
- Mottagande verksamhetssystem äger auktoritativa data och kontrollerar tillåtna åtgärder. Verksamheten äger processens beslut.
- En kvittens är inte liktydig med att ett processsteg eller en verksamhetsåtgärd är genomförd.

### Förtydligande generation 4 för processförmågan – r0039
- Verksamheten ska själv kunna utforma, prova/simulera, publicera, följa upp, ändra och avveckla normala ärendeflöden genom godkända verktyg.
- Risk och användning styr behov av granskning och professionellt stöd; inte ett generellt IT-godkännande för varje justering.
- Utvecklingsförmågan erbjuder gemensam skapande- och publiceringsväg; processförmågan erbjuder själva processtjänsterna, inklusive långlivade instanser och mänskliga uppgifter.

### Förtydligande generation 3 för processförmågan – r0040
- En gemensam ärendehanteringsplattform räcker inte om varje processtillägg genomförs av ett centralt team.
- I generation 3 kan professionella utvecklingsteam själva konfigurera, testa, driftsätta, övervaka och förändra sina ärendeflöden inom kontrollerade ramar; plattformsteamet levererar självbetjänad processtjänst och förvaltar gemensam teknik.
- Processägaren äger verksamhetslogiken; teamägda ändringar får inte obehörigen påverka gemensamma komponenter eller andra team.

## Redaktionell harmoniseringsnorm – r0047

- Varje förmågekapitel anger sitt eget tjänsteerbjudande och konkreta självbetjäning i G3/G4, inte en fullständig katalog över grannförmågornas ansvar.
- Kapitel 03 definierar förmåga, plattform, självbetjäning och generationsprinciper. Kapitel 13 beskriver den generella skapande-, test-, publicerings-, överlåtelse- och avvecklingsvägen.
- Kapitel 04 äger gränssnitt, formulärkomponenter och kanalutskick; 05 äger processinstanser, tidsgränser och att utlösa påminnelser; 06 äger uttryckliga regler, giltighet och regelresultat.
- Kapitel 07 äger datalagring, datamängder och ETL/ELT; 08 äger sökindex, semantiska analysmått och AI/agenttjänster; 09 äger API-/meddelandekontrakt och anropsmekanismer.
- Kapitel 10 erbjuder tekniska identiteter och mandatmekanismer; 12 erbjuder skydd, säkerhetsdetektion och säkerhetskontroller. Verksamhetens system ansvarar för sina åtkomst- och beslutsregler.
- Kapitel 14 äger exekveringsprofiler; 15 nätverkets tekniska trafikvägar; 16 observabilitet och samordnad återhämtning. Samma tekniska produkt kan stödja flera förmågor.
- Behåll nödvändiga säkerhetsdistinktioner och G4:s faktiska möjlighet att utforma, prova, publicera och förvalta egna formulär, flöden och regler. Korta bara generiska upprepningar.
