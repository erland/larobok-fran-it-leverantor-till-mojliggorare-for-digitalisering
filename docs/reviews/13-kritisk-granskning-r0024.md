# Kritisk redaktionell granskning – kapitel 13, revision r0024

## Underlag och avgränsning

- Manuskapitel 13 från projekt r0023 och dess kritiskt granskade källkapitel för *Utveckling och teknisk leverans*.
- Korsläsning mot manuskapitel 2, 7, 8 och 9 och projektets redaktionella canon.
- Granskningen är en intern redaktionell och arkitektonisk bedömning; inte oberoende faktagranskning eller verifiering av specifika produkter.

## Iakttagelser och genomförda ändringar

1. **Oklart driftansvar.** Den tidigare formuleringen om en sammanhängande livscykel kunde få utvecklingsplattformen att låta som ägare av applikationens körmiljö och driftsövervakning. Tydligare gräns mot *Applikationsexekvering och körmiljö* och *Driftbarhet och motståndskraft*; kravet på en sammanhängande användarupplevelse behålls.
2. **Generation 3 behövde tydligare effekt.** Självbetjäning definieras nu genom att normala ändringar inte behöver lämnas över, inte genom enbart tillgång till en pipeline eller kort väntetid.
3. **Generation 4 upprepade livscykeln.** Femstegslistan och det efterföljande exemplet har ersatts av en kort beskrivning av tjänsteerbjudandet, tre riskbaserade användningsnivåer och övergången till professionell förvaltning.
4. **För svag gräns mellan AI-stödd utveckling och AI som funktion.** AI-genererad kod kräver kodkontroller; en publicerad AI-lösning kräver också beteendeutvärdering och behörighetskontroller från andra förmågor.
5. **Risk för för omfattande löften om överlämning.** Formuleringen säger nu att artefakter, beroenden och ansvar bör kunna tas om hand, men att teknisk omarbetning ändå kan behövas.
6. **Tjänster före verktyg.** Fler namngivna produktkategorier skulle inte öka läsarvärdet; avsnittet skiljer mellan leveransväg, självbetjäning och verksamhetsnära skapandemiljö.
7. **Läsbarhet.** Ingen retorisk fetstil eller CAP-IT-koder i manus; kursiva hänvisningar till andra förmågor.

## Bedömning mot kapitlen 7–9

- Kapitel 7: utvecklingsplattformen återanvänder datatjänster men bestämmer inte lagringsteknik på egen hand.
- Kapitel 8: AI-modeller och beteendeutvärdering hör dit; skapande- och releaseflödet hör hit.
- Kapitel 9: godkända verksamhetsfunktioner och deras åtgärdsmandat hör dit i samverkan med identitet och säkerhet.
- Ingen ny plattform föreskrivs. Flera verktyg kan ingå i samma tjänsteerbjudande.

## Kvarstående sak- och kvalitetskontroller

- Verifiera inför publicering eventuella specifika påståenden om AI-byggverktyg, programvaruförsörjningskedja och leveranssäkerhet mot aktuella primärkällor.
- Korsgranska senare mot manuskapitlen om körmiljö, driftbarhet, identitet och cybersäkerhet när de skrivs.
- Formellt kapitelgodkännande och oberoende sakkunniggranskning återstår.
