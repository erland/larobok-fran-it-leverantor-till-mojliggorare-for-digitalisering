# Kritisk granskning – CAP-IT-12: Cybersäkerhet och tekniskt skydd

*Version 2.0 · 7 november 2026*

## Samlad bedömning

Kapitelstrukturen fungerar: generation 2 är utgångspunkt, medan arvet från generation 1 används för igenkänning. De två förbättringsspåren – få dagens distribuerade säkerhetsarbete att fungera och därefter standardisera självbetjänade skydd – bör behållas. **Revidering krävdes däremot i bedömningen av kritikalitet, i tjänsternas verifieringsprov och i diagnosen av varför kontroller brister.**

## Identifierade brister och utförda åtgärder

| Iakttagelse | Risk i tidigare version | Ändring i version 2 |
|---|---|---|
| För kategoriska prioriteringar | DLP, HSM, externa anslutningar och särskilt WAF framstod som allmängiltiga behov | Tillämplighetsvillkor och situationsberoende plattformsprioritet har tydliggjorts i YAML |
| Funktion kontra plattform | Kritisk skyddsfunktion tolkades ibland som krav på central produkt | Separat bedömning av skyddets kritikalitet och gemensamt tjänstebehov, inklusive villkor |
| Orsak till svagt skydd | Indikator kunde tolkas som direkt produktfel | Ny diagnostik för produkt, konfiguration, integration, arkitektur, ansvar och kompetens |
| Verifiering mellan förmågor | Workloadskydd och WAF kunde tilldelas ansvar för secrets-/behörighetsbeslut | Prov skiljer respektive skyddstjänst från IAM, runtime och applikationens auktorisation |
| Återgång/återkallelse | 'Rollback' av policy och omedelbar spärr av all åtkomst kunde tolkas för absolut | Återgång begränsas till när tekniskt möjlig; befintliga sessioner beaktas |
| AI-skanning | Statisk analys riskerade framstå som fullständig validering av agentbeteende | Separat beteendetest krävs utöver kod- och beroendekontroller |
| Forskning/källor | Extern vägledning kunde vara svår att spåra | OWASP 2026 och officiell källa tydliggjord i text och YAML |

## Kvarvarande begränsningar

1. Prioriteringarna är generella expertbedömningar, inte en bedömning av en verklig organisations riskprofil.
2. Gränsdragningar mot CAP-IT-07, 08, 09, 10 och 13 behöver harmoniseras i slutredigeringen.
3. Lokala lag- och tillsynskrav, exempelvis för samhällsviktig verksamhet, ingår inte i de generella tjänsteprioriteringarna.
4. Verifieringsproven är exempel. Organisationen behöver godkänna testomfattning och använda ofarliga testdata.
5. Kapiteltexten är internt sak- och språkgranskad men inte externt oberoende faktagranskad.

## Rekommendation

Använd version 2 som redaktionellt underlag. Behåll generationsstrukturen, men dra lärdom av att **säkerhetskritikalitet, produktval, centralisering och tjänstens egna kontrollansvar måste behandlas som olika frågor** i kommande kapitel.
