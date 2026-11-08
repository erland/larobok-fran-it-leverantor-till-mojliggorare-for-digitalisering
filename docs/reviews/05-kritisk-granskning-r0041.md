# Kritisk granskning – kapitel 05, r0041

## Omfattning och bedömning

Hela kapitel 05 har prövats mot föregående revision och mot kapitel 09 (integration), 10 (identitet) och 13 (utveckling och leverans). Huvudbudskapet är korrekt för bokens illustrativa generationsmodell: ett gemensamt specialistteam kan gå från utförare av alla processtillägg till leverantör av en självbetjänad plattform (G3), varefter verksamhetsmedarbetare kan skapa många av sina egna flöden (G4). Beskrivningen är en målbild, inte något som automatiskt följer av att en plattform är gemensam.

## Kritiska fynd och genomförda ändringar

1. **Självbetjäning utan konkret teknisk förutsättning (viktig):** Tydliggjort behovet av avgränsade konfigurationsytor, behörigheter, testdata och kontrollerad publicering. Om den gemensamma plattformen inte kan isolera förändringar kan självbetjäning vara olämplig eller kräva anpassning.
2. **Risk för verkliga sidoeffekter vid G4-test (viktig):** Lagt till att simulering och test ska använda testuppgifter eller kontrollerade anslutningar så att riktiga ärenden och externa åtgärder inte påverkas av misstag.
3. **Publicering sammanblandad med beslutsmandat (viktig):** Förtydligat att publicering inte ger rätt att fatta eller verkställa beslut och att ansvariga verksamhetssystem prövar mandat och beslutens regler.
4. **Rätt nivå för självständig verksamhet (måttlig):** Kopplat självbetjäning för enklare flöden till tydliga skyddsräcken och en identifierad ägare.

## Kontroll mot andra kapitel

- **Kapitel 09:** Integration ansvarar för transport och anropskontrakt; processförmågan för instanser, väntelägen och övergångar. Inga ändringar behövs.
- **Kapitel 10:** Identiteter och mandatmekanismer är skilda från verksamhetens beslut om tillåtna åtgärder. Inga ändringar behövs.
- **Kapitel 13:** Utvecklings- och leveransförmågan erbjuder gemensamma publiceringsvägar; processplattformen tillhandahåller flödesspecifika skapande- och testfunktioner. Dessa kan vara integrerade i en och samma produkt. Inga ändringar behövs.

## Avgränsningar och kvarstående frågor

- Kapitlet ska inte ange en viss workflowmotor, SaaS-tjänst eller organisatorisk uppdelning som obligatorisk.
- Tekniskt ansvar för gemensam plattform, produktteams ansvar för sina processlösningar och verksamhetens processägarskap ska hållas isär.
- Kommande kapitel om *Regler och beslut* måste pröva gränsen mellan definierad processövergång och egentlig beslutsregel.
- Oberoende teknisk sakgranskning och formellt godkännande kvarstår. Ingen extern faktakontroll har gjorts i denna revision.
