# Faktakontroll och källspårbarhet – första publiceringspasset (r0056)

**Datum:** 2026-11-08  
**Utgångspunkt:** Samtliga manuskapitel 00–17 i projekt r0055.  
**Avgränsning:** Identifiering av centrala prövbara sakpåståenden, första kontroll mot utvalda primärkällor och dokumentation av kvarstående risker. **Inga kapiteltexter har ändrats.** Detta är inte en fullständig oberoende teknisk, juridisk eller vetenskaplig faktagranskning.

## Samlad slutsats

Manusets överordnade resonemang är tekniskt rimligt och stämmer i huvudsak med etablerade principer om interna plattformar, självbetjäning, säker programvaruleverans, riskhantering, isolering och ekonomisk uppföljning. Inga uppenbart felaktiga generella teknikpåståenden har identifierats i detta urval. Det är dock fel att kalla bokens fyra generationer för en externt validerad standard eller att dra slutsatsen att generation 4 kommer att uppnås likadant i alla stora organisationer. Denna framtidsmodell är ett författarresonemang. Påståenden om faktiska licensavtal, rättsligt bindande krav, produktspecifika leveransgarantier och AI-agentsystems beteende måste fortsatt behandlas med villkor och prövas vid konkret tillämpning.

### Prioriterade fynd

1. **OWASP-utgåvan har ändrats (prioritet hög för källregistret):** `docs/faktakontroll.md` hänvisar i äldre revisionsnotering till OWASP 2025. Officiellt projekt anger nu *OWASP Top 10 for Large Language Model Applications 2026*, publicerad 2026-08-04 [K004]. Den tidigare noteringen har behållits som historik men försetts med aktuellt förtydligande. Ett eventuellt framtida bokcitat ska använda relevant, daterad utgåva. De namngivna riskkategorierna och deras ordning har också ändrats mellan utgåvorna.
2. **G3-plattformar är väl underbyggda (hög tilltro till princip):** DORA beskriver intern plattform som produkt med självbetjäningsflöden [K002]. Detta stödjer syftet med att gå från specialistköer till utvecklingsteamens självständighet. DORA har däremot inte belagt just bokens G1–G4-modell.
3. **Säkerhet i publiceringsvägen är väl grundad (hög tilltro till princip):** NIST SSDF rekommenderar systematiska säkerhetspraktiker i utvecklingslivscykeln [K001]. Säkerhetskontroller minskar risk men kan inte garantera att genererad eller manuellt skriven kod är säker.
4. **AI-agenter måste riskprövas (hög tilltro till riskens existens):** NIST AI 600-1 och OWASP 2026 stödjer att generativ AI kräver riskbedömning och att prompt injection, för omfattande agentsjälvständighet, informationsläckage och hög förbrukning är relevanta risker [K003, K004]. Källorna bevisar inte att alla föreslagna skydd räcker i ett visst verksamhetssystem.
5. **Skydd mot noisy neighbor är tekniskt väl belagt men har gränser:** Kubernetes kvoter och multitenancy-dokumentation ger konkreta motåtgärder [K005, K006]. Kvoter för CPU/minne skyddar inte automatiskt nättrafik, externa API:er eller alla gemensamma beroenden. Manusets reservation om detta är viktig.
6. **Trafikpolicy och verksamhetsmandat bör förbli separata:** NIST zero trust betonar att nätverksplacering inte ger implicit tillit [K007]. Lokal behörighetslogik och lagliga mandat beror dock på domän, säkerhetspolicy och faktisk implementation.
7. **Observability-begreppen är standardmässiga:** OpenTelemetry beskriver loggar, mätvärden och spårningar [K008]. Detta verifierar termerna, inte en automatisk förmåga att återställa hela verksamhetsflöden.
8. **Ekonomistyrning är stödjbar men verklig licenskostnad är avtalsspecifik:** FinOps-principerna stöder insyn, ansvar och optimering efter nytta [K009]. Inga konkreta per-användare-priser, rabatter eller licensvillkor är verifierade i manus. Alla kostnadsexempel ska fortsatt vara generiska.
9. **Proveniens får inte överförklaras:** SLSA definierar var/när/hur en byggartefakt skapats [K010]; det bevisar inte automatiskt reproducerbarhet, korrekt funktion eller frihet från sårbarheter.

## Kapitelvis kontrollmatris

Status avser **det särskilt granskade sakområdet**, inte ett totalt godkännande av kapitlet.

