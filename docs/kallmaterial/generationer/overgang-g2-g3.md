# Från distribuerade IT-stöd till plattformsorienterad IT

**Mål:** Produktifierade, säkra och självbetjänade plattformstjänster med tydliga servicelöften.

Detta är en rekommenderad ordningsföljd av **förmågeutveckling**, inte ett påstående om att alla plattformstjänster behövs i alla system. Vågorna är överlappande och vissa arbeten bör gå parallellt.

## Våg 1: A. Plattformens minsta säkra produkt
Koppla automatiserad leverans till identitet, policy, instrumentering och återställning.

### CAP-IT-10 – Utveckling och teknisk leverans
Gemensamma pipelines, IaC/GitOps och paved roads
**Tjänster i baseline:** PLS-039, PLS-040, PLS-041, PLS-042, PLS-092, PLS-093, PLS-086, PLS-094, PLS-095, PLS-019.

### CAP-IT-07 – Identitet och tillit
Automatiserade identitets-/credentialflöden
**Tjänster i baseline:** PLS-025, PLS-085, PLS-026, PLS-030, PLS-063, PLS-027, PLS-028, PLS-029, PLS-068, PLS-079.

### CAP-IT-12 – Cybersäkerhet och tekniskt skydd
Säkerhetskontroller som kod och guardrails
**Tjänster i baseline:** PLS-079, PLS-069, PLS-052, PLS-077, PLS-050, PLS-051, PLS-048, PLS-078, PLS-086, PLS-053, PLS-087.

### CAP-IT-09 – Driftbarhet och motståndskraft
Tjänstekvalitet och backup/observability som standardprofil
**Tjänster i baseline:** PLS-037, PLS-038, PLS-035, PLS-070, PLS-036.

## Våg 2: B. Självbetjänade resurser och kommunikation
Inför konsumtionsbara tjänstekontrakt för runtime, nät, databas och integration.

### CAP-IT-08 – Applikationsexekvering och körmiljö
Självbetjänade körprofiler och livscykel
**Tjänster i baseline:** PLS-032, PLS-091, PLS-031, PLS-033, PLS-034, PLS-078.

### CAP-IT-13 – Nätverk och konnektivitet
Deklarativ policy och självbetjänad nätanslutning
**Tjänster i baseline:** PLS-057, PLS-079, PLS-072, PLS-054, PLS-055, PLS-071, PLS-089, PLS-056, PLS-073, PLS-058, PLS-076, PLS-087.

### CAP-IT-04 – Datahantering och informationslagring
Självbetjänade databaser med säkerhet och livscykel
**Tjänster i baseline:** PLS-064, PLS-065, PLS-098, PLS-066, PLS-082, PLS-067, PLS-012, PLS-081, PLS-083, PLS-010, PLS-097, PLS-074, PLS-013, PLS-011, PLS-088, PLS-075, PLS-084.

### CAP-IT-06 – Integration och informationsutbyte
Produktifierad API-/meddelandeplattform
**Tjänster i baseline:** PLS-020, PLS-024, PLS-021, PLS-022, PLS-080, PLS-023, PLS-079, PLS-075.

## Våg 3: C. Standardmönster för användning
Erbjud återanvändbara komponenter och domännära byggblock, bara där återkommande behov finns.

### CAP-IT-01 – Interaktion, presentation och kanaler
Förvaltade designsystem och klientstarter
**Tjänster i baseline:** PLS-001, PLS-002, PLS-003, PLS-004, PLS-074, PLS-089, PLS-075.

### CAP-IT-11 – Slutanvändarmiljö och klientplattform
Automatiserad enrollment och klientefterlevnad
**Tjänster i baseline:** PLS-045, PLS-046, PLS-077, PLS-047.

### CAP-IT-02 – Process, workflow och ärendehantering
Återanvändbara workflow-/case-byggblock vid återkommande behov
**Tjänster i baseline:** PLS-005, PLS-006, PLS-007, PLS-004.

### CAP-IT-03 – Regler och beslut
Delade regel- och beslutsfunktioner vid efterfrågan
**Tjänster i baseline:** PLS-008, PLS-009.

## Våg 4: D. Data- och analysprodukter
Bygg gemensamma mått, sökning, pipelines och AI/ML-erbjudanden efter efterfrågan och datamognad.

