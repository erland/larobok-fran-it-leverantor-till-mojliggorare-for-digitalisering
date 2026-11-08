# Redaktionell pilotgranskning – kapitel 9, revision r0021

## Underlag och metod
- Primärkälla: `docs/kallmaterial/kapitel/CAP-IT-06-kapitel.md`, motsvarande kritisk granskning och YAML-modell.
- Korsläst mot bokkapitel 07 och 08 samt redaktionell canon.
- Inga nya obligatoriska produkter eller tekniska generationstrappor föreslås. Aktuella leverantörspåståenden undviks.

## Redaktionsbeslut
1. Fokus på **erbjudna gemensamma tjänster**: API-publicering, meddelande- och händelsetjänster, fil/externa anslutningar, kontrakt, felhantering och observerbarhet.
2. Källmaterialets centrala risker bevaras koncentrerat: idempotens, dubbelskrivning/transaktionell utkorg, begränsningar i exakt-en-gång-semantik, kvittenser, återspelning och verksamhetseffekter.
3. ETL/ELT avgränsas från integration: analytisk datainläsning, bearbetning, historisering och datapublicering beskrivs i kapitel 07. API/meddelande/fil kan användas som transport även i sådana flöden.
4. Integration hålls skild från processorkestrering och verksamhetsregler; tekniskt kontrakt är inte samma sak som juridiskt/verksamhetsmässigt kontrakt.
5. G3 konkretiseras som det centrala integrationsteamets förflyttning från obligatorisk utförare till produktansvarig, inklusive full livscykel och felsökning.
6. G4 konkretiseras som godkända, begripliga verksamhetsfunktioner och säkra anslutningar; betrodd mandatkontroll utanför AI-modellen.
7. Förmågehänvisningar skrivs kursivt utan CAP-IT-nummer. Ingen retorisk fetstil i läsarmanuset.

## Begränsningar och fortsatt kontroll
- Källa och text stödjer principerna men ingen produkt- eller implementationsspecifik garanti om exakt-en-gång-leverans, återspelning eller agentmandat.
- Extern faktagranskning av tekniska garantier och eventuella rättsliga utbytesvillkor behövs före publicering.
- Senare kapitel om Process, workflow och ärendehantering och Identitet och tillit ska korsgranskas mot verktygs- och kontraktsansvar.
- Arbetsutkast; inget automatiskt eller manuellt kapitelgodkännande registreras i detta steg.
