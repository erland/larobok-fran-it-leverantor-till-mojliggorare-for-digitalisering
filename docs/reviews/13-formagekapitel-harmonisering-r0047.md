# Samordnad redaktionell harmonisering – samtliga 13 förmågekapitel (r0047)

**Underlag:** samgranskningsrapport r0046, samtliga manuskapitel 04–16, kanonisk bokinriktning och kapitel 03.  
**Typ av revision:** redaktionell koncentration och terminologisk harmonisering, utan ändring av förmågeindelning eller källmodeller.  
**Status:** redaktionellt granskad arbetsrevision; ingen oberoende teknisk eller juridisk faktagranskning.

## Samlad bedömning och redigeringsbeslut

Samgranskningen r0046 fann inte någon grundläggande motsägelse i modellen. Den största svagheten var ackumulerad upprepning. Därför har denna revision inte försökt skriva om förmågorna från början, utan reducerat generiska gränsutläggningar och gjort de kvarvarande formuleringarna mer förmågespecifika. De 13 tjänsteområdena och skillnaden mellan generation 3 och generation 4 består.

### 1. Vem äger vad?

| Kapitel | Behållen huvudsaklig tjänst | Förtydligad gräns / minskad upprepning |
|---|---|---|
| 04 Interaktion | Formulärkomponenter, klientupplevelse, kanalutskick | Publiceringsmodellen förklaras en gång i 13; verksamhetssystem prövar åtgärdsrätt |
| 05 Process | Processinstanser, väntelägen, mänskliga uppgifter, processversion | Regel- och integrationskedjan förkortad, processägarens ansvar kvar |
| 06 Regler | Regelmodeller, simulering, giltighet, regelresultat | Längre katalog över integrations-, identitets- och processansvar ersatt med kärngräs |
| 07 Data | Lagring, dataflöden, katalog, datamängder | Transport respektive sök/semantik avgränsas kort, generell överlåtelse kortad |
| 08 Analys/AI | Sökindex, semantiska modeller, BI och AI-utvärdering/agentstöd | Skiljer AI-beteende från mandat och generella releaseflöden, utan full kedjeupprepning |
| 09 Integration | API:er, kontrakt, meddelanden och verktygsanrop | Publicerings- och identitetskedjan förkortad, mottagarens prövning kvar |
| 10 Identitet | Tekniska identiteter och tekniska mandatmekanismer | Gränsparagraf kondenserad utan att förlora skillnaden mot verksamhetsbehörighet |
| 11 Klient | Enhetsprofiler, klientdistribution, lokala data och sessioner | Agentmandatsförklaring koncentrerad till klientens specifika kontroller |
| 12 Cybersäkerhet | Skydd, sårbarheter, säkerhetsdetektion och kontroller | AI-riskkontroller kvar, lång kedja över AI/integration/identitet kortad |
| 13 Utveckling | Generell väg för skapa, testa, publicera, överlåta och avveckla | Kortare gränslista; kapitlet kvar som kanonisk hemvist för leveransmodellen |
| 14 Körmiljö | Körprofiler, exekvering, resursisolering | Överlapp mot utveckling och driftbarhet kondenserat |
| 15 Nätverk | DNS, konnektivitet, segmentering, trafikpolicy | Enhetlig G3/G4-struktur; G2-perspektivet behålls utan ensam extra huvudrubrik |
| 16 Driftbarhet | Observabilitet, incidentstöd, återställningssamordning | Förkortad slutlig ansvarsinventering, teknisk och verksamhetsmässig kontinuitet kvar |

### 2. Gemensamma principer – en tydligare huvudplats

- Kapitel 03 förklarar nu uttryckligen att självbetjäning i generation 3 inte är ett nytt formulär till en manuell specialistkö och att teknisk publiceringsrätt inte automatiskt medför verksamhetsmandat.
- Kapitel 13 behåller normalmodellen för personligt experiment, delad lösning och verksamhetskritisk lösning, inklusive överlåtelse och avveckling. Den generiska modellen upprepas inte fullständigt i övriga kapitel.
- Kapitel 04–06 behåller uttryckligen möjligheten för professionella utvecklingsteam i G3 och verksamhetens medarbetare i G4 att **själva utforma, prova, publicera och vidareutveckla** relevanta gränssnitt, flöden och regler. Detta är förmågespecifik konkretisering, inte en duplicerad plattformsprocess.

