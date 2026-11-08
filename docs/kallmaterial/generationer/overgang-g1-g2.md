# Från sammanhållna system till distribuerade IT-stöd

**Mål:** Sammanhängande och felsökbara tjänstekedjor med tydliga ansvar och kontrakt.

Detta är en rekommenderad ordningsföljd av **förmågeutveckling**, inte ett påstående om att alla plattformstjänster behövs i alla system. Vågorna är överlappande och vissa arbeten bör gå parallellt.

## Våg 1: A. Grundskydd och ägarskap
Identifiera och skydda tjänster, data, trafik och återställningsmöjligheter innan tjänsteantalet ökar kraftigt.

### CAP-IT-07 – Identitet och tillit
Federation, maskinidentiteter och återkallelse
**Tjänster i baseline:** PLS-025, PLS-085, PLS-026, PLS-030, PLS-063, PLS-027, PLS-028, PLS-029, PLS-068, PLS-079.

### CAP-IT-09 – Driftbarhet och motståndskraft
Korrelerad övervakning och restore av beroendekedjor
**Tjänster i baseline:** PLS-037, PLS-038, PLS-035, PLS-070, PLS-036.

### CAP-IT-12 – Cybersäkerhet och tekniskt skydd
Samordnad hot-/sårbarhetshantering över tjänster
**Tjänster i baseline:** PLS-079, PLS-069, PLS-052, PLS-077, PLS-050, PLS-051, PLS-048, PLS-078, PLS-086, PLS-053, PLS-087.

### CAP-IT-13 – Nätverk och konnektivitet
Kontrollerade tjänsteflöden och segmentering
**Tjänster i baseline:** PLS-057, PLS-079, PLS-072, PLS-054, PLS-055, PLS-071, PLS-089, PLS-056, PLS-073, PLS-058, PLS-076, PLS-087.

## Våg 2: B. Reproducerbar teknisk leverans
Få kontroll på kod, konfiguration, driftmiljö, datamigrering och releases.

### CAP-IT-10 – Utveckling och teknisk leverans
Versionskontroll, automatiska tester och repeterbara releaser
**Tjänster i baseline:** PLS-039, PLS-040, PLS-041, PLS-042, PLS-092, PLS-093, PLS-086, PLS-094, PLS-095, PLS-019.

### CAP-IT-08 – Applikationsexekvering och körmiljö
Standardiserade runtimeprofiler och styrda ändringar
**Tjänster i baseline:** PLS-032, PLS-091, PLS-031, PLS-033, PLS-034, PLS-078.

### CAP-IT-04 – Datahantering och informationslagring
Dataägarskap, konsistens och schema-/migreringskontrakt
**Tjänster i baseline:** PLS-064, PLS-065, PLS-098, PLS-066, PLS-082, PLS-067, PLS-012, PLS-081, PLS-083, PLS-010, PLS-097, PLS-074, PLS-013, PLS-011, PLS-088, PLS-075, PLS-084.

## Våg 3: C. Samverkan över tjänstegränser
Versionera kontrakt och kunna återuppta/laga tvärsystemflöden; separat workflow/regelplattform endast vid behov.

### CAP-IT-06 – Integration och informationsutbyte
Versionshanterade API-/meddelandekontrakt, idempotens
**Tjänster i baseline:** PLS-020, PLS-024, PLS-021, PLS-022, PLS-080, PLS-023, PLS-079, PLS-075.

### CAP-IT-02 – Process, workflow och ärendehantering
Återupptagningsbara tvärsystemprocesser vid behov
**Tjänster i baseline:** PLS-005, PLS-006, PLS-007, PLS-004.

### CAP-IT-03 – Regler och beslut
Reproducerbara, versionerade domänbeslut vid behov
**Tjänster i baseline:** PLS-008, PLS-009.

## Våg 4: D. Användar- och informationshelhet
Motverka fragmenterad användarupplevelse och motstridiga rapporter över systemgränser.

### CAP-IT-01 – Interaktion, presentation och kanaler
Enhetlig användarresa över tjänstegränser
**Tjänster i baseline:** PLS-001, PLS-002, PLS-003, PLS-004, PLS-074, PLS-089, PLS-075.

