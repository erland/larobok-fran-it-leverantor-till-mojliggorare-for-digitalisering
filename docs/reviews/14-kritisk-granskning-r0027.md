# Kritisk granskning – kapitel 14, r0027

## Underlag och metod
Läst hela kapitel 14 i r0026 och jämfört med läsarmanus för kapitel 7, 8, 9 och 13, samt gällande innehålls-canon. Granskningen gäller redaktionell skärpa och förmågegränser; tekniska rekommendationer är inte oberoende sakgranskade.

## Iakttagelser och åtgärder

1. **Otydligt tjänsteerbjudande:** Körprofilerna var definierade men tjänstevillkor, kapacitetsgränser och driftinsyn var utspridda. Förtydligat vilka egenskaper varje profil ska deklarera, hur utvecklingsteam får insyn utan plattformsadministration och vad förvaltat versionsansvar innebär.
2. **Överlapp mot driftbarhet:** Hälsokontroller, loggar och felsökning kunde tolkas som att körmiljöförmågan ensam tillhandahåller hela incident- och observabilityerbjudandet. Tydliggjort ansvar: körmiljön ger signaler och tekniska exekveringskontroller; driftbarhetsförmågan tillhandahåller gemensam analys, incidentprocesser och återhämtning. Den exakta gränsen ska valideras när driftbarhetskapitlet skrivs.
3. **Repetitiv generation 3:** Kärnpoängen om självbetjäning återkom två gånger. Komprimerat till ansvarsfördelning och konkret normalfall.
4. **Generation 4 för allmän:** Ersatt upprepade risknivåer från kapitel 13 med ett särskilt exempel på kontinuerlig kontra händelsestyrd körning. Förtydligat att behovsbeskrivning inte ersätter skyddsbeslut och att en godkänd SaaS-assistent kan använda extern exekvering.
5. **För långt samspelsavsnitt:** Behållit nödvändiga gränser mot utveckling, data, nätverk, identitet, säkerhet och driftbarhet utan att återberätta andra förmågor.

## Kvarstående risker och kontroller
- De uppräknade körmiljötyperna är tjänstekategorier, inte en rekommenderad obligatorisk produktportfölj; val måste baseras på verkliga arbetslaster och krav.
- Förmågegränsen mot *Driftbarhet och motståndskraft* är provisorisk tills det kapitlet skrivs och samgranskas.
- Formellt kapitelgodkännande och oberoende teknisk faktagranskning återstår.
