# Från plattformsorienterad IT till verksamhetsnära AI-utveckling

**Mål:** Delegerad digital utveckling med riskstyrda, mätbara och återkallbara tekniska mandat.

Detta är en rekommenderad ordningsföljd av **förmågeutveckling**, inte ett påstående om att alla plattformstjänster behövs i alla system. Vågorna är överlappande och vissa arbeten bör gå parallellt.

## Våg 1: A. Mandat och spärrar före skala
Avgränsa identiteter, agentåtkomst, datautbyte och maskinella åtgärder utifrån verksamhetsrisk.

### CAP-IT-07 – Identitet och tillit
Agentidentiteter, delegering och tidsbundna mandat
**Tjänster i baseline:** PLS-025, PLS-085, PLS-026, PLS-030, PLS-063, PLS-027, PLS-028, PLS-029, PLS-068, PLS-079.

### CAP-IT-12 – Cybersäkerhet och tekniskt skydd
Data-/verktygsskydd, policykontroller och incidentrespons
**Tjänster i baseline:** PLS-079, PLS-069, PLS-052, PLS-077, PLS-050, PLS-051, PLS-048, PLS-078, PLS-086, PLS-053, PLS-087.

### CAP-IT-04 – Datahantering och informationslagring
Proveniens, åtkomst och retention för AI-konsumerad data
**Tjänster i baseline:** PLS-064, PLS-065, PLS-098, PLS-066, PLS-082, PLS-067, PLS-012, PLS-081, PLS-083, PLS-010, PLS-097, PLS-074, PLS-013, PLS-011, PLS-088, PLS-075, PLS-084.

### CAP-IT-06 – Integration och informationsutbyte
Behörighetsbunden, begränsad integration och verktygsanrop
**Tjänster i baseline:** PLS-020, PLS-024, PLS-021, PLS-022, PLS-080, PLS-023, PLS-079, PLS-075.

## Våg 2: B. Kvalitet i produktion
Integrera AI-utvärdering, ändringsspår, observability, kostnadskontroll och möjlighet att stoppa lösningar.

### CAP-IT-10 – Utveckling och teknisk leverans
AI-assisterad utveckling med verifieringsgrindar och spårbarhet
**Tjänster i baseline:** PLS-039, PLS-040, PLS-041, PLS-042, PLS-092, PLS-093, PLS-086, PLS-094, PLS-095, PLS-019.

### CAP-IT-09 – Driftbarhet och motståndskraft
Automatisk telemetry, incidentkontroll och stopp av AI-flöden
**Tjänster i baseline:** PLS-037, PLS-038, PLS-035, PLS-070, PLS-036.

### CAP-IT-05 – Analys, sökning och intelligent informationsbearbetning
Godkänd modellåtkomst, grounding, evals och dataägarskap
**Tjänster i baseline:** PLS-017, PLS-099, PLS-096, PLS-016, PLS-019, PLS-064, PLS-065, PLS-015, PLS-098, PLS-082, PLS-083, PLS-074, PLS-090, PLS-088, PLS-018, PLS-014.

## Våg 3: C. Kontrollerade bygg- och körvägar
Erbjud godkända mallar, körprofiler och kanaler för både professionella team och verksamhetsnära byggare.

### CAP-IT-08 – Applikationsexekvering och körmiljö
Begränsade körprofiler, kvoter och automatisk avveckling
**Tjänster i baseline:** PLS-032, PLS-091, PLS-031, PLS-033, PLS-034, PLS-078.

### CAP-IT-13 – Nätverk och konnektivitet
Riskklassad nätaccess och egress för verktyg och agenter
**Tjänster i baseline:** PLS-057, PLS-079, PLS-072, PLS-054, PLS-055, PLS-071, PLS-089, PLS-056, PLS-073, PLS-058, PLS-076, PLS-087.

### CAP-IT-01 – Interaktion, presentation och kanaler
Tillgängliga, granskningsbara AI-skapade gränssnitt
**Tjänster i baseline:** PLS-001, PLS-002, PLS-003, PLS-004, PLS-074, PLS-089, PLS-075.