### CAP-IT-11 – Slutanvändarmiljö och klientplattform
Hantering av heterogen klientflotta
**Tjänster i baseline:** PLS-045, PLS-046, PLS-077, PLS-047.

### CAP-IT-05 – Analys, sökning och intelligent informationsbearbetning
Konsistenta rapporter och spårbara datapipelines
**Tjänster i baseline:** PLS-017, PLS-099, PLS-096, PLS-016, PLS-019, PLS-064, PLS-065, PLS-015, PLS-098, PLS-082, PLS-083, PLS-074, PLS-090, PLS-088, PLS-018, PLS-014.

## Förslag på prioritering och verifiering
Använd de fem grundkraven: tjänsteägare, repeterbarhet, policy/säkerhet, verifierbar leverans och återställbarhet. Besluta först vilka konsumenter och riskklasser som omfattas.

### Detaljerad tjänstevis prioritering
Kriterier nedan avser **målbilden G2**. Formuleringar som ”där…”, ”vid…” och ”för…” är viktiga för villkorad kritikalitet.

| Förmåga / tjänst | Funktionskritikalitet | Gemensam tjänst | Målkrav (förkortat) |
|---|---|---|---|
| CAP-IT-09 / PLS-037 | Kritisk | Viktig | Applikations- och datakonsistenta kopior tvärs databaser, köer och beroenden; säkrade kopior, versions- och schemahantering samt återställningsordning. |
| CAP-IT-09 / PLS-038 | Kritisk för verksamhetskritiska kedjor | Viktig | Karta över beroenden och felområden; sekvenserad återstart av API:er, data, meddelandeköer, identitet och nätverk; fallback vid partiell degradering. |
| CAP-IT-09 / PLS-035 | Kritisk | Viktig | Gemensamma korrelations-ID, fördelade traces, mätvärden per tjänst och applikationsflöde, strukturerade loggar, servicekarta och riktad dataskyddsfiltrerin |
| CAP-IT-09 / PLS-070 | Viktig för reglerade/kritiska kedjor | Situationsberoende | Gemensamma händelseidentifierare och identitetsreferenser över tjänstegränser; tidsstämplar och skydd mot efterhandsändring. |
| CAP-IT-09 / PLS-036 | Kritisk | Viktig | End-to-end-hälsokontroller, felkvoter, latens och beroendestatus; mindre brus, tydlig jourkedja, deduplicering och larm på symptom. |
| CAP-IT-08 / PLS-032 | Viktig för VM-beroende tjänster | Viktig | Standardisera VM-profiler och nät/identitetskopplingar, automatisera skapande, säkerställ konsekvent konfiguration och definierade ägare när tjänster förde |
| CAP-IT-08 / PLS-091 | Viktig för berörda applikationer | Viktig där flertal delar runtime | Stöd flera oberoende tjänster/instanser med separata konfigurationer, certifikat, beroenden, säker uppgradering och tydliga miljökontrakt. |
| CAP-IT-08 / PLS-031 | Viktig för containerbaserade mikrotjänster | Viktig | Isolera tjänster, deklarera resurser, exponeringsgränser, identitet, konfiguration och hälsokontroller; definiera rollout- och skalningsbeteende genom sams |
| CAP-IT-08 / PLS-033 | Viktig där bakgrundsjobb finns | Viktig | Separera jobb per tjänst och miljö; standardisera retries, idempotens, låsning, samtidighetsgränser och tidsgränser. Beakta API/köberoenden. |
| CAP-IT-08 / PLS-034 | Situationsberoende | Situationsberoende | Isolera resurskrävande arbetslaster, hantera prioritering/kö och tekniska beroenden över tjänstegränser. |
| CAP-IT-08 / PLS-078 | Kritisk för högriskworkloads | Viktig | Skydd som omfattar VM/container/tjänstegränser, identifierar otillåten process-, nät- eller filaktivitet och kan koppla fynd till workloadägare. |
| CAP-IT-10 / PLS-039 | Kritisk | Kritisk | Tillämpa pull requests, skyddade grenar, ägargranskning och tydliga tjänste-/repoägare. |
| CAP-IT-10 / PLS-040 | Kritisk | Viktig | Automatisera test och leverans per tjänst; använd isolerade byggjobb, skyddade credentials och reverseringssteg. |
| CAP-IT-10 / PLS-041 | Kritisk | Viktig | Lagra immutable artefakter centralt per team/tjänst; styr åtkomst och livslängd. |
| CAP-IT-10 / PLS-042 | Viktig | Viktig | Inför IaC för återkommande miljöer; ändringar granskas och driftavvikelse upptäcks. |
| CAP-IT-10 / PLS-092 | Viktig | Viktig | Standardisera tjänsteskelett med API-kontrakt, klienttimeouts, test och telemetry; tillåt motiverade undantag. |
| CAP-IT-10 / PLS-093 | Situationsberoende | Viktig vid mobilportfölj | Automatisera plattformsspecifika byggen och enhetstester; skydda signeringsmaterial. |
| CAP-IT-10 / PLS-086 | Kritisk | Viktig | Inför automatiska SAST/SCA/secrets-kontroller där pipeline finns; triagera med risk och ägare. |
| CAP-IT-10 / PLS-094 | Bra att ha | Situationsberoende | Tillåt avgränsade assistenter om nyttan kan visas; säkerställ kodskydd och loggad användning. |
| CAP-IT-10 / PLS-095 | Situationsberoende | Situationsberoende | Pilotera SDK och promptversionering vid konkret behov, utan att föreskriva generell agentplattform. |
| CAP-IT-10 / PLS-019 | Situationsberoende | Situationsberoende | Inför versionssatta eval-dataset och regressionsfall för förekommande modeller. |
| CAP-IT-13 / PLS-057 | Kritisk | Viktig | Tjänstevis routning, hälsokontroller, TLS-hantering och spårbar konfiguration för flera oberoende komponenter. |
| CAP-IT-13 / PLS-079 | Kritisk | Viktig | Standardiserad partinventering, krypterade anslutningar och testade beroenden mellan anslutning och informationsutbyte. |
| CAP-IT-13 / PLS-072 | Kritisk | Kritisk | Routning och segmentering mellan många workloads, kontroll av öst–väst-trafik och kapacitetsuppföljning. |
| CAP-IT-13 / PLS-054 | Kritisk | Kritisk | Inventering av tjänsteadresser och namn i flera miljöer, automatiserad upptäckt och konflikthantering. |
| CAP-IT-13 / PLS-055 | Kritisk | Viktig | Enhetsbaserad segmentering, central policy och uppföljning av kapacitet när fler digitala tjänster används. |
| CAP-IT-13 / PLS-071 | Kritisk | Viktig | Mätbar latens, kapacitet och redundans för distribuerade beroenden; tydliga prioriteringar för kritiska flöden. |
| CAP-IT-13 / PLS-089 | Situationsberoende | Situationsberoende | Skalbar distribution/caching för flera kanaler, accesskontroller och stabil leverans vid varierande last. |
| CAP-IT-13 / PLS-056 | Kritisk | Viktig | Rollseparerad åtkomst till distribuerade tjänstemiljöer utan bred intern nätåtkomst. |
| CAP-IT-13 / PLS-073 | Kritisk | Kritisk | Tjänstespecifik internetexponering och utgående beroenden kartläggs; övervakning av egress och felvägar. |
| CAP-IT-13 / PLS-058 | Kritisk | Kritisk | Tjänste- och miljönära trafikpolicy, begränsning av lateral rörelse och spårbar ändringshantering. |
| CAP-IT-13 / PLS-076 | Situationsberoende | Situationsberoende | Prioriterad kommunikation och uppföljning över flera system och användargrupper i fält. |
| CAP-IT-13 / PLS-087 | Kritisk vid extern exponering | Viktig | API-/webbskydd med tjänstespecifik policy, rate limiting och synlighet för distribuerade endpoints. |
| CAP-IT-07 / PLS-025 | Kritisk | Kritisk | Gemensam SSO/federation och tokenvalidering mellan flera applikationer; starkare autentisering efter risk. |
| CAP-IT-07 / PLS-085 | Kritisk | Kritisk | Samma identifierare och kvalitetssäkrade attribut för flera system; hantera kopior, synk och motstridiga uppgifter. |
| CAP-IT-07 / PLS-026 | Kritisk | Kritisk | Konsoliderad rättighetsinventering, joiner/mover/leaver-flöden och regelbunden omprövning. |
| CAP-IT-07 / PLS-030 | Kritisk | Viktig | Konsekventa tjänstegränskontroller och uttryckliga anropskontexter; delad policy där flera tjänster kräver samma prövning. |
| CAP-IT-07 / PLS-063 | Kritisk | Kritisk | Central hantering och spårning av privilegier över många komponenter; hårdare kontroll av delade adminkonton. |
| CAP-IT-07 / PLS-027 | Kritisk | Kritisk | Unik identitet per tjänst/miljö och skyddat service-till-service-förtroende; inga gemensamma långlivade tekniska konton. |
| CAP-IT-07 / PLS-028 | Kritisk där certifikat behövs | Kritisk | Gemensam certifikatinventering, förnyelse och trust-hantering över fler system och gränssnitt. |
| CAP-IT-07 / PLS-029 | Kritisk där hemligheter används | Kritisk | Centraliserad secrets-distribution, revisionsloggning och rotation för många tjänster/miljöer. |
| CAP-IT-07 / PLS-068 | Situationsberoende | Viktig vid stor användning | Återanvändbara signeringsintegrationer och identitetskopplingar över flera ärende-/dokumentflöden. |
| CAP-IT-07 / PLS-079 | Kritisk vid extern tillit | Viktig | Inventerade partneridentiteter, tydliga trust boundaries och samordnad certifikat-/kontoavveckling vid ändring. |
| CAP-IT-12 / PLS-079 | Situationsberoende | Viktig | Separata säkra profiler per partner, central registrering av certifikat, incidentkontakt och avveckling. |
| CAP-IT-12 / PLS-069 | Viktig | Viktig | DLP-kontroller samordnas över endpoint, e-post och molntjänster och får tydligt ägarskap. |
| CAP-IT-12 / PLS-052 | Kritisk | Viktig | Central kontroll av nyckelåtkomst och rotation för fler tjänster; separata nycklar per skyddsdomän. |
| CAP-IT-12 / PLS-077 | Kritisk | Kritisk | Central EDR-telemetri och enhetspolicy för klienter som når distribuerade tjänster. |
| CAP-IT-12 / PLS-050 | Kritisk | Kritisk | Korrelation av identitets-, nät-, workload- och apphändelser; dokumenterade use cases. |
| CAP-IT-12 / PLS-051 | Kritisk | Viktig | Korrelation och tidslinje över tjänstegränser; kontrollerade förfaranden för forensiska kopior. |
| CAP-IT-12 / PLS-048 | Kritisk | Kritisk | Sårbarheter sätts i sammanhang med exponering och berörda tjänstekedjor. |
| CAP-IT-12 / PLS-078 | Kritisk | Kritisk | Separat skydd per tjänst samt kontroll av lateral rörelse och runtimebeteende. |
| CAP-IT-12 / PLS-086 | Kritisk | Viktig | Automatisk SAST/SCA och secrets-scan i olika tjänsters pipelines samt triageansvar. |
| CAP-IT-12 / PLS-053 | Viktig | Viktig | Gemensamma policykontroller i CI/CD och körmiljö med separata ägare för undantag. |
| CAP-IT-12 / PLS-087 | Kritisk | Viktig | API-specifika skyddsregler, rate limit och botdetektion över tjänstekedjor. |
| CAP-IT-04 / PLS-064 | Viktig | Viktig | Separat analytisk lagring med styrda inläsningar, partitionering och kapacitetsplanering för många källor. |
| CAP-IT-04 / PLS-065 | Kritisk | Viktig | Idempotenta pipelines, versionsstyrda scheman och återkörning vid delvis misslyckad inläsning. |
| CAP-IT-04 / PLS-098 | Viktig | Situationsberoende | Gemensamma versionsstyrda mått prioriteras för tvärfunktionella analyser. |
| CAP-IT-04 / PLS-066 | Viktig | Viktig | Gemensamma metadata och manuellt kompletterad härkomst över centrala dataflöden. |
| CAP-IT-04 / PLS-082 | Kritisk | Viktig | Automatiserade kvalitetskontroller vid gränsövergångar och dataladdningar med avvikelseägare. |
| CAP-IT-04 / PLS-067 | Viktig | Viktig | Gemensam distribution med versionsnummer, identitetsmatchning och felhantering. |
| CAP-IT-04 / PLS-012 | Situationsberoende | Viktig | Cache-policy för flera tjänster med invalidation och skydd mot stale reads. |
| CAP-IT-04 / PLS-081 | Situationsberoende | Viktig | Tjänstvisa ägarskap, indexeringsprofiler och schemaevolution över konsumenter. |
| CAP-IT-04 / PLS-083 | Situationsberoende | Situationsberoende | Kontrollerade grafimporter och relationstyper; källsystemens ägarskap dokumenteras. |
| CAP-IT-04 / PLS-010 | Kritisk | Kritisk | Isolerade databaser/schemaägarskap per tjänst, versionsstyrda migrationer och kontrollerad kompatibilitet. |
| CAP-IT-04 / PLS-097 | Viktig | Situationsberoende | Federerade läsfrågor med tidsgränser, källbelastningsskydd och ansvar för frågekostnad. |
| CAP-IT-04 / PLS-074 | Situationsberoende | Viktig | Samordnade geodatatjänster och uppdateringsfrekvens över flera fält- och ärendetjänster. |
| CAP-IT-04 / PLS-013 | Kritisk | Kritisk | Isolerade volymer per workload med konsekvent åtkomst och flytt-/snapshothantering. |
| CAP-IT-04 / PLS-011 | Viktig | Viktig | Gemensamma säkra buckets, versionshantering, livscykelregler och händelseintegration. |
| CAP-IT-04 / PLS-088 | Situationsberoende | Viktig | Asynkron transkodning med kö, retry och format-/codecstandarder för flera tjänster. |
| CAP-IT-04 / PLS-075 | Situationsberoende | Viktig | Synkronisering med checkpoint, konfliktstrategier och säkra enhetsidentiteter över tjänster. |
| CAP-IT-04 / PLS-084 | Viktig | Viktig | Gemensam generering med versionshanterade mallar, central kvalitet och deterministiska utdata. |
| CAP-IT-06 / PLS-020 | Kritisk där API används | Viktig | Versionshanterade API-kontrakt, gateway/skydd där exponeringsrisk finns, konsumentinventering, tidsgränser och kontrollerade breaking changes mellan distri |
| CAP-IT-06 / PLS-024 | Viktig där många adapterbehov | Viktig | Återanvändbara adaptrar, idempotent meddelandehantering, korrelations-ID och kontrollerad teknisk retry; undvik central punkt som äger all domänlogik. |
| CAP-IT-06 / PLS-021 | Kritisk där tillförlitlig kö behövs | Viktig | Förvaltade köer med retry, dead-letter-kö, backpressure, korrelations-ID och idempotenta konsumenter; dimensionera och separera felområden. |
| CAP-IT-06 / PLS-022 | Viktig vid eventdriven arkitektur | Situationsberoende | Publicera domänhändelser med ägare, kontrakt, nycklar, ordningsantaganden, retention och oberoende konsumenter; kontrollera replay och dubbletter. |
| CAP-IT-06 / PLS-080 | Viktig där kontrakt används | Viktig | Delad sökbar kontraktskatalog med kompatibilitetsregler; automatiserade consumer/provider-tester, schema-validering och migrationsfönster. |
| CAP-IT-06 / PLS-023 | Kritisk där filutbyte används | Viktig där många filflöden | Spårbara filer över organisationsgränser med tekniska profiler, avtalade scheman, kvittens, omkörning och dataskydd/retention. |
| CAP-IT-06 / PLS-079 | Kritisk vid extern anslutning | Viktig vid flera partners | Konsekvent extern partneronboarding, certifikat-/identitetskontroller, segmentering, teknisk loggning, incidentkontakt och ägda kontrakt. |
| CAP-IT-06 / PLS-075 | Situationsberoende | Viktig vid flera fältappar | Flera klienter kräver återupptagbar synk, lokala köer, versionskontroll, konfliktregler och testad hantering av partiell anslutning. |
| CAP-IT-01 / PLS-001 | Viktig | Viktig | Gemensamma tokens, navigation, fel- och väntelägen; tydliga kompatibilitetsregler när flera team återanvänder komponenter. |
| CAP-IT-01 / PLS-002 | Kritisk vid många webbteam | Viktig | Delad klientarkitektur, API-kontrakt, standardiserad telemetri, säker tokenhantering och test av brutna beroenden. |
| CAP-IT-01 / PLS-003 | Viktig vid många formulär | Situationsberoende | Delade scheman, versionering av fält och förutsägbar felhantering mot flera tjänster; formulär skickar data via definierade API:er. |
| CAP-IT-01 / PLS-004 | Kritisk vid verksamhetskritiska aviseringar | Viktig vid flera appar | Gemensamma kanalspecifika mallar, korrelation, kvittensstatus, felkoder och hantering av dubbletter. |
| CAP-IT-01 / PLS-074 | Situationsberoende | Situationsberoende | Dokumenterade geodatakontrakt, cache och lämpliga API:er för flera konsumenter; separat behörighet för skyddade lager. |
| CAP-IT-01 / PLS-089 | Situationsberoende | Situationsberoende | Kontrollerad distribution via cache eller CDN vid behov; token/URL-livstid, versionsändringar och mätning av uppspelningsfel. |
| CAP-IT-01 / PLS-075 | Kritisk om offline är verksamhetskrav | Viktig vid många fältappar | Idempotent synkronisering, versionsmärkt lokalt state, konfliktdetektion och återupptagning efter nätavbrott. |
| CAP-IT-02 / PLS-005 | Kritisk vid tvärsystemprocesser | Viktig vid många flöden | Hållbar exekvering, korrelations-ID, timeout, idempotens, kompensation, versionshantering av körande instanser och översikt över hela flödet. |
| CAP-IT-02 / PLS-006 | Kritisk vid distribuerad ärendehantering | Viktig vid flera ärendesystem | Korrelera ärendestatus över tjänster; historik, delegering, sammanslagning/uppdelning där behov finns och konsekvent hänvisning till dokument och beslut. |
| CAP-IT-02 / PLS-007 | Kritisk vid många teamöverlämningar | Viktig vid flerkanalshandläggning | Samordnad uppgiftsidentitet, köpolicy, tidsfrister, eskalering, delegering och robust synk mellan flera system. |
| CAP-IT-02 / PLS-004 | Kritisk vid tidskritiska tvärsystemflöden | Viktig vid många applikationer | Händelsekorrelation, återförsök, leveransstatus, idempotens, mallversion och säker kanalval kopplat till processstatus. |
| CAP-IT-03 / PLS-008 | Kritisk vid tvärsystem- och rättsverkande beslut | Viktig vid flera konsumenter | Separera regel-API från intern implementation; explicit datakontrakt, giltighetstid, idempotenta anrop där relevant, regelversion och beslutskorrelation. |
| CAP-IT-03 / PLS-009 | Viktig för regelverk som delas av flera tjänster | Viktig vid delat beslutsbehov | Formella regler och versionerade testuppsättningar för flera konsumenter, beslutstabeller, täckningsanalys och konsekvensjämförelse mellan versioner. |
| CAP-IT-11 / PLS-045 | Kritisk vid stor eller heterogen klientflotta | Viktig | Centrerad enrollment, policy per enhetsklass, krypteringsstatus, versions-/patchrapport, fjärrlåsning och selektiv radering där detta stöds; policy även fö |
| CAP-IT-11 / PLS-046 | Viktig för många installerade klientappar | Viktig | Centralt styrda distributionsringar, kompatibilitetsmatris, signatur-/paketkontroll, inventering, återförsök och rapportering av misslyckade installationer |
| CAP-IT-11 / PLS-077 | Kritisk för förvaltade endpoints | Kritisk vid bred klientflotta | Samordnat EDR/anti-malware, endpointtelemetri, isolering, detectionsignal och samverkan med SOC; täckning av laptop och mobil där plattformen stöder det. |
| CAP-IT-11 / PLS-047 | Situationsberoende | Viktig vid många externa/tillfälliga användare | Profilbaserade virtuella desktops, separat identitet, sessionshantering, nätverkssegmentering, prestandauppföljning och tillgänglighetskrav. |
| CAP-IT-05 / PLS-017 | Situationsberoende | Situationsberoende | Kontrollerade piloter med informationsklassning, leverantörsvillkor och tokenbudget per applikation |
| CAP-IT-05 / PLS-099 | Situationsberoende | Situationsberoende | Definitioner och tränings-/inferenskonsistens vid flera prediktiva modeller |
| CAP-IT-05 / PLS-096 | Situationsberoende | Situationsberoende | Reproducerbara träningskörningar med registrerat dataset, kod, parametrar och resurser |
| CAP-IT-05 / PLS-016 | Situationsberoende | Situationsberoende | Tjänstegränssnitt, versionshantering, in-/utdataschema och övervakning av fel |
| CAP-IT-05 / PLS-019 | Kritisk när AI används i konsekvensfyllda flöden | Situationsberoende | Mätningar mot representativa testdata, feltyper, robusthet och versionsjämförelser |
| CAP-IT-05 / PLS-064 | Viktig | Situationsberoende | Samordnade historiska dataområden, partitionering, refresh och hanterbar belastning |
| CAP-IT-05 / PLS-065 | Viktig | Situationsberoende | Reproducerbar ETL/ELT med felhantering, datakvalitetskontroller och körlogg |
| CAP-IT-05 / PLS-015 | Viktig | Situationsberoende | Tvärsystemrapporter med drill-down, schemalagda rapporter och källspårbarhet |
| CAP-IT-05 / PLS-098 | Viktig vid gemensamma mått | Situationsberoende | Delade definitioner och versionering när flera system gör samma beräkningar |
| CAP-IT-05 / PLS-082 | Viktig | Situationsberoende | Kvalitetsmått, ägda regler och avvikelsehantering över dataflöden |
| CAP-IT-05 / PLS-083 | Situationsberoende | Situationsberoende | Styrd grafdatabas vid genuina frågor om relationskedjor |
| CAP-IT-05 / PLS-074 | Situationsberoende | Situationsberoende | Gemensamma koordinatsystem, kartlager och API-kontrakt för flera applikationer |
| CAP-IT-05 / PLS-090 | Situationsberoende | Situationsberoende | Standardiserad extraktion med mätning av fel och manuellt efterarbete |
| CAP-IT-05 / PLS-088 | Situationsberoende | Situationsberoende | Köbaserad formatkonvertering med standardrenditions och spårning |
| CAP-IT-05 / PLS-018 | Situationsberoende | Situationsberoende | Pilot med retrieval, åtkomstfiltrering, källproveniens och verifiering av relevans |
| CAP-IT-05 / PLS-014 | Viktig vid informationsintensiva IT-stöd | Situationsberoende | Gemensamma sökindex för flera informationskällor med relevansmätning |

### Godkännandekriterier
- Minst ett verkligt ändrings-/fel-/åtkomstscenario demonstrerat över berörda tjänstegränser.
- Skydd, spårbarhet och rollback/återställning har verifierats av ansvariga team.
- Tjänster som klassats situationsberoende etableras först när identifierade konsumenter motiverar investeringen.
- Underlag för beslut innehåller mätbar effekt, livscykelägare och driftkostnad.
