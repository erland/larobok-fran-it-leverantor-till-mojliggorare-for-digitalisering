# Redaktionell granskning – Kapitel 05, r0037

## Underlag och metod
- `docs/kallmaterial/kapitel/CAP-IT-02-kapitel.md`, kritiskt reviderad version 2.0 (7 november 2026).
- `docs/kallmaterial/granskningar/CAP-IT-02-granskning.md`.
- `docs/kallmaterial/modeller/CAP-IT-02-modell.yaml`, orörd.
- Manuskapitel 09, 10, 13 och 16 för kontroll av gränsdragningar.

## Bedömning och redaktionella beslut

1. **Tjänsteerbjudandet är primärt.** Fyra direkta tjänstekategorier i källmodellen återges begripligt: workfloworkestrering, tekniskt ärendesammanhang, mänskliga uppgifter/arbetsköer och notifieringsleverans. Formulär, regelmotorer och teknisk systemmeddelandetransport förs inte in som egna direkta tjänster.
2. **Central motor är inte ett krav.** Små, välavgränsade flöden kan ofta hanteras i domänapplikationens egen logik. Plattformens gemensamma produktvärde måste motiveras av återkommande behov.
3. **Kritiska G2-risker bevarade.** Konkurrerande uppdateringar, dubbletter, fel/återförsök och kompensation uttrycks kortfattat och utan påstående att en generell motor löser verksamhetsreglerna.
4. **G3 omfattar hela livscykeln.** Självbetjäning avser etablering, uppföljning, ändring, felhantering och avveckling. Pågående processinstanser kan behöva fortsätta under äldre definition eller särskilt migreras; inget generellt migrationslöfte ges.
5. **G4 stödjer verksamhet utan att överlåta ansvar till AI.** Byggstenar, mänskligt godkännande och omprövning vid förändrad risk. En extern godkänd SaaS/low-code-lösning kan redan innehålla stöd för exekvering; det är inte ett krav på egen intern motor.
6. **Gränsdragning:** Integration erbjuder meddelandetransport och API-kontrakt, identitet identitets-/mandatmekanismer, verksamhetssystem beslut och auktoritativ status, utvecklingsförmågan skapande och publicering, driftbarhet tvärgående incident- och återhämtningsstöd. Processförmågan håller samman processinstansens steg, väntan och mänskliga uppgifter.
7. **Självständigt kapitel:** Generationsmodellen återberättas inte; ingen källkodsliknande förmågekod eller retorisk fetstil förekommer i läsarmanuset.

## Kvarstående kontroller
- Extern verksamhets- och teknisk sakgranskning för processrättsliga krav, särskilt delgivning, beslutsfattande och bevarande.
- Praktisk verifiering av processversionsmigrering behöver göras för vald produkt och konfiguration; källtexten anger specifikt att generella garantier inte kan ges.
- Fortsatt avstämning med kommande kapitel 06 *Regler och beslut* för att inte dubblera beslutstjänster eller beslutens mandat.
- Formellt redaktionellt godkännande återstår. Ingen ny extern faktakontroll genomfördes för denna komprimering av befintligt källmaterial.
