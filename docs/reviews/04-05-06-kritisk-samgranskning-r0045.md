# Kritisk samgranskning – kapitel 04, 05 och 06, r0045

## Syfte och underlag

Sammanhängande läsning av hela `chapters/04-interaktion-kanaler.md`, `chapters/05-process-workflow.md` och `chapters/06-regler-beslut.md` från projektversion r0044, med `chapters/13-utveckling-leverans.md` som kontroll och projektets redaktionella canon som norm. Granskningen gäller tjänsteansvar, självbetjäning i generation 3 och 4, användarupplevelse, säker testning, publiceringsmandat och upprepningar. Inga nya externa sakuppgifter eller rättsliga tolkningar har lagts till.

## Kritiska fynd och genomförda justeringar

1. **Formulärens funktionella ägare var otydlig.** Kapitel 04 erbjöd formulärmotorn, samtidigt som kapitel 05 listade formulär som en del av processtjänsten. **Ändrat 04 och 05:** Kanal-/interaktionsförmågan erbjuder formulär- och klientfunktionerna; processförmågan sammansätter och använder formuläret vid rätt steg och ärende. Det kan fortfarande vara en enda leverantörsprodukt.
2. **Notifieringar riskerade dubbel tjänsteägare.** Båda kapitlen kunde uppfattas som ansvariga för att leverera meddelanden. **Ändrat 04 och 05:** Processen bestämmer när en notifiering ska utlösas, kanaltjänsten sköter leveransen. Teknisk implementering kan återanvända integrationstjänster; kapitelgränsen handlar om funktion, inte produkt.
3. **Kvittenser och verksamhetsstatus.** Gränssnittskapitlet behövde tydligare skilja teknisk inlämning från faktisk ärendestatus. **Ändrat 04:** återkopplingen bygger på auktoritativ status, inte bara på klientens eller API:ets kvittens.
4. **Sammanhängande och ofarlig provning i G4.** Kapitel 04–06 beskrev testning men hade olika precision för produktionseffekter. **Ändrat 04 och 06, kontrollerat 05:** skyddade provdata och testanslutningar, simulering utan att ändra verkliga ärenden, notifiera verkliga mottagare eller producera beslut.
5. **Publiceringsrätt kontra beslutsmandat.** Kapitel 05/06 var tydliga men kapitel 04 kunde misstolkas. **Ändrat 04:** behörighet att publicera en vy innebär inte rätt att ändra verksamhetsregler eller fatta beslut.
6. **G3/G4-ansvar och generell leveransväg.** Kontrollerat att G3 = utvecklingsteamens fulla normala livscykel på gemensamma, förvaltade byggblock och att G4 även låter verksamheten skapa, testa, publicera och vidareutveckla många lösningar själv. Kapitel 13 beskriver den generella skapande-/publiceringsvägen; **ingen textändring i 13** för att undvika dubbelbeskrivning.

## Samlat exempel och ansvarsgräns

Ett kompletteringsflöde kan använda ett formulär från interaktionsförmågan, låta processförmågan avgöra när kompletteringen behövs och vem som väntar, och använda ett regelresultat för att bedöma om underlaget är komplett. Vid en statusändring ska gränssnittet visa det som verksamhetssystemet faktiskt bekräftat. Behörig verksamhet ansvarar för regler, beslut och processinnehåll. Den generella leveransvägen beskrivs i kapitel 13.

## Vad som återstår

- Oberoende teknisk granskning och vid behov tillgänglighets- och juridisk bedömning.
- Verifiering i en faktisk plattform av isolerade teamytor, säkra testanslutningar, versionsövergångar och skyddade publiceringsflöden.
- Formellt kapitelgodkännande av 04, 05 och 06.

Inga källmodeller, originalunderlag eller andra kapitel har reviderats.