### 3. Särskilt granskade beroenden

**04–05–06:** Formulärfunktioner respektive placering i process, enskild regelversion respektive processinstans och skillnaden mellan teknisk publicering och verksamhetsbeslut är bevarade. Endast upprepade sammanfattningar är kortade. Processversioner och hantering av pågående ärenden finns fortfarande i 05, regelgiltighet och historiska utfall i 06.

**07–08–09:** Datahanteringens ETL/ELT, kvalitet och publicerade datamängder skiljs från integrationens transportmekanismer och analysförmågans sökindex, semantiska mått och AI. Ingen ny central plattform föreslås.

**08–09–10–12–13:** AI-förmågan erbjuder agent-/modelltjänster och utvärdering; integration erbjuder godkända anropsgränssnitt; identitet erbjuder mekanismer för att styrka aktörer och avgränsa mandat; cybersäkerhet erbjuder skydd och hotdetektion; utveckling erbjuder den generella leveransvägen. Betrodda verksamhetstjänster prövar själva vilka åtgärder som tillåts. Vissa korta påminnelser finns kvar där de är säkerhetsmässigt väsentliga.

**09–12–14–15–16:** Felsökning av ett API, säkerhetsdetektion, körmiljöns driftssignaler, nätnåbarhet och gemensam observabilitet är olika funktioner. Revisionen koncentrerar gränsstyckena utan att slå samman ansvaren; logginsamling och samordnad incident-/återställningsförmåga ligger kvar i 16.

### 4. Struktur och läsrytm

- Generation 3 och 4 har nu samma rubriknivå (H2) genom förmågedelen och samma typ av tankstreck.
- Det tidigare separata G2-avsnittet i kapitel 15 har blivit ett inledande perspektiv före G3, med innehållet bevarat.
- Undantag motiverade av särskild teknik (offlinearbete, långa processinstanser, äldre regelgiltighet, externa SaaS-kontroller, verifierad återställning) har inte kortats bort.
- Ingen omstrukturering av 13-kapitelsmodellen, inga nya tekniska produktkrav och ingen uppdelning i 13 plattformsteam har gjorts.

## Kvarstående risker och redaktionella kontrollpunkter

1. Korta gränssatser om tekniska garantier behöver ibland återkomma för att kapitlen ska kunna läsas var för sig. Total eliminering vore sämre för förståelsen.
2. Begrepp som *tekniskt mandat*, *verksamhetsbeslut*, *processinstans* och *regelversion* kan få ett gemensamt register inför slutredigering.
3. Det återkommande ärende-/agentexemplet kan samlas till ett referensfall i kapitel 17, som ännu inte är skrivet; denna revision skapar inte ett sådant kapitel i förtid.
4. En oberoende sak- och rättslig kontroll av bland annat behörigheter, informationshantering, tillgänglighet och konsekvenser av automatiserade beslut återstår.
5. Formellt kapitelgodkännande återstår. R0047 markerar inte någon oberoende granskning som genomförd.

## Verifiering och spårbarhet

Revisionens diff, ordmängder och berörda filer listas i projektets `docs/reviews/` och revisionslogg. Ursprungliga `docs/kallmaterial` och YAML-modeller är oförändrade. Valideringen kontrollerar även frånvaro av interna CAP-koder i löpande manus och intakta samtliga tretton kapitel.

## Ändringsomfattning per kapitel

| Kapitel | Ord r0046 | Ord r0047 | Riktade textgrepp |
|---|---:|---:|---:|
| 03-it-formagor.md | 589 | 650 | 1 |
| 04-interaktion-kanaler.md | 946 | 913 | 2 |
| 05-process-workflow.md | 1284 | 1189 | 2 |
| 06-regler-beslut.md | 1022 | 980 | 1 |
| 07-datahantering.md | 1005 | 980 | 4 |
| 08-analys-ai.md | 903 | 869 | 5 |
| 09-integration.md | 995 | 947 | 3 |
| 10-identitet-tillit.md | 595 | 573 | 1 |
| 11-slutanvandarmiljo.md | 876 | 843 | 1 |
| 12-cybersakerhet.md | 829 | 821 | 1 |
| 13-utveckling-leverans.md | 718 | 707 | 1 |
| 14-kormiljo.md | 828 | 817 | 1 |
| 15-natverk.md | 900 | 877 | 2 |
| 16-driftbarhet.md | 815 | 792 | 1 |