### CAP-IT-05 – Analys, sökning och intelligent informationsbearbetning
Återanvändbar BI, sökning och datagrund
**Tjänster i baseline:** PLS-017, PLS-099, PLS-096, PLS-016, PLS-019, PLS-064, PLS-065, PLS-015, PLS-098, PLS-082, PLS-083, PLS-074, PLS-090, PLS-088, PLS-018, PLS-014.

## Förslag på prioritering och verifiering
Använd de fem grundkraven: tjänsteägare, repeterbarhet, policy/säkerhet, verifierbar leverans och återställbarhet. Besluta först vilka konsumenter och riskklasser som omfattas.

### Detaljerad tjänstevis prioritering
Kriterier nedan avser **målbilden G3**. Formuleringar som ”där…”, ”vid…” och ”för…” är viktiga för villkorad kritikalitet.

| Förmåga / tjänst | Funktionskritikalitet | Gemensam tjänst | Målkrav (förkortat) |
|---|---|---|---|
| CAP-IT-09 / PLS-037 | Kritisk | Viktig | Katalogiserade, policybaserade backup-profiler; automatisk anslutning, retention, kryptering, isolering och självbetjänad restore i behörig omfattning; aut |
| CAP-IT-09 / PLS-038 | Kritisk för verksamhetskritiska kedjor | Viktig | Förvaltade återställningsprofiler, deklarativa beroenden, automatiserad miljöåterskapning, regelbundna övningar och mätning av faktisk RTO/RPO. |
| CAP-IT-09 / PLS-035 | Kritisk | Kritisk | Standardinstrumentering som ingår i utvecklingsmallar och runtime; självbetjänad åtkomst, multi-tenancy, datakvalitet, kostnadskontroll, retention och korr |
| CAP-IT-09 / PLS-070 | Viktig för reglerade/kritiska kedjor | Viktig | Gemensamt erbjudande för inkoppling, händelseschema, integritetsskydd, åtkomstkontroller, retention och verifierbar export; tydlig skillnad mot felsöknings |
| CAP-IT-09 / PLS-036 | Kritisk | Kritisk | Standardiserad SLO-/larmhantering som del av plattformsprodukt; larmregler i kod, tjänstekatalog, runbooks, underhållsfönster och mätning av larmkvalitet. |
| CAP-IT-08 / PLS-032 | Situationsberoende | Viktig där VM behövs | Erbjud deklarativa VM-profiler via API/IaC, policykontroller, kvoter, livscykel och standardanslutning till identitet, säkerhet och observerbarhet; tydliga |
| CAP-IT-08 / PLS-091 | Situationsberoende | Viktig för fortsatt middleware-portfölj | Publicera valbara, förvaltade runtimeprofiler med kompatibilitetsmatris, IaC/deklarativ konfiguration, automatiserad provisionering och tydlig livscykel. K |
| CAP-IT-08 / PLS-031 | Viktig för containerportföljen | Kritisk om container är organisationens standardväg | Tydliga runtimeprofiler som produkter: API/IaC, namespace-/tenantisolering, kvoter, policy, image- och versionsstöd, automatiserad säker grundkonfiguration |
| CAP-IT-08 / PLS-033 | Viktig | Viktig | Självbetjänade jobbprofiler: resurser, scheman, execution history, parametrar, eventtrigger, rättigheter, kvoter och standardtelemetri. Teknikval kan vara  |
| CAP-IT-08 / PLS-034 | Situationsberoende | Viktig vid återkommande behov | Definiera styrda GPU/acceleratorprofiler, kvoter, tilldelning, tillgänglig kapacitet, debitering och återanvändbar drivrutinsbaseline; hantera att vissa pr |
| CAP-IT-08 / PLS-078 | Kritisk för högriskworkloads | Viktig | Policybaserad anslutning till valda runtimeprofiler, riskklasser, undantagsprocess, uppföljning av täckning och teknisk integration med leverans/observabil |
| CAP-IT-10 / PLS-039 | Kritisk | Kritisk | Erbjud organisationsgemensamt SCM med SSO, repo-mallar, spårbar policy, automatiserad onboard/offboard. |
| CAP-IT-10 / PLS-040 | Kritisk | Kritisk | Tillhandahåll pipeline-mallar, policygrindar, spårbara promotionflöden och självbetjänad driftsättning. |
| CAP-IT-10 / PLS-041 | Kritisk | Kritisk | Erbjud gemensamt register med signering/attestering, retention, promotion och konsumtionspolicy. |
| CAP-IT-10 / PLS-042 | Kritisk | Kritisk | Erbjud parametriserade IaC-moduler och GitOps-flöden med policy, driftavvikelsekontroll och återtagning. |
| CAP-IT-10 / PLS-092 | Viktig | Kritisk | Publicera versionerade paved roads med CI/CD, identitet, secrets och runtimekoppling integrerade. |
| CAP-IT-10 / PLS-093 | Situationsberoende | Viktig vid mobilportfölj | Erbjud standardiserade mobilmallar, säker signering, testmatriser och releasekanaler. |
| CAP-IT-10 / PLS-086 | Kritisk | Kritisk | Integrera riskbaserade säkerhetsgrindar, container- och IaC-skanning och spårbar undantagsprocess i paved roads. |
| CAP-IT-10 / PLS-094 | Viktig | Viktig | Tillhandahåll godkända AI-verktyg med styrd repoåtkomst, policyer, spårbarhet, utbildning och mätning. |
| CAP-IT-10 / PLS-095 | Viktig vid AI-portfölj | Viktig vid AI-portfölj | Erbjud stöd för tool calling, retrievalkoppling, telemetry och policy i versionssatta startmallar. |
| CAP-IT-10 / PLS-019 | Viktig vid AI-portfölj | Viktig vid AI-portfölj | Integrera kvalitet-, robusthet- och säkerhetstester i leveranspipelinen, med spårbara acceptansgränser. |
| CAP-IT-13 / PLS-057 | Kritisk | Kritisk | Självbetjänad ingress med standardprofiler, deklarativ routing, automatisk certifikathantering och skyddade undantag. |
| CAP-IT-13 / PLS-079 | Kritisk | Kritisk | Återanvändbara anslutningsprofiler, automatiserad teknisk onboarding och versionsstyrda tillits- och trafikpolicyer. |
| CAP-IT-13 / PLS-072 | Kritisk | Kritisk | Deklarativ nätverksprovisionering för kluster och miljöer, standardiserad egress och lifecycle-koppling till workloads. |
| CAP-IT-13 / PLS-054 | Kritisk | Kritisk | API-/IaC-styrd DNS/IPAM, standardiserade miljözoner, livscykelkopplade poster och automatisk städning. |
| CAP-IT-13 / PLS-055 | Kritisk | Viktig | Policybaserad onboarding, NAC/integrerad identitet och gemensamma anslutningsprofiler för användare och IoT. |
| CAP-IT-13 / PLS-071 | Kritisk | Viktig | Standardiserade platsprofiler, central policy och automatiserad driftsättning där det är praktiskt möjligt. |
| CAP-IT-13 / PLS-089 | Situationsberoende | Viktig vid medieportfölj | Konsumerbara distributionsprofiler med CDN-/edgeintegration, automationsgränssnitt och mätbar tjänstekvalitet. |
| CAP-IT-13 / PLS-056 | Kritisk | Kritisk | Identitets- och enhetsstyrd tjänstespecifik åtkomst med självbetjänad ansökan och automatiserad avveckling. |
| CAP-IT-13 / PLS-073 | Kritisk | Kritisk | Standardiserade ingress-/egressprofiler, policystyrda destinationslistor och deklarativ provisionering. |
| CAP-IT-13 / PLS-058 | Kritisk | Kritisk | Deklarativa policyprofiler, automatiska kontroller och mikrosegmentering där komplexiteten motiverar det. |
| CAP-IT-13 / PLS-076 | Situationsberoende | Viktig vid fältverksamhet | Förvaltade fältkommunikationsprofiler, gemensam övervakning och återanvändbar integration till plattformar. |
| CAP-IT-13 / PLS-087 | Kritisk vid extern exponering | Kritisk | Självbetjänad WAF/API-skyddsprofil, central policy, automatiska testregler och versionsstyrda undantag. |
| CAP-IT-07 / PLS-025 | Kritisk | Kritisk | Standardiserad OIDC/SAML-federation, stark phishingresistent MFA där risk kräver det, självbetjänad klientregistrering och standardiserad tokenpolicy. |
| CAP-IT-07 / PLS-085 | Kritisk | Kritisk | Förvaltade katalog-API:er, attributkontrakt och automatiserad livscykelsynk med källans sanningsansvar tydligt avgränsat. |
| CAP-IT-07 / PLS-026 | Kritisk | Kritisk | Policybaserad begäran och godkännande, automatiskt tilldelade/återkallade entitlements, mätbar avveckling och attestering. |
| CAP-IT-07 / PLS-030 | Kritisk | Viktig | Återanvändbar policy decision point, versionsstyrda policyer och policytest; beslut verkställs av tjänsten som äger resursen. |
| CAP-IT-07 / PLS-063 | Kritisk | Kritisk | JIT/JEA, tidsbegränsad elevation, sessionsspårning, kontrollerat break-glass och standardiserad administration. |
| CAP-IT-07 / PLS-027 | Kritisk | Kritisk | Automatisk utfärdning/rotation av kortlivade workloadidentiteter, bindning till körmiljö och federerad tjänstetillit. |
| CAP-IT-07 / PLS-028 | Kritisk där certifikat behövs | Kritisk | Automatiserad certifikatprovisionering och rotation knuten till miljö och workload; separata trust-domäner. |
| CAP-IT-07 / PLS-029 | Kritisk där hemligheter används | Kritisk | Automatiserad dynamisk hemlighetsutdelning eller workloadbaserad autentisering där möjligt; API/IaC, policy och rotation. |
| CAP-IT-07 / PLS-068 | Situationsberoende | Viktig vid stor användning | Standard-API för signering/stämpling/tidsstämpling, attestflöden och format-/bevarandekrav, med val av tillitsnivå. |
| CAP-IT-07 / PLS-079 | Kritisk vid extern tillit | Kritisk vid stor partnerportfölj | Standardprofiler och onboarding för extern tillit, förvaltade partnercredentials, revision och tidsstyrt avslut. |
| CAP-IT-12 / PLS-079 | Situationsberoende | Viktig | Självbetjänad onboarding med förgodkända profiler, policykontroller och spårbar anslutningslivscykel. |
| CAP-IT-12 / PLS-069 | Viktig | Kritisk | Informationspolicy kopplas till tekniska guardrails och klassningsmetadata i standardprofiler; godkända undantag spåras. |
| CAP-IT-12 / PLS-052 | Kritisk | Viktig | API-baserad key management med roller, loggning, automatisk rotation där möjligt och profiler för HSM vid behov. |
| CAP-IT-12 / PLS-077 | Kritisk | Kritisk | Skydd aktiveras automatiskt vid enhetsregistrering; avvikande enhet spärras från skyddsvärda resurser. |
| CAP-IT-12 / PLS-050 | Kritisk | Kritisk | Standardiserade detektionspaket vid onboarding, täckningsmätning och prioriterad incidenttriage. |
| CAP-IT-12 / PLS-051 | Kritisk | Viktig | Förberedda playbooks för workloadisolering, forensisk export och specialisteskalering. |
| CAP-IT-12 / PLS-048 | Kritisk | Kritisk | Kontinuerlig inventering med automatisk tillgångsägare och integrerade fynd från PLS-086. |
| CAP-IT-12 / PLS-078 | Kritisk | Kritisk | Policyprofiler och standardiserat runtime-skydd integreras med provisionering av containers och VM. |
| CAP-IT-12 / PLS-086 | Kritisk | Kritisk | Paved-road-scanning av kod, IaC, images och SBOM; riskbaserade grindar, undantag och spårbarhet. |
| CAP-IT-12 / PLS-053 | Kritisk | Kritisk | Policy-as-code i golden paths med automatisk enforcement, tidsbestämda undantag och rollback. |
| CAP-IT-12 / PLS-087 | Kritisk | Kritisk | Standardprofiler för WAF/API-skydd vid onboarding, riskstyrd tuning och mätning av falskpositiva. |
| CAP-IT-04 / PLS-064 | Kritisk | Viktig | Förvaltade warehouse-/lakehouse-profiler med katalog, åtkomstpolicy, kostnadsgränser och reproducerbara miljöer. |
| CAP-IT-04 / PLS-065 | Kritisk | Kritisk | Mallbaserade, testade pipelineprofiler med katalogregistrering, policykontroll och lineage som standard. |
| CAP-IT-04 / PLS-098 | Viktig | Viktig | Publicerade måttkontrakt med återanvändbar API-/BI-konsumtion, roller och versionshantering. |
| CAP-IT-04 / PLS-066 | Kritisk | Kritisk | Automatiserad metadatafångst, sökning, klassningskoppling och lineage i plattformens standardflöden. |
| CAP-IT-04 / PLS-082 | Kritisk | Kritisk | Återanvändbara kvalitetsregler med standardmått, trend och policygrindar i pipelineprofiler. |
| CAP-IT-04 / PLS-067 | Viktig | Viktig | Självbetjänad prenumeration och publicering mot ägarstyrda referensdataprodukter. |
| CAP-IT-04 / PLS-012 | Situationsberoende | Viktig | Förvaltad cacheprofil med åtkomst, kvoter, mätvärden och automatisk livscykel. |
| CAP-IT-04 / PLS-081 | Situationsberoende | Viktig | Policyklar dokumentdatabasprofil med provad restore, schema- och retentionkontrakt. |
| CAP-IT-04 / PLS-083 | Situationsberoende | Situationsberoende | Standardprofil med behörighetsfilter, schemaändring och avgränsad querykostnad. |
| CAP-IT-04 / PLS-010 | Kritisk | Kritisk | Självbetjänade databasprofiler med IaC, säkerhetsbaseline, nyckelrotation, backupkoppling och kostnadsstyrning. |
| CAP-IT-04 / PLS-097 | Viktig | Viktig | Självbetjänad policykontrollerad federation med katalog, audit trail och kvoter. |
| CAP-IT-04 / PLS-074 | Situationsberoende | Viktig | Återanvändbara kartlager, geokodnings-API och attributåtkomst som standarderbjudande. |
| CAP-IT-04 / PLS-013 | Kritisk | Kritisk | Självbetjänade lagringsklasser, kvoter, livscykel och krypteringsprofiler för applikationer. |
| CAP-IT-04 / PLS-011 | Kritisk | Kritisk | Förvaltade objektklasser och självbetjänad provisionering med policy, kryptering och retention. |
| CAP-IT-04 / PLS-088 | Situationsberoende | Viktig | Självbetjänat API för standardformat, malwarekontroll och återanvändbara renditions. |
| CAP-IT-04 / PLS-075 | Situationsberoende | Viktig | Återanvändbar offline-SDK/profil med dataurval, retention och central livscykel. |
| CAP-IT-04 / PLS-084 | Viktig | Viktig | Självbetjänat dokument-API med typade data, godkända mallar och lagringsintegration. |
| CAP-IT-06 / PLS-020 | Kritisk där API används | Kritisk vid många team | Självbetjänad API-publicering via mall/API, dokumenterad developer experience, policyprofiler för auth, kvoter och rate limiting, automatiska kontrakts-/sä |
| CAP-IT-06 / PLS-024 | Viktig där återkommande adapterbehov | Viktig | Förvaltade adapterprofiler och transformationer som versionerade, testade tjänster med självbetjänad driftsättning, spårbar mapping och säkra standardinstä |
| CAP-IT-06 / PLS-021 | Kritisk där tillförlitlig kö behövs | Kritisk vid många kökonsumenter | Köer som självbetjänade produkter med åtkomstpolicy, retention, kvoter, schema-/versionskontroll, automatiserade kapacitets- och återställningsprov. |
| CAP-IT-06 / PLS-022 | Viktig vid eventdriven arkitektur | Viktig där strömmar används | Självbetjänad topic-/strömprofil med register, schemaevolution, åtkomstpolicy, kvoter, retention och automatiska kompatibilitetstester. |
| CAP-IT-06 / PLS-080 | Viktig där kontrakt används | Kritisk vid många oberoende team | Kontrakt som självbetjänade, versionsstyrda artefakter med kvalitetspipeline, ägarmetadata, schema-policy och automatiserade brytändringskontroller. |
| CAP-IT-06 / PLS-023 | Kritisk där filutbyte används | Kritisk vid omfattande filflöden | Självbetjänad filöverföringsprofil med partnerspecifika behörigheter, onboarding, automatisk antivirus-/innehållskontroll enligt risk och mätbart SLA. |
| CAP-IT-06 / PLS-079 | Kritisk vid extern anslutning | Kritisk vid omfattande partnerportfölj | Standardiserad anslutningsprofil per riskklass, automatiserade kontroller, katalog över motparter, självbetjäning av låg risk och styrd avveckling. |
| CAP-IT-06 / PLS-075 | Situationsberoende | Kritisk vid bred fältportfölj | Återanvändbar offline-/synkgrund med säker lokal datalivscykel, enhets-/identitetskoppling, självbetjänade SDK-profiler och automatiserade konflikttester. |
| CAP-IT-01 / PLS-001 | Kritisk vid många team | Kritisk vid många team | Versionerade komponentpaket och design tokens, tillgänglighetsregression i CI, migrationsguider, deprecationspolicy, support och adoptionsmätning. |
| CAP-IT-01 / PLS-002 | Kritisk vid självbetjäning | Kritisk vid många team | Självbetjänad projektgenerator, testsvit, komponentintegration, dependency-uppdateringar och lättanvända säkra leveransmallar. |
| CAP-IT-01 / PLS-003 | Viktig vid återkommande formulär | Viktig vid stor återanvändning | Versionerade formulärdefinitioner, valideringskontrakt, tillgängliga standardkomponenter, testmiljö och konfigurerbar publiceringsprocess. |
| CAP-IT-01 / PLS-004 | Kritisk vid verksamhetskritiska aviseringar | Viktig vid bred kanalanvändning | Självbetjänade godkända notifieringsprofiler, mall-/kanalversionering, preferenser, samtycken där relevant, kvoter och leveransstatistik. |
| CAP-IT-01 / PLS-074 | Viktig vid många geoflöden | Viktig vid många geoflöden | Självbetjänade kart-/geokodningsprofiler med licens-/kostnadskontroll, SLO, tillgängliga textalternativ och datakvalitet. |
| CAP-IT-01 / PLS-089 | Viktig vid omfattande medieflöden | Viktig vid stor medieportfölj | Självbetjänade distributionsprofiler, mätbar latency/kostnad, rättighetsvillkor, signerade länkar och tillgängliga textnings-/alternativspår. |
| CAP-IT-01 / PLS-075 | Kritisk om offline är verksamhetskrav | Kritisk vid omfattande fältverksamhet | Självbetjänad offline-SDK/profil med krypterad cache, policy för datalivslängd, testverktyg för konflikter och telemetri. |
| CAP-IT-02 / PLS-005 | Kritisk vid komplexa flöden | Kritisk vid bred återanvändning | Självbetjänad processruntime med standardiserade exekveringsprofiler, skalning, spårbarhet, rollback/migrering av definitioner och isolering mellan konsume |
| CAP-IT-02 / PLS-006 | Kritisk vid återkommande casebehov | Viktig vid stor caseportfölj | Versionerade generiska casebyggblock: tillstånd, milstolpar, auditspår, uppgiftsrelationer, dokumentreferenser och delad säkerhetsprofil. |
| CAP-IT-02 / PLS-007 | Kritisk vid stora handläggningsflöden | Viktig vid många konsumenter | Självbetjänat task-API med köprofil, SLA, revisionsspår, standardiserad notifieringskoppling och integration med identitet. |
| CAP-IT-02 / PLS-004 | Kritisk när avisering krävs | Viktig vid bred användning | Självbetjänade aviseringsprofiler, mottagarpreferenser, kanalpolicy, mallar, kvoter, spårbarhet, åtkomststyrning och uppföljning av leveransutfall. |
| CAP-IT-03 / PLS-008 | Kritisk vid omfattande regelåteranvändning | Viktig vid många regelportföljer | Självbetjänad runtime med versionspinning, isolerade beslutsdefinitioner, godkänd dataåtkomst, telemetri, säker rollback och definierad driftsprofil. |
| CAP-IT-03 / PLS-009 | Viktig vid föränderliga regelportföljer | Viktig vid återkommande modellbehov | Självbetjänad modelleringsmiljö med återanvändbara mallar, simulering, versionsdiff, semantisk validering, tester, attester och publiceringsgrindar. |
| CAP-IT-11 / PLS-045 | Kritisk för förvaltad digital arbetsplats | Kritisk vid många team/enheter | Automatiserad enrollment, roll-/riskbaserade profiler, compliance-API, styrd ändringshantering, drifttelemetri, återställning av policy och automatiserad a |
| CAP-IT-11 / PLS-046 | Viktig för installerade appar, inte generellt för rena webbappar | Viktig vid stor appportfölj | Självbetjänad godkänd appkatalog, automatisk tilldelning utifrån behov/behörighet, deklarativ uppdateringspolicy, stegvis deployment och automatiserad bort |
| CAP-IT-11 / PLS-077 | Kritisk | Kritisk | Obligatorisk skyddsprofil vid enrollment, policy-as-code-liknande kontroll, automatiska täckningsmått, riskbaserad isolering och dokumenterade undantag med |
| CAP-IT-11 / PLS-047 | Situationsberoende | Viktig vid återkommande behov | Självbetjänad provisionering från godkända images/profiler, autoskalning där ekonomiskt rimligt, policy för sessionsdata, central observability och automat |
| CAP-IT-05 / PLS-017 | Situationsberoende | Viktig när behovet återkommer | Gemensam gateway med tillåtna modeller, autentisering, kvoter, versionsbyte, loggning och isolerade konsumenter |
| CAP-IT-05 / PLS-099 | Situationsberoende | Viktig när behovet återkommer | Versionerade features med point-in-time-korrekt retrieval, batch/online-paritet och styrd åtkomst |
| CAP-IT-05 / PLS-096 | Situationsberoende | Viktig när behovet återkommer | Förvaltade träningsjobb med köer, kvoter, experimenttracking och miljöversionering |
| CAP-IT-05 / PLS-016 | Situationsberoende | Viktig när behovet återkommer | Standardiserad modellserving med skalning, canary/rollback, latensmål och mått på modellbeteende |
| CAP-IT-05 / PLS-019 | Kritisk för produktions-AI | Viktig när behovet återkommer | Gemensam evalpipeline och kvalitetströsklar före AI-release, inklusive säkerhets- och integritetstest |
| CAP-IT-05 / PLS-064 | Viktig | Viktig när behovet återkommer | Självbetjänad warehouse/lakehouse-profil med säker dataseparering, kostnadskontroll och datalivscykel |
| CAP-IT-05 / PLS-065 | Viktig | Viktig när behovet återkommer | Versionshanterade pipelines som tjänst med automatiska tester, driftschema, lineage och återkörning |
| CAP-IT-05 / PLS-015 | Viktig | Viktig när behovet återkommer | Självbetjänad BI med certifierade dataset, styrda behörigheter och standardiserat måttlager |
| CAP-IT-05 / PLS-098 | Viktig | Viktig när behovet återkommer | Certifierade semantiska kontrakt som används av BI och dataappar med ansvariga dataägare |
| CAP-IT-05 / PLS-082 | Kritisk för besluts-/AI-data | Viktig när behovet återkommer | Standardiserade datakvalitetskontrakt med automatiska tester, avvikelselarm och katalogkoppling |
| CAP-IT-05 / PLS-083 | Situationsberoende | Viktig när behovet återkommer | Förvaltad grafprofil med åtkomst, backupintegration, prestanda och schemalivscykel |
| CAP-IT-05 / PLS-074 | Situationsberoende | Viktig när behovet återkommer | Återanvändbara geotjänster med kvalitetsmått, licensvillkor och standardiserad åtkomst |
| CAP-IT-05 / PLS-090 | Situationsberoende | Viktig när behovet återkommer | Självbetjänad OCR/transkribering med styrd datalagring, kvalitetsmått och versionshantering |
| CAP-IT-05 / PLS-088 | Situationsberoende | Viktig när behovet återkommer | Förvaltad transkodningstjänst med skalning, formatprofiler och automatiska returer |
| CAP-IT-05 / PLS-018 | Viktig för organisationens RAG-lösningar | Viktig när behovet återkommer | Förvaltad retrievalpipeline med chunkning, embedding/index och dokumentbaserade ACL-kontroller |
| CAP-IT-05 / PLS-014 | Viktig vid informationsintensiva IT-stöd | Viktig när behovet återkommer | Självbetjänad indexering, skalbar sökprofil, ACL-synk och livscykel |

### Godkännandekriterier
- Minst ett verkligt ändrings-/fel-/åtkomstscenario demonstrerat över berörda tjänstegränser.
- Skydd, spårbarhet och rollback/återställning har verifierats av ansvariga team.
- Tjänster som klassats situationsberoende etableras först när identifierade konsumenter motiverar investeringen.
- Underlag för beslut innehåller mätbar effekt, livscykelägare och driftkostnad.
