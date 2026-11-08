# Kritisk granskning och genomförd revision – CAP-IT-04

*Version 2.0 · 7 november 2026*

## Samlat omdöme

**Godkänd som reviderat faktaboksunderlag med förbehåll för extern sak- och juridisk granskning.** Kapitlet har en relevant G2-diagnos, håller isär funktion och gemensam plattform och beskriver 17 källmodellkopplade tjänster utan att göra dem till en inköpslista. Revisionen behövdes framför allt för att undvika kategoriska påståenden om dataradering, rollback och teknikval.

## Kritiska iakttagelser och justeringar

1. **Generationslogik/prioritet:** Analytisk datahantering och objektlagring blev automatiskt ”kritiska” i G3–G4. Det är inte generellt motiverat. Ersatt med konsekvens- och användningsfallsstyrd bedömning. Övriga kritikalitetsbedömningar har fått förklarande villkor; genomgång för varje verksamhet behövs.
2. **Schemaförändring och återgång:** Att rulla tillbaka applikationskod betyder inte att tidigare dataversion eller externa händelser återställs. Kapitel och verifieringsprov skiljer kompatibel migration, framåträttning och verklig dataåterställning.
3. **Radering, backup och bevarande:** Tidigare formuleringar kunde uppfattas som krav på omedelbar radering ur alla medier. Korrigerat för primärdata, index, kopior, backup och arkiv; undantag och juridisk prövning synliggörs.
4. **Aktualitet kontra konsistens kontra återställningsmål:** Eget avsnitt om tidsfönster, RPO/RTO och kontroller i faktiskt informationsflöde, inklusive illustrativa, inte föreskrivna siffror.
5. **Teknikneutral verifiering:** Kubernetes-PVC och PDF/A var för specifika som allmänna krav; ersatt med teknikneutrala prov respektive villkorad PDF/A.
6. **Offline-konflikter:** `last-write-wins` är inte generellt fel; avgörande är en medveten och testad konfliktpolicy som passar data och verksamhetskonsekvens.
7. **AI- och datarättigheter:** Teknisk nekning kan bara garanteras vid kontrollerade åtkomstvägar; källspårning garanterar inte korrekt genererat svar. Återkallelse påverkas av tokenlivslängd och redan exporterade kopior.
8. **Felsökning före produktbyte:** Tillagd metod som skiljer mellan informationsägarskap, arkitektur/integration, implementation/förvaltning och faktisk produktbegränsning samt fyra åtgärdsval.
9. **Tjänstespecifika kontroller:** Skärpt bland annat pipeline, semantiskt lager, datakatalog, kvalitetskontroll, masterdata, cache, grafdatabas, relationsdatabas, federerad åtkomst, lagring, offline-synk och dokumentgenerering.

## Kvarstående risker

- De 17 tjänsternas identiteter och uppdrag är bibehållna från tidigare källmodell. Alla serviceprofiler bygger på analytiska tolkningar; kontrollera originalbaseline om taxonomin uppdateras.
- Laglig grund, bevarande, gallring, rätt till radering, skydd av säkerhetskopior och sekretess måste sakkunniggranskas för aktuell offentlig eller privat verksamhet.
- RPO/RTO och aktualitetsvärden måste fastställas för riktiga verksamhetsflöden, inklusive beroenden till CAP-IT-09.
- Kapitel 04, 06 och 07 bör språkgranskas tillsammans för termerna auktoritativ källa, datakontrakt, attributbehörighet och syftesbegränsning.
- Kontrollera referenser före slutredigering; NIST SP 800-209 Rev. 1 (juli 2026) är ett utkast, inte fastställd standard.

## Verifiering

YAML har parsats och granskningsskriptet kontrollerar 17 unika PLS-ID:n, fyra generationsprofiler per tjänst samt revisionsändringar. ZIP-arkivet kontrolleras separat.