| Kapitel | Särskilt granskat påstående | Bedömning i denna kontroll | Primärkällor / fortsatt prövning |
|---|---|---|---|
| 00 Inledning | Fyra generationer är tankemodell | Tydligt markerat som analytisk, ej standard | Redaktionellt modellbeslut; inte extern sakfråga |
| 01 När IT blir en broms | Distribuerade tjänster ger fler koordinationsberoenden | Rimlig systemarkitekturanalys, inte empiriskt kvantifierad här | Kvalitativ princip; empiriska effekter kvarstår |
| 02 Fyra generationer | G3 självständiga team, G4 även verksamhet | DORA stöder G3-principer; G4 framtidsanalys | K002; G4 bör inte presenteras som uppnådd standard |
| 03 Gemensamma IT-förmågor | Kapabilitet kontra produkt; G4-kostnader | Analysmodell med stödjande ekonomiprinciper | K002, K009; modell är bokens egen |
| 04 Interaktion och kanaler | Formulär, PWA och klientkanaler | Begreppsligt rimligt; särskilda plattformsegenskaper ej verifierade | Tillgänglighetskrav och mobil/offline bör prövas separat |
| 05 Process och workflow | Långlivade processer, versioner och dubbelutförande | Rimliga designrisker, inte produktgarantier | Verifiera vid val av workflowmotor |
| 06 Regler och beslut | Regelresultat är inte alltid formellt beslut | Korrekt viktig princip i bokens ansvarslinje | Rättslig bedömning är domänspecifik |
| 07 Datahantering | Konsistens, backup och lagringsprofiler varierar | Rimligt, men inga tjänstespecifika SLA verifierade | Verifiera lagringsprofil, backup/RPO/RTO och licenser per tjänst |
| 08 Analys och AI | RAG/AI-användning, AI-risker och begränsningar | AI-riskernas förekomst stöds | K003, K004; operativ kvalitet kräver lokala tester |
| 09 Integration | Transportkvittens skild från processutfall; återförsök | Teknisk princip rimlig, inga leveransgarantier belagda för produkt | Test av kö/ström/API och idempotens vid införande |
| 10 Identitet | Arbetslastidentitet skild från delegerat mandat | Konsekvent med principen om explicit åtkomstprövning | K007; delegationens juridik/implementation kvarstår |
| 11 Slutanvändarmiljö | Lokal exekvering och klientisolering | Teknikprincip rimlig; klientskydd varierar | Verifiera faktisk klient-/appmodell och BYOD-villkor |
| 12 Cybersäkerhet | Skydd, sårbarhetsarbete och AI-angrepp | God principgrund, skydd aldrig fullständig garanti | K001, K003, K004, K007 |
| 13 Utveckling/leverans | Säker leveranskedja, självbetjäning och proveniens | Principer grundade, leveransutfall måste mätas | K001, K002, K010; integritet ≠ reproducerbarhet |
| 14 Körmiljö | Resursgränser och isolering minskar påverkan | Väl stödd med uttryckliga begränsningar | K005, K006; extern belastning separat |
| 15 Nätverk | Nätåtkomst räcker inte för applikationsbehörighet | Tydligt stöd i zero trust-principer | K007; inga produktbundna policygarantier verifierade |
| 16 Driftbarhet | Loggar, mätvärden, spårningar och återställning | Telemetribegrepp verifierade; återställningsförmåga kontextuell | K008; övningar och dataåterställning separat |
| 17 Ansvar/kompetens | Plattform som produkt; kostnadsansvar och G4-styrning | Principer underbyggda; organisationsutfall framtids-/ledningsanalys | K002, K009; ingen generell ROI bevisad |

## Viktiga kvarvarande frågor före faktagodkännande

### Prioritet hög

- **Rättslig kontroll:** Vem får utforma, godkänna respektive automatisera formella verksamhetsbeslut? Uppgifter om mandat, loggning, retention och behandling av personuppgifter kan inte godkännas generellt utan tillämplig sektor, lagstiftning och nationell jurisdiktion. Kap 5–6, 8–10, 12, 17.
- **AI-kvalitet och säkerhet:** Separat specialistgranskning av RAG, agenters handlingsutrymme, prompt-injection-skydd och AI-utvärdering. Kontrollera aktuell OWASP 2026 där äldre 2025-referenser förekommer. Kap 8, 10, 12–13, 17.
- **Källhänvisningar i färdiga manuset:** Besluta hur K001–K010 kopplas till läsarkapitlen och var källförteckningen placeras. Ett källregister utan hänvisningar gör det svårt för läsaren att skilja källa från analys.

### Prioritet medel

- **Produkt- och leverantörsberoenden:** Verifiera stöd för isolering, behörighetskontroller, versionshantering, exporterbarhet samt faktiska licens- och API-kostnader innan ett konkret plattformsval rekommenderas. Kap 4–5, 7–9, 11, 13–14, 17.
- **Drift och kontinuitet:** Kontrollera att påståenden om återställning, säkerhetskopiering och spårbarhet inte förväxlas med en testad förmåga i verklig miljö. Kap 7, 9, 14, 16.
- **Läsbarhet och sakprecision:** Behåll formuleringar som ”kan”, ”bör”, ”inom godkända ramar” där de uttrycker teknisk eller organisatorisk variation. Undvik att skriva om dem till ”garanterar” eller ”alltid”.

### Prioritet lägre

- Rensa äldre arbetsnoteringar i `docs/projektstatus.md` och `project-index.md` först när historiken kan bevaras någon annanstans; båda innehåller tidiga statusrader som är historiska, inte aktuell projektstatus.
- Slutlig bibliografisk formatering och publikationsdatum samt eventuella beständiga länkar.

## Metod och begränsningar

1. Läste/manuellt kontrollerade samtliga kapitel 00–17, projektets källpolicy och faktakontrollregister.
2. Slog upp ett urval av tio auktoritativa källor hos ansvariga organisationer eller officiella projekt.
3. Jämförde källornas faktiska räckvidd med bokens påståenden; noterade där källan stödjer ett teknikbegrepp snarare än bokens slutsatser.
4. Inventerade kvarstående frågor som förutsätter specialistkunskap, juridisk prövning, produktdokumentation eller test i faktisk miljö.
5. Inga bokkapitel, källmaterial eller YAML-modeller har ändrats. Ingen formell extern kollegial sakgranskning har utförts.

**Statusbeslut:** *Första källkontrollpass genomfört – inga kapitel godkända för publicering enbart genom detta pass.*
