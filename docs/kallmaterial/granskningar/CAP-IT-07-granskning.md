# Kritisk granskningsrapport – CAP-IT-07, version 2

*7 november 2026 · intern redaktionell och arkitekturell granskning*

## Samlad bedömning

Kapitelstrukturen är lämplig som fristående faktaboksunderlag. Generation 2 fungerar som huvudperspektiv och gränsen mellan gemensam identitetsteknik och verksamhetsstyrd åtkomst är riktig i huvudsak. Version 1 behövde dock större precision i identitetsbegrepp, återkallelse, agentdelegering och hur indikatorer omsätts i prov. Ändringarna är genomförda i version 2.

## Identifierade brister och ändringar

| Område | Risk i tidigare version | Åtgärd i version 2 |
|---|---|---|
| Begrepp | Identifiering, autentisering, auktorisation och delegation gick delvis ihop | Skärpta definitioner; delegation definieras separat |
| Tillämplighet | Formuleringen kunde tolkas som att all människoinriktad åtkomst måste autentiseras | Förtydligar möjlig anonym publik läsning |
| Tokenvalidering | Protokollexempel saknade explicit referens till OAuth-säkerhet | Tillagt RFC 9700 och separata prov för utfärdare/mottagare |
| Kontoavslut | Risk att central avstängning förväxlas med omedelbar spärr överallt | Skilda prov för nya inloggningar, sessioner, giltiga token och nedströms behörighet |
| G2→G3 | Säkerhetsbrister kunde felaktigt framstå som huvudargument för central plattform | Rättelse av grundbrist skiljs från återkommande, standardiserbart tjänstebehov |
| Agentidentitet | Formuleringarna kunde ge intryck att varje agent kräver separat kontotyp | Spårbar agentkörning och verkställbar delegation sätts före teknisk kontoform |
| G4-risk | Återkallelse kunde uppfattas som reversering av redan utförda handlingar | Begränsningen och beroenden till process- och säkerhetskontroller förklaras |
| Beslutsnytta | Indikatorer var ibland generella | Nytt diagnostiskt scenario och tjänstespecifika YAML-prov |

## Kvarvarande svagheter

1. Avsnittet om elektronisk signering behöver juridisk sakgranskning för avsedda jurisdiktioner och verksamhetsfall.
2. Lokal IAM-/PKI-kompetens behöver granska praktiska implementationsexempel och vilka protokoll som används i den aktuella miljön.
3. Det saknas organisationsspecifika baslinjemått för avvecklingstid, incidentfrekvens, antal manuella identitetsärenden och risknivåer. Dessa ska inte uppfinnas i en faktabok.
4. Generation 4 är ett framåtblickande resonemang; ingen allmänt fastlagd standard för agentidentiteter antas.
5. Begreppen *behörighet*, *rättighet*, *mandat*, *tillit*, *workload* och *credential* bör harmoniseras när alla kapitel sammanställs.

## Spårbarhet

De tio tjänstenamnen, PLT-/PLS-kopplingarna och grundavgränsningen följer den uppladdade konceptuella baseline v1.1. Generationsprofiler, indikatorer och rekommendationer är arkitekturbedömningar. Externa referenser i kapitlet är NIST SP 800-63-4, NIST SP 800-207, RFC 9700 och OWASP NHI Top 10 (2025). Dessa standarder definierar inte bokens generationsmodell.

## Intern verifiering

Kontrolleras maskinellt vid paketering: giltig YAML, tio unika tjänster, fyra profiler per tjänst, samtliga refererade PLS-id:n i kapiteltexten samt integritet i ZIP. Detta är inte en oberoende säkerhetsgranskning.
