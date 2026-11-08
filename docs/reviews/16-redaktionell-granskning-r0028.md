# Redaktionell granskning – kapitel 16, r0028

## Källunderlag
- `docs/kallmaterial/kapitel/CAP-IT-09-kapitel.md`, faktaboksunderlag v3.0.
- `docs/kallmaterial/granskningar/CAP-IT-09-granskning.md`.
- Modell `docs/kallmaterial/modeller/CAP-IT-09-modell.yaml`.
- Korsläst manuskapitel 7, 8, 9, 13 och 14 i r0027.

## Redaktionella beslut
1. **Tjänsteerbjudande först:** Observability, larm/tjänstekvalitet, backup/återställning, större återhämtning och särskild teknisk revisionsspårbarhet. Avstår från att föra över de tekniska tjänste-ID:na till läsarmanuset.
2. **G2 utan överdrift:** Kvarvarande brister i distribuerade system (grön komponentövervakning men trasigt användarflöde) hålls isär från behovet att göra stödet självbetjänat i G3.
3. **G3 ansvar:** Gemensamma plattformar levererar stöd och automation; produktteamet har ansvar för instrumentering, larmbehov och applikationsåtgärder; tvärgående incidenter kräver fortfarande samordning.
4. **G4 riskanpassning:** En verksamhetsskapad lösning får begripliga standardkontroller och stoppmöjlighet; kritiska agentåtgärder behöver insyn och särskild hantering. Upprepar inte hela publiceringslivscykeln från kapitel 13.
5. **Korrekt återhämtning:** Skillnaden mellan RPO/RTO, testad återläsning, återbyggbara data och irreversibla externa åtgärder hålls tydlig.
6. **Förmågegränser:** Körmiljön producerar signaler; driftbarhet möjliggör analys/larm/återhämtning; AI:s utvärdering och integrationens åtgärdskontrakt förblir där.

## Kvarstående granskning
- Säkerställ rätt användning av SLI/SLO, RPO/RTO och återställningsbegrepp i slutlig teknisk sakgranskning.
- Bestäm källhänvisningar för normer och standarder i framtida källregister. Ingen extern faktagranskning utförd i detta steg.
- Formellt kapitelgodkännande återstår.
