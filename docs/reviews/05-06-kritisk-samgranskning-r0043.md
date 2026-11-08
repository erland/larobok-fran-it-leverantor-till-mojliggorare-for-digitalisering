# Kritisk samgranskning – kapitel 05 och 06, r0043

## Underlag och metod

Hela manuskapitel 05 (*Process, workflow och ärendehantering*) och 06 (*Regler och beslut*) i projektversion r0042 har jämförts med kapitel 09 (*Integration och informationsutbyte*) och 10 (*Identitet och tillit*) som kontrollkapitel. Bedömningen gäller ansvar, teknisk rimlighet, generationslogik, autonomi och riskstyrd kontroll. Inga nya externa fakta eller rättsliga slutsatser har tillförts.

## Kritiska iakttagelser

1. **Processlogik kontra regelutvärdering.** Kapitel 05 angav att giltiga övergångar är verksamhetsregler, men pekade inte ut när regelförmågan kan ge ett återanvändbart resultat. Risk: läsaren kan uppfatta att workflowplattformen även äger regelutvärderingen. **Åtgärd:** Processförmågan använder utvärderat resultat för rätt instans och steg; regelmodeller kan erbjudas av kapitel 06. Alla enklare övergångar måste inte externaliseras till en regelmotor.
2. **Processversion kontra regelversion.** Ett pågående ärende kan vara låst till en viss processdefinition samtidigt som regelns giltighetsvillkor ger en annan regelversion. Risk: versionsmodellerna blandas samman. **Åtgärd:** Tydliggjort att dessa två versioner och deras giltighet måste bedömas separat.
3. **Publiceringsrätt kontra verksamhetsmandat.** I generation 3 kan utvecklingsteam få teknisk rätt att publicera modeller, men godkännandet av regelns innebörd ligger hos behörig verksamhet. I generation 4 behöver självständighet uttryckligen gälla en behörig verksamhetsmedarbetare med identifierat ansvar. **Åtgärd:** Preciserat kapitel 05 och 06 utan att göra ett centralt specialistråd till standardkrav.
4. **Integration och identitet.** Kapitel 09 erbjuder transport, kontrakt och teknisk spårbarhet; kapitel 10 tekniska identitets- och mandatmekanismer. Den mottagande tjänsten behöver fortsatt verkställa relevanta rättigheter. **Åtgärd:** Ingen textändring i 09 eller 10 eftersom gränserna redan är konsekventa.

## Samlad bedömning av generationerna

- **Generation 2:** Centrala specialistteam kan behöva implementera flöden respektive regler åt andra. Verksamheten äger fortfarande innehållet.
- **Generation 3:** Professionella utvecklingsteam tar självständigt ansvar för konfiguration, test och teknisk publicering på förvaltade plattformstjänster, men får inte automatiskt mandat att fastställa verksamhetsregler eller beslut.
- **Generation 4:** Behöriga verksamhetsmedarbetare kan självständigt utforma, prova, publicera och förvalta lämpliga flöden och regler med riskanpassade kontroller. Mer konsekvensrika beslut kan kräva separat godkännande.

## Återstående granskning

Formellt kapitelgodkännande, oberoende teknisk sakgranskning och specifik juridisk bedömning av automatiserat beslutsfattande återstår. Källmaterial och YAML-modeller ändras inte. Inga generella garantier om exakt historisk reproduktion av beslut görs.