### CAP-IT-11 – Slutanvändarmiljö och klientplattform
Riskstyrd klientåtkomst till nya verktyg
**Tjänster i baseline:** PLS-045, PLS-046, PLS-077, PLS-047.

## Våg 4: D. Verksamhetsstyrda processer och beslut
Möjliggör automation och AI-förslag utan att överlåta regelägarskap och verksamhetsbeslut till plattformen.

### CAP-IT-02 – Process, workflow och ärendehantering
Verksamhetsnära arbetsflöden med mänskliga grindar
**Tjänster i baseline:** PLS-005, PLS-006, PLS-007, PLS-004.

### CAP-IT-03 – Regler och beslut
AI som regelförslag, inte obevakad regelägare
**Tjänster i baseline:** PLS-008, PLS-009.

## Förslag på prioritering och verifiering
Använd de fem grundkraven: tjänsteägare, repeterbarhet, policy/säkerhet, verifierbar leverans och återställbarhet. Besluta först vilka konsumenter och riskklasser som omfattas.

### Detaljerad tjänstevis prioritering
Kriterier nedan avser **målbilden G4**. Formuleringar som ”där…”, ”vid…” och ”för…” är viktiga för villkorad kritikalitet.

| Förmåga / tjänst | Funktionskritikalitet | Gemensam tjänst | Målkrav (förkortat) |
|---|---|---|---|
| CAP-IT-09 / PLS-037 | Kritisk | Viktig | Automatiskt skydd även för verksamhetsbyggda appar, konfiguration, AI-arbetsflödens tillstånd, kunskapsindex och relevanta externa beroenden; klassningssty |
| CAP-IT-09 / PLS-038 | Kritisk för verksamhetskritiska kedjor | Viktig | Riskklassad kontinuitet för många små lösningar och AI-kedjor; snabbt stopp/isolering, återstart i känd version, beroende på externa modellleverantörer, ma |
| CAP-IT-09 / PLS-035 | Kritisk | Kritisk | Automatisk instrumentering även för AI/agentkedjor: versions-ID, modell- och promptkonfiguration, tool calls, latens, token-/kostnadssignaler och kvalitets |
| CAP-IT-09 / PLS-070 | Viktig för reglerade/kritiska kedjor | Viktig | Spårbara delegerade åtgärder från appar och AI-agenter med användare, agent-/workloadidentitet, verktygsanrop, beslutspunkt och stopp/återkallande; datamin |
| CAP-IT-09 / PLS-036 | Kritisk för kritiska flöden | Kritisk | Riskklassade larm för verksamhetslösningar, AI-kostnads- och kvalitetsavvikelser, plötsliga felaktiga agentåtgärder, automatisk avstängning samt tydligt mä |
| CAP-IT-08 / PLS-032 | Situationsberoende | Situationsberoende | Ge styrd VM-runtime när verksamhetslösningar kräver särskild kompatibilitet; begränsa autonom provisionering genom identitet, kvoter, kostnadstak, godkända |
| CAP-IT-08 / PLS-091 | Situationsberoende | Situationsberoende | Behåll säkra kompatibilitetsprofiler där verksamhetsnära lösningar återanvänder äldre tjänster; erbjud väl dokumenterade API-gränser snarare än fri adminis |
| CAP-IT-08 / PLS-031 | Viktig för många nya applikationer | Viktig | Maskinkonsumerbara, riskklassade profiler för AI-assisterad utveckling; tidsbegränsade previewmiljöer, kvoter, kostnadsgränser, isolering, ägarspårbarhet o |
| CAP-IT-08 / PLS-033 | Viktig för automatiserade flöden | Viktig | Kortlivade AI-/datajobb med budget, tidsgränser, godkända verktyg, isolering och audit på uppdragsnivå. Kräv explicita kontrollpunkter innan jobb gör irrev |
| CAP-IT-08 / PLS-034 | Situationsberoende | Viktig om lokal AI/ML kräver acceleratorer | Styr GPU-konsumtion för AI, media och autonom bearbetning genom policy, kapacitetsgränser, budget och prioritet. Extern hanterad LLM kan minska behovet av  |
| CAP-IT-08 / PLS-078 | Kritisk för högriskworkloads | Viktig | Automatisk riskklassad kontroll även för verksamhetsbyggda workloads och autonoma exekveringar; stöd för karantän/stopp, spårning till ansvarig och mekanis |
| CAP-IT-10 / PLS-039 | Kritisk | Kritisk | Kräv ursprung och ägare även för AI-genererade ändringar; minimera agentbehörigheter och skydda produktionsgrenar. |
| CAP-IT-10 / PLS-040 | Kritisk | Kritisk | Verifiera även AI-assisterade förändringar; tillämpa riskbaserade godkännanden, isolerade agentjobb och deployment-spärrar. |
| CAP-IT-10 / PLS-041 | Kritisk | Kritisk | Knyt AI-genererade byggresultat till ägare, källcommit och attestering; hantera snabb artefaktomsättning. |
| CAP-IT-10 / PLS-042 | Kritisk | Kritisk | Gör deklarativa kontrakt maskinkonsumerbara med begränsade agentmandat, kvoter och automatisk avveckling. |
| CAP-IT-10 / PLS-092 | Viktig | Kritisk | Anpassa utvecklingsgrund för AI-assisterad kodproduktion med maskinläsbara regler och automatisk konformitetskontroll. |
| CAP-IT-10 / PLS-093 | Situationsberoende | Viktig vid mobilportfölj | Stöd AI-assisterad mobilutveckling med kontrollerad device-API-användning, privacy-kontroller och automatiserade testsviter. |
| CAP-IT-10 / PLS-086 | Kritisk | Kritisk | Förstärk för AI-genererat innehåll, dependency confusion, agentändringar och snabb återtestning; granska även verktygsbehörigheter. |
| CAP-IT-10 / PLS-094 | Viktig | Kritisk vid brett agentbruk | Stöd agentiska arbetsflöden med kortlivade credentials, isolerade arbetsytor, begränsade kommandon och granskningsgrindar. |
| CAP-IT-10 / PLS-095 | Kritisk för agentlösningar | Kritisk vid bred AI-utveckling | Erbjud riskgraderade agentmönster: read-only, föreslå, utföra; verktygsbehörighet och human-in-the-loop. |
| CAP-IT-10 / PLS-019 | Kritisk för högrisk-AI | Kritisk vid bred AI-utveckling | Testa agentverktyg, retrieval och prompt injection-scenarier; komplettera offline-evals med kontrollerad driftuppföljning. |
| CAP-IT-13 / PLS-057 | Kritisk | Kritisk | Riskklassad exponering av verksamhets- och AI-lösningar med automatisk avveckling, kvoter och spårbar extern åtkomst. |
| CAP-IT-13 / PLS-079 | Kritisk | Kritisk | Policy- och riskstyrd anslutning för nya verksamhetsflöden och agentanrop, med begränsade mandat och granskbara dataflöden. |
| CAP-IT-13 / PLS-072 | Kritisk | Kritisk | Dynamiska isoleringsprofiler för tillfälliga AI-/verksamhetsworkloads och automatisk nedstängning av kommunikationsvägar. |
| CAP-IT-13 / PLS-054 | Kritisk | Kritisk | Snabb, styrd provisionering och avveckling av kortlivade lösningar med ägare, TTL och policybegränsningar. |
| CAP-IT-13 / PLS-055 | Kritisk | Viktig | Risk- och kontextstyrd anslutning för fler verksamhetsnära enheter och edge/AI-klienter. |
| CAP-IT-13 / PLS-071 | Kritisk | Viktig | Flexibel och säker anslutning för verksamhetsnära samt tillfälliga platser med riskbaserad kontinuitet. |
| CAP-IT-13 / PLS-089 | Situationsberoende | Viktig vid medieportfölj | Säker medieleverans till AI-/verksamhetsnära applikationer, med åtkomstbegränsning och spårbart nyttjande. |
| CAP-IT-13 / PLS-056 | Kritisk | Kritisk | Granulär och kortlivad åtkomst även för verksamhetsnära operatörer och automatiserade operatörsflöden. |
| CAP-IT-13 / PLS-073 | Kritisk | Kritisk | Kontrollerad externt riktad åtkomst för agentiska verktyg, kostnadskvoter och kortlivade miljöer. |
| CAP-IT-13 / PLS-058 | Kritisk | Kritisk | Dynamisk identitets-/riskkopplad policy för agent- och verksamhetsworkloads, med säkra standardvärden. |
| CAP-IT-13 / PLS-076 | Situationsberoende | Viktig vid fältverksamhet | Riskstyrd anslutning för nya sensorer, autonoma hjälpmedel och AI-stöd under avbrott eller begränsad bandbredd. |
| CAP-IT-13 / PLS-087 | Kritisk vid extern exponering | Kritisk | Riskanpassade kontroller för AI-/agentgränssnitt, automatisering och omfattande verktygsanrop, med möjlighet till snabb spärr. |
| CAP-IT-07 / PLS-025 | Kritisk | Kritisk | Säker autentisering och delegerade användarsessioner för verksamhetsappar och AI-assistenter; distinkt användaridentitet, appidentitet och agentmandat. |
| CAP-IT-07 / PLS-085 | Kritisk | Kritisk | Ägar-, ändamåls- och livscykelmetadata även för verksamhetsnära lösningar och deras tekniska identiteter; undvik att lägga agentspecifika mandat i personka |
| CAP-IT-07 / PLS-026 | Kritisk | Kritisk | Just-in-time och tidsbegränsade mandat för verksamhetslösningar/agentdelegering; begriplig attestering av agentens tillåtna åtgärder. |
| CAP-IT-07 / PLS-030 | Kritisk | Kritisk vid många agentflöden | Finkornig delegation för agentverktyg, ändamål, tid, kontext och risk; mänsklig attestering vid högriskåtgärder och beslut vid varje faktisk resursåtkomst. |
| CAP-IT-07 / PLS-063 | Kritisk | Kritisk | Explicit restriktion mot stående agent-adminrättigheter; kortlivade verktygsmandat, mänsklig kontroll för högriskändring. |
| CAP-IT-07 / PLS-027 | Kritisk | Kritisk | Unik identitet och ägare per autonomt arbetsflöde/agent, avgränsad delegering och möjlighet att snabbt frysa/avveckla. |
| CAP-IT-07 / PLS-028 | Kritisk där certifikat behövs | Kritisk | Kortlivade certifikat och policyprövad kedja även för tillfälliga tjänster och AI-kopplingar; omedelbar spärr/avveckling vid kompromiss. |
| CAP-IT-07 / PLS-029 | Kritisk där hemligheter används | Kritisk | Ephemeral secrets för agentjobb, tool-scoped åtkomst, läckagebegränsning och säker stängning efter uppdrag. |
| CAP-IT-07 / PLS-068 | Situationsberoende | Viktig vid stor användning | Säkra människa-i-loopen-flöden för AI-förberedda dokument och agentutlösta ärenden; agentens förslag är inte en juridisk underskrift. |
| CAP-IT-07 / PLS-079 | Kritisk vid extern tillit | Kritisk vid stor partnerportfölj | Finkornigt riskstyrt part- och uppdragsmandat för agenters externa anrop, explicit godkännande av nya motparter och omedelbar spärr. |
| CAP-IT-12 / PLS-079 | Situationsberoende | Viktig | Tids- och ändamålsbegränsade agent-/verksamhetsanrop via samma kontrollerade partnerkanal; minimala scopes. |
| CAP-IT-12 / PLS-069 | Kritisk | Kritisk | Gränser även för promptar, retrieval, verktygsutdata och AI-agenters export; sanering och förhindrande av överdelning. |
| CAP-IT-12 / PLS-052 | Kritisk | Viktig | Korta användningsmandat för agentarbetsflöden, isolerade nyckeloperationer och skydd mot massdekryptering. |
| CAP-IT-12 / PLS-077 | Kritisk | Kritisk | Skydd vid AI-assisterat arbete, lokal dataåtkomst och kodgenerering samt agentens klientbehörigheter. |
| CAP-IT-12 / PLS-050 | Kritisk | Kritisk | Detektion av agentmissbruk, promptinjektionens effekter, massverktygsanrop och dataexfiltration. |
| CAP-IT-12 / PLS-051 | Kritisk | Viktig | Teknisk analys av agentens kontext, verktygsbeslut, prompt-/modellversion och delegering med integritetsskydd. |
| CAP-IT-12 / PLS-048 | Kritisk | Kritisk | Upptäck även kortlivade verksamhetsappar, AI-komponenter och agenters exponerade verktyg. |
| CAP-IT-12 / PLS-078 | Kritisk | Kritisk | Kortlivade AI-workloads, isolerad exekvering av agentkod samt detektion av avvikande resurs- och verktygsanvändning. |
| CAP-IT-12 / PLS-086 | Kritisk | Kritisk | Analysera AI-genererad kod, agentverktyg, prompt-/konfigurationsartefakter och modellberoenden med relevant specialiserad utvärdering. |
| CAP-IT-12 / PLS-053 | Kritisk | Kritisk | Riskklasser styr vilka AI-/agentverktyg, dataåtkomster och åtgärder som får nyttjas; maskinell avveckling. |
| CAP-IT-12 / PLS-087 | Kritisk | Kritisk | Skydd av agentexponerade API:er, schema-/verktygskontroll och begränsning av automatiserad överanvändning. |
| CAP-IT-04 / PLS-064 | Kritisk | Kritisk | Policybegränsade analysytor för AI med definierad härkomst, dataavgränsning och spårbara kopior. |
| CAP-IT-04 / PLS-065 | Kritisk | Kritisk | Tydliga datakontrakt och kvalitetsspärrar även för AI-ingestion, embedding- och uppdateringsflöden. |
| CAP-IT-04 / PLS-098 | Kritisk | Kritisk | AI-agenter använder samma godkända mått och begreppsdefinitioner som mänskliga analytiker. |
| CAP-IT-04 / PLS-066 | Kritisk | Kritisk | Maskinläsbar proveniens för AI-konsumtion, beslutsunderlag och åtkomstbeslut. |
| CAP-IT-04 / PLS-082 | Kritisk | Kritisk | Färskhet, representativitet och källdrift övervakas även för AI- och agentkonsumtion. |
| CAP-IT-04 / PLS-067 | Viktig | Viktig | Styrda auktoritativa kodverk används även i AI-genererad logik; källans begreppsägarskap bevaras. |
| CAP-IT-04 / PLS-012 | Situationsberoende | Viktig | Kortlivade AI-/agentcachedata isoleras efter användare, ändamål och dataklass. |
| CAP-IT-04 / PLS-081 | Situationsberoende | Viktig | Agentåtkomst begränsas via applikationslager och dokumentens ändamål; rå databasaccess är inte standard. |
| CAP-IT-04 / PLS-083 | Situationsberoende | Viktig | Kunskapsgrafer får versionerad proveniens och relationell behörighetsfiltrering för AI. |
| CAP-IT-04 / PLS-010 | Kritisk | Kritisk | Dataåtkomst för genererade lösningar/AI sker med minsta privilegium, tidsbegränsning och transaktionsgränser. |
| CAP-IT-04 / PLS-097 | Viktig | Kritisk | AI/agent-frågor begränsas via attributpolicy, syfte och frågekvoter utan breda datakopior. |
| CAP-IT-04 / PLS-074 | Situationsberoende | Viktig | Agent-/analysfrågor använder platsdata med geofencing, sekretess och upplösningsbegränsning. |
| CAP-IT-04 / PLS-013 | Kritisk | Kritisk | Kortlivade verksamhetslösningar har automatisk gallring och separation mellan tillfälligt och beständigt tillstånd. |
| CAP-IT-04 / PLS-011 | Kritisk | Kritisk | AI-artefakter, promptbilagor och dataset lagras med ändamål, proveniens och automatisk tidsgräns. |
| CAP-IT-04 / PLS-088 | Situationsberoende | Viktig | AI-medieflöden får rättigheter, metadata och proveniens från original genom hela kedjan. |
| CAP-IT-04 / PLS-075 | Situationsberoende | Viktig | AI-stöd i fält får lokala sekretessgränser och kan stängas av när datastatus är osäker. |
| CAP-IT-04 / PLS-084 | Viktig | Viktig | AI kan hjälpa till att förbereda underlag men rättsligt betydelsefulla dokument kommer från godkänd mall och data. |
| CAP-IT-06 / PLS-020 | Kritisk där API används | Kritisk vid bred agentåtkomst | Agent- och verksamhetsutvecklade konsumenter får avsikts-, identitets- och riskstyrd API-åtkomst via avgränsade verktyg; policy och kostnad/kvot synlig per |
| CAP-IT-06 / PLS-024 | Viktig där agentverktyg integreras | Viktig | Policykontrollerad anslutning av AI-/verksamhetsflöden till godkända adapterverktyg, tydlig separation mellan teknisk orkestrering och domänbeslut; ändring |
| CAP-IT-06 / PLS-021 | Kritisk där tillförlitlig kö behövs | Viktig | Säker asynkron hantering av AI-/verksamhetsuppdrag med begränsad livslängd, avbrytning, tydlig ansvarig aktör och säkra kompensationsmönster. |
| CAP-IT-06 / PLS-022 | Viktig vid omfattande AI-eventflöden | Viktig där strömmar används | AI-/verksamhetslösningar får explicit tillåten konsumtion av relevanta händelser; replay, informationsklass och händelsers giltighet begränsas per syfte. |
| CAP-IT-06 / PLS-080 | Viktig där kontrakt används | Kritisk vid omfattande maskinkonsumenter | Maskinläsbara kontrakt för agentverktyg och datakonsumenter, explicit åtkomst och schemakvalitet, automatiserad upptäckt av drift från förväntat kontrakt. |
| CAP-IT-06 / PLS-023 | Kritisk där filutbyte används | Viktig där agentdrivet filutbyte finns | Tillåten och tidsbegränsad filåtkomst för verksamhetsnära lösningar; AI får inte fritt exportera material utan klassning, kontroll och spårbar mottagare. |
| CAP-IT-06 / PLS-079 | Kritisk vid extern anslutning | Kritisk vid extern agentåtkomst | Villkorade agent- och verksamhetskopplingar med uttrycklig tillåtelselista per motpart, ändamål och transaktionsklass; mänsklig kontroll vid hög konsekvens |
| CAP-IT-06 / PLS-075 | Situationsberoende | Viktig där AI används i fält | Verksamhetsnära fältappar och AI-assistenter arbetar med säkert begränsad offlinekunskap, kan visa datans ålder och kräver ny auktorisation innan riskfylld |
| CAP-IT-01 / PLS-001 | Kritisk vid bred självutveckling | Kritisk vid bred självutveckling | Godkända komponenter för AI-genererade gränssnitt, tydlig visning av förslag kontra beslut, mänsklig kontroll vid riskfyllda handlingar och automatiska til |
| CAP-IT-01 / PLS-002 | Kritisk vid bred AI-assisterad webb | Kritisk vid många producenter | AI-assisterad kodgenerering sker inom signerade och versionsstyrda mallar; automatisk testning av UI, integritet och tillgänglighet, begränsade agentverkty |
| CAP-IT-01 / PLS-003 | Viktig för verksamhetsnära formulär | Viktig vid kontrollerad självutveckling | Riskstyrd självbetjäning för formulärskapande; AI får föreslå fält men publicering, personuppgiftshantering och verksamhetsvalidering kräver ansvarig godkä |
| CAP-IT-01 / PLS-004 | Kritisk vid verksamhetskritiska aviseringar | Kritisk vid mycket bred automatisering | Agentutlösta notifieringar begränsas av mottagarkrets, ämne, sekretessklass, frekvens och åtgärdsmandat; avvikelse kan stoppas. |
| CAP-IT-01 / PLS-074 | Viktig vid agentstödd geoverksamhet | Viktig vid stor geoportfölj | AI-baserad geoassistans visar osäkerhet och källor, begränsar åtkomst till känsliga positioner och kräver mänskligt beslut vid högriskåtgärd. |
| CAP-IT-01 / PLS-089 | Viktig vid omfattande medieflöden | Viktig vid stor medieportfölj | Styrd mediaåtkomst för genererade eller multimodala gränssnitt; tydlig markering av syntetiskt material där relevant och strikt skydd av privata länkar. |
| CAP-IT-01 / PLS-075 | Kritisk om offline är verksamhetskrav | Kritisk vid omfattande fältverksamhet | Kontrollerad AI-assistans även vid intermittent nät; tydliga begränsningar för lokal modell-/datakopia och obligatorisk avstämning innan riskhandling. |
| CAP-IT-02 / PLS-005 | Kritisk vid agentstyrda affärsflöden | Kritisk vid bred verksamhetsautomation | Policybaserad exekvering för agentinitierade steg, separata mandat, mänsklig attest för högriskåtgärder, reproducerbar processhistorik och säker avbrytning |
| CAP-IT-02 / PLS-006 | Kritisk där AI behandlar ärenden | Viktig vid bred verksamhetsutveckling | Maskinläsbar ärendekontext med dataminimering och behörighetskontroll, föreslagna nästa steg, spårbar agentmedverkan och mänskligt ansvar för beslut. |
| CAP-IT-02 / PLS-007 | Kritisk vid AI-förslag till mänskliga beslut | Kritisk vid bred hybridautomation | Explicit separation av agentuppgift och mänsklig attest; tidbegränsade uppdrag, förklarbar prioritering, delegation och automatisk flaggning vid osäkerhet. |
| CAP-IT-02 / PLS-004 | Kritisk vid agentbaserad extern avisering | Viktig vid bred agentanvändning | Policy på agentinitierade utskick: syfte, mottagare, innehåll, klassning, frekvens och mänskligt godkännande när konsekvensen är hög. |
| CAP-IT-03 / PLS-008 | Kritisk vid AI-initierade regelstyrda handlingar | Viktig vid bred verksamhetsautomation | AI-förslag får endast aktiveras via explicit attest, deterministisk regelkörning, tillåten verktygsåtkomst och spårbar proveniens för regel/indata/beslut. |
| CAP-IT-03 / PLS-009 | Kritisk för omfattande AI-assisterade regeländringar | Viktig vid utbredd verksamhetssjälvständighet | AI kan skapa modellutkast och testfall men dessa måste valideras syntaktiskt och semantiskt; utför kontrafaktisk simulering, bias- och konsekvenstester sam |
| CAP-IT-11 / PLS-045 | Kritisk för hanterade enheter med känslig åtkomst | Kritisk där klientposture styr åtkomst | Kontinuerlig postureutvärdering, kortlivad enhetstillit, automation för externa/temporära användare och standard för tillåtna AI-verktyg utan att ge genere |
| CAP-IT-11 / PLS-046 | Viktig där lokal programinstallation behövs | Viktig för kontrollerade installationsflöden | Snabb kuraterad publicering av verksamhetsappar, automatiserade kompatibilitets- och skadevarukontroller och avvecklingspolicy; för webb- och AI-appar kan  |
| CAP-IT-11 / PLS-077 | Kritisk för högriskklienter och generell rekommenderad skyddsnivå | Kritisk för hanterade endpoints | Skydd även mot missbruk av klientbaserade AI-assistenter, browser-/sessionsrisker och misstänkta lokala dataflöden där verktygsstöd finns; respons måste va |
| CAP-IT-11 / PLS-047 | Situationsberoende | Viktig för särskilda isolerings- och datakontrollbehov | Riskprofiler för isolerad användning av känsliga appar eller AI-verktyg, tydlig sessionsisolering, begränsat urklipp/filöverföring vid behov och spårbar ti |
| CAP-IT-05 / PLS-017 | Kritisk där generativ AI används i stor skala | Viktig för många konsumenter | Riskstyrd modellåtkomst för verksamhetsappar/agenter med verktygsbegränsningar, utvärdering och återkallelse |
| CAP-IT-05 / PLS-099 | Situationsberoende | Viktig för många konsumenter | Skalbar feature-serving för många modeller med driftövervakning, driftspårning och snabb återkallelse |
| CAP-IT-05 / PLS-096 | Situationsberoende | Viktig för många konsumenter | Kontrollerad finjustering och storskalig träning med datalinje, kostnadstak, skydd för träningsdata och godkända modeller |
| CAP-IT-05 / PLS-016 | Situationsberoende | Viktig för många konsumenter | Riskstyrd serving med automatiska evals, drift-/biaslarm och återtagbara versioner för många konsumenter |
| CAP-IT-05 / PLS-019 | Kritisk för produktions-AI | Viktig för många konsumenter | Kontinuerliga regressions- och agenttester med mänsklig eskalering, adversarial fall och produktionsuppföljning |
| CAP-IT-05 / PLS-064 | Viktig | Viktig för många konsumenter | Styrda återanvändbara analysdata för AI och verksamhetsanalys med lineage, åtkomstpolicy och kvalitetsnivåer |
| CAP-IT-05 / PLS-065 | Viktig | Viktig för många konsumenter | Datapipelines för kontinuerliga AI- och analysflöden med policy, ändringsupptäckt och kostnadsövervakning |
| CAP-IT-05 / PLS-015 | Viktig | Viktig för många konsumenter | Verksamhetsnära fråge- och analysstöd med AI-assistans utan att kringgå auktoritativa mått eller källbehörigheter |
| CAP-IT-05 / PLS-098 | Kritisk för AI som konsumerar affärsmått | Viktig för många konsumenter | Samma semantiska lager konsumeras av AI-agenter och mänskliga analytiker med behörighet och versionsspårbarhet |
| CAP-IT-05 / PLS-082 | Kritisk för besluts-/AI-data | Viktig för många konsumenter | Kvalitetsgrindar före modellträning, retrieval och agentanvändning; löpande kontroll av källdata |
| CAP-IT-05 / PLS-083 | Situationsberoende | Viktig för många konsumenter | Grafbaserad kunskapsrepresentation för avancerad analys/AI när effekt verifierats mot enklare alternativ |
| CAP-IT-05 / PLS-074 | Situationsberoende | Viktig för många konsumenter | Geodata i verksamhetsnära analys och AI med skydd för känsliga positioner och kontrollerad härledning |
| CAP-IT-05 / PLS-090 | Situationsberoende | Viktig för många konsumenter | AI-baserad multimodal extraktion med riskklassning, mänsklig verifiering och skydd för känsligt innehåll |
| CAP-IT-05 / PLS-088 | Situationsberoende | Viktig för många konsumenter | Automatiserad produktion av AI-anpassade mediarepresentationer med källkoppling och kostnadskontroller |
| CAP-IT-05 / PLS-018 | Kritisk för kunskapsgrundade AI-svar | Viktig för många konsumenter | Riskstyrd grounding för agent- och AI-appar med källtrogenhet, färskhetskontroller och skydd mot promptinjektion i källinnehåll |
| CAP-IT-05 / PLS-014 | Viktig vid informationsintensiva IT-stöd | Viktig för många konsumenter | Hybrid/semantisk sökning till både mänskliga användare och AI, med behörighets- och aktualitetskontroller |

### Godkännandekriterier
- Minst ett verkligt ändrings-/fel-/åtkomstscenario demonstrerat över berörda tjänstegränser.
- Skydd, spårbarhet och rollback/återställning har verifierats av ansvariga team.
- Tjänster som klassats situationsberoende etableras först när identifierade konsumenter motiverar investeringen.
- Underlag för beslut innehåller mätbar effekt, livscykelägare och driftkostnad.
