# Kritisk granskning – CAP-IT-01, version 2.0

*7 november 2026 · Separat revisionsomgång av den befintliga kapiteltexten och YAML-modellen*

## Samlad bedömning

Kapitlet har en övertygande G2-utgångspunkt och håller korrekt isär användarresan från bakomliggande tjänster. Det gör inte webbteknik eller centralisering obligatoriska, och de sju PLS/PLT-kopplingarna bevaras. Den första versionen var dock starkare på principer än på bevisbar användarnytta, skillnaden mellan klienttyper, konsumtion av plattformsuppgraderingar och praktiskt offlineskydd. Version 2 korrigerar dessa fyra luckor och behåller kapitelstrukturen.

## Identifierade brister och åtgärder

| Nr | Bedömning av version 1 | Ändring i version 2 | Konsekvens |
|---|---|---|---|
| 1 | Webb- och native-tillgänglighet behandlades nästan som ett testfall. | Eget avsnitt om webb, native mobil och specialklienter; WCAG2ICT som informativ källa. | Undviker falsk tillgänglighetsförsäkran från enbart webbtester. |
| 2 | För stort fokus på adoption och införande av komponenter. | Mått för slutförandegrad, felåterhämtning, tid och begriplighet per målgrupp. | Faktisk användarnytta blir mätbar. |
| 3 | Självbetjäning omfattade uppgradering men inte uttryckligt konsumentprov. | Migrations- och kompatibilitetsprov i två konsumerande produkter, inklusive gamla versioner. | Plattformen bedöms för hela livscykeln. |
| 4 | Offlinesynkprov omfattade konflikt och avbrott men inte tillräckligt tydligt utebliven bakgrundssynk. | Nya scenarier med avstängd app, kvarvarande kö och manuell återhämtning. | Mindre risk för tyst datatapp. |
| 5 | Lokal data på delade, förlorade eller utbytta fältenheter behandlades mycket kortfattat. | Separat kontroll av utloggning, token, lokal lagring, återautentisering och möjlig radering. | Bättre förutsättningar att begränsa informationsläckage. |
| 6 | Flera G3-tjänster hade begränsade testspecifikationer för migrationskostnad. | Alla tjänster får explicit migrationskontroll och individuellt G3-verifieringsprov. | Mer jämförbara, testbara tjänstebedömningar. |
| 7 | WCAG 2.2 nämndes utan avgränsning för icke-webbaserade appar. | Hänvisning till W3C WCAG2ICT, uttryckligen icke-normativ. | Källan blir rätt använd. |
| 8 | Kapitlet behövde tydligare motstånd mot teknikdriven lösning. | Beslutsordningen och villkorade bedömningar behålls. | Byte av teknik kräver observerat problem. |

## Spårbarhet och omfattning

**Källgrundat:** tjänsteidentiteter, tjänstebenämningar och PLT-kopplingar härleds från baseline v1.1. De sju tjänsterna är PLS-001, PLS-002, PLS-003, PLS-004, PLS-074, PLS-089 och PLS-075. Ingen ytterligare direkt stödjande tjänst läggs till.

**Redaktionell analys:** generationsbedömningar, indikatorer, prioriteringar och föreslagna verifieringsprov är tolkningar för en generell organisation, inte kartläggning av en faktisk organisations nuläge.

**Extern komplettering:** W3C:s WCAG2ICT ger vägledning för icke-webbaserad programvara, men avgör inte i sig juridisk tillämplighet. MDN:s offlinevägledning ger teknisk kontext; stöd och timing för bakgrundssynk måste testas per målplattform.

## Kvarstående begränsningar inför publicering

1. Rättslig kravuppfyllelse (tillgänglighet, personuppgiftshantering, notifiering/delgivning) behöver granskas per faktisk verksamhet och jurisdiktion.
2. Krav på användartestning och mätning behöver kalibreras mot verkliga målgrupper och konsekvenser; detta är en generell faktabok, inte en fullständig testplan.
3. Teknikspecifika möjligheter till fjärradering, lokalt nyckelskydd och offlinearbete varierar med klient, enhet och driftmodell.
4. Extern sakgranskning och terminologisk harmonisering med övriga 12 förmågor kvarstår.

## Verifiering

YAML-filen är parsbar, innehåller exakt sju bevarade PLS/PLT-kopplingar, 28 G1–G4-profiler och tjänstespecifika verifieringsprov. Kapiteltexten och modellen har kontrollerats för motsägelser i ovanstående områden. ZIP-filen CRC-kontrolleras vid paketering.
