# Kritisk granskning – CAP-IT-11, version 2

**Granskningsobjekt:** Kapitel och YAML från första faktaboksunderlaget för CAP-IT-11. **Resultat:** Reviderad version 2, inte extern certifiering eller produktverifiering.

## Samlad bedömning

Kapitlets generationslogik fungerar: G1 är kort historik, G2 skiljer avhjälpande av kvarvarande grundbrister från nyttan av en G3-plattform, och G4 är framåtblickande. Källmodellens fyra PLS-ID och tre PLT-ID är fortsatt korrekta enligt det befintliga källunderlaget. Största kvarvarande svagheterna var breda antaganden om endpointskydd, avsaknad av en explicit testmodell för delade klienter samt begränsade resonemang om specialenheter och offlinearbete.

## Granskningsfynd och utförda ändringar

| Nr | Fynd i version 1 | Bedömning och ändring i version 2 |
|---|---|---|
| 1 | Endpointskydd klassades som kritiskt och som gemensam plattform även när enhetsklass och hotbild varierar. | **Väsentligt.** Korrigerat fyra generationsprofiler för PLS-077: hotmodell och faktisk kontroll före universellt agent-/EDR-krav. |
| 2 | BYOD beskrevs men inte konkret rätt att radera privata respektive arbetsrelaterade data. | **Väsentligt.** Tydligare skillnad mellan ägande, hanteringsläge, arbetsprofil, raderingskommando och bekräftad effekt; test tillagt för PLS-045. |
| 3 | Delade enheter saknade kontroll av faktisk användarseparation. | **Väsentligt.** Nytt scenario för användarbyte, cache, utskrifter, filer, token och webbsessioner. |
| 4 | Offlineklienter behandlades främst som åtkomst- och raderingsrisk. | **Väsentligt.** Nytt fall om utgångna mandat, osynkroniserad verksamhetsdata och kontrollerad återanslutning. |
| 5 | Central policy kunde stoppa alla användare, men reservadministration provades inte fullt ut. | **Väsentligt.** Tydligare G3-kontroll: prov av administrativ reservväg och stoppvillkor före bred utrullning. |
| 6 | Klientuppdatering mättes mer som teknisk installation än genomfört arbete. | **Viktigt.** Kompletterat med klientuppgiftsprov, hjälpmedel och kringutrustning; motexempel när appbutik/OS begränsar nedgradering. |
| 7 | Ansvar mellan klient, SOC, IAM och verksamhet beskrevs men saknade gemensamt incidentprov. | **Viktigt.** Ny incidentansvarsmatris samt prov där isolering kan hota osynkroniserade data. |
| 8 | DaaS isoleringsnivå kunde överskattas. | **Viktigt.** Skärpt verifiering av kvarvarande exportvägar, andra sessioner, verklig användbarhet och kostnader. |
| 9 | Generationskritikalitet kunde feltolkas som obligatoriskt produktkrav. | **Viktigt.** Förtydligat situationsberoende plattformsbehov för UEM och EDR utan att urvattna skyddskraven. |
| 10 | Mätmodellen saknade användarupplevelse för särskilda klientklasser. | **Viktigt.** Ny uppföljning av faktisk förmåga att slutföra arbetsuppgifter med hjälpmedel, offline- och specialutrustning. |

## Källkritik och avgränsning

**Källmodellen** stöder PLS-045, PLS-046, PLS-077 och PLS-047 samt deras existerande plattformsanknytning. **NIST SP 800-124 Rev. 2 (2023)** omfattar säker hantering av både organisationsägda och privata mobila enheter genom livscykeln och beskriver fjärrradering som en begränsad kontroll, inte en garanti. **NIST SP 800-46 Rev. 2 (2016)** ger riskbaserat stöd om fjärråtkomst och BYOD. **NIST SP 800-53 Rev. 5**, inklusive senare underhållsuppdateringar, är en kontrollkatalog, inte en certifiering av en särskild klientteknik. Begrepp som generationsprofiler, mätetal, incidentansvar och teknikval är våra redaktionella arkitekturbedömningar, inte påståenden om källmaterialets ordalydelse eller en specifik organisations verkliga tillstånd.

## Kvarstående frågor före slutlig publicering

1. Extern sakgranskning av klienthantering och informationssäkerhet för organisationens valda OS, BYOD-policy och skyddskrav.
2. Rättslig/integritetsmässig granskning av övervakning, selektiv radering och insamlad endpointtelemetri i aktuella jurisdiktioner; den här texten är inte juridisk rådgivning.
3. Konkreta målvärden för tillgänglighet, patchtakt, förlorade enheter och uppgraderingsframgång måste sättas lokalt utifrån risk.
4. Samordnad bokredigering mot CAP-IT-01, CAP-IT-07, CAP-IT-09, CAP-IT-10 och CAP-IT-12 för att minska överlappning och säkerställa samma terminologi.

**Slutsats:** Version 2 är en bättre, mer teknikneutral och verifierbar faktabokstext. Den kan gå vidare till samlad redaktionell granskning, men är inte slutligt publiceringsgranskad.
