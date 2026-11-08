# Kritisk samgranskning – Process, workflow och ärendehantering samt Integration och informationsutbyte (r0038)

## Underlag och metod

Fullständig korsläsning av kapitel 05 och 09 i r0037. Kapitel 10 (*Identitet och tillit*) och 13 (*Utveckling och teknisk leverans*) användes som kontroll för behörighet, agentmandat, verksamhetsskapade lösningar och skapande-/publiceringsväg. Granskningen bedömer ansvarsgränser, generation 3–4, begriplighet och repetitioner. Tidigare granskade interna källunderlag och modeller har behållits som dokumentationsbas; ingen ny oberoende produkt- eller juridisk verifiering har gjorts.

## Fynd och genomförda justeringar

1. **Teknisk kvittens kunde misstas för slutfört processsteg (kapitel 05).** Tydliggjort att lyckad meddelandeleverans eller ett kvitterat anrop inte i sig garanterar genomförd verksamhetsåtgärd. Ett uteblivet eller sent svar måste kunna utredas i processkontexten.
2. **Dubbla leveranser och processtillstånd riskerade att blandas samman (kapitel 05 och 09).** Integrationen stödjer transport, återförsök, felutredning och idempotent behandling. Mottagande system skyddar mot dubbla verksamhetseffekter. Processförmågan hanterar vilken processinstans och vilket steg som påverkas, inklusive tidsgränser och sena svar.
3. **Oklart om processplattformen äger verksamhetsprocessen (kapitel 09).** Formuleringen att processförmågan 'ansvarar för verksamhetens processflöde och beslutspunkter' kunde tolkas som att en central plattform äger verksamhetsbeslut. Ändrat till att plattformen *erbjuder tekniskt stöd*, medan verksamheten äger processens utformning och beslut.
4. **Generation 4 behövde tydligare skillnad mellan processbyggsten och verksamhetsfunktion (kapitel 05).** Processbyggstenen 'begär komplettering' kan använda en godkänd integrationsfunktion, men är inte ensam ansvarig för dess behörighets- och verksamhetsregler.
5. **Kapitel 10 och 13 – inga textändringar.** Kapitel 10 skiljer redan tekniskt identitets-/mandatstöd från verksamhetssystemets behörighetskontroll. Kapitel 13 ansvarar redan för skapande-, test- och publiceringsvägen, inte processmotorn eller integrationsanslutningarna. Ytterligare formuleringar skulle främst skapa upprepning.

## Samlad ansvarsfördelning

| Förmåga/aktör | Ansvar | Gräns |
| --- | --- | --- |
| Process, workflow och ärendehantering | Processinstanser, väntelägen, mänskliga uppgifter, eskalering, teknisk ärendekontext | Inte ägare till verksamhetsbeslut eller systemens auktoritativa ärendedata |
| Integration och informationsutbyte | API:er, meddelanden, händelser, filutbyte, kontrakt och anropsspårbarhet | Inte ansvarig för ett långlivat processflödes verksamhetsstatus |
| Identitet och tillit | Identitets- och mandatmekanismer | Inte beslutsfattare för verksamhetsåtgärder |
| Utveckling och teknisk leverans | Skapande-, test-, leverans- och publiceringsvägar | Inte ägare till processregler eller integrationernas tekniska tjänster |
| Verksamhetsägare och verksamhetssystem | Processregler, beslut, auktoritativa uppgifter och kontroll av tillåtna åtgärder | Inte driftansvariga för alla gemensamma plattformstjänster |

## Generationskontroll

I **generation 3** kan professionella team använda workflow- och integrationstjänster genom automatiserad självbetjäning genom hela livscykeln. Det innebär inte att varje flöde behöver en gemensam processmotor eller att datakonsistens kan garanteras av en kö.

I **generation 4** kan en godkänd skapandemiljö kombinera processbyggstenar och förvaltade verksamhetsfunktioner. Processägaren bestämmer automatiseringsgränser och ansvar; det mottagande systemet prövar åtgärder. En AI-genererad instruktion räcker inte som behörighetskontroll.

## Återstående frågor

- Framtida kapitel 06 *Regler och beslut* ska ytterligare förtydliga regel- och beslutsstödets gräns mot workflow och verksamhetssystem.
- Oberoende teknisk granskning behövs för valda produkters hantering av idempotens, processversionsmigrering och återförsök.
- Verksamhetsspecifika krav på formella beslut, ärendehistorik och rättelser behöver juridisk och domänmässig sakgranskning.
- Formellt kapitelgodkännande har inte gjorts.
