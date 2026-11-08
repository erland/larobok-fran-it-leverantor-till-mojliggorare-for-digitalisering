# Faktakontroll – arbetsregister

| ID | Kapitel | Påstående / del | Status | Underlag / verifiering | Åtgärd |
|---|---|---|---|---|---|
| F001 | 01 | Distribuerade tjänster ökar antalet gränsytor och behov av samordning | Redaktionsanalys, ej externt verifierad | `docs/kallmaterial/generationer/overgang-g1-g2.md` | Granska formuleringar och källa inför publicering |
| F002 | 01–02 | Plattformsprodukt, självbetjäning, livscykel och tydliga tjänsteansvar | Källunderlagsstödd analys | `docs/kallmaterial/generationer/overgang-g2-g3.md` | Verifiera relevanta aktuella primärkällor vid faktagranskning |
| F003 | 02 | AI-assistenter, agenter och AI-stödd verksamhetsutveckling | Redaktionell framtidsanalys | `docs/kallmaterial/generationer/overgang-g3-g4.md` samt godkänd bokplan | Kontrollera påståenden om teknikens faktiska tillämpning och begränsningar |
| F004 | 02 | Riskanpassad indelning i personligt hjälpmedel, delad lösning och kritiskt stöd | Författarens analytiska modell | `docs/bokplan-godkand.md` | Presentera som föreslaget förhållningssätt, inte universell standard |
| F005 | 01–02 | Fiktivt fall om ärendehantering | Illustration | Redaktionellt konstruerat | Får inte beskrivas som verklig fallstudie |

**Öppna frågor:** Ingen oberoende extern sakgranskning genomförd. Särskilt G4-beskrivningar är framåtblickande och ska förbli nyanserade. Detaljerade källreferenser kan kompletteras under kapitelgranskningen. 

## Kapitel 08, pilot r0008
- Kapitelunderlag: CAP-IT-05 v2 och granskningsrapport; sakliga exempel är redaktionella illustrationer, inte verifierade organisationsfall.
- Extern fackgranskning av analys, söksäkerhet och AI kvarstår.
- Aktuella leverantörs- och rättspåståenden har medvetet undvikits i manuset.

## Kontrollpunkter efter r0009
- Stäm av beskrivningen av RAG, agentsäkerhet och utvärdering mot OWASP 2025 och NIST AI 600-1 före slutpublicering.
- Kontrollera förmågegränser mellan CAP-IT-05 och CAP-IT-04/06/07/10/12 vid tvärkapitelgranskning.

## Kapitel 09 – kontroll inför publicering
- Kontrollera integrationsprodukters faktiska garantier för leverans, ordning, retention och idempotens i den tänkta miljön (ej verifierat för någon produkt).
- Kontrollera tillits- och mandatkrav för verksamhetsfunktioner och agentanrop; rättsliga tillämpningar bedöms separat.
- Teknisk principkälla finns i granskade originalunderlaget, bl.a. AWS Transactional Outbox och Spring Kafka Exactly Once; produktval förordas inte.

## Kapitel 13 – fortsatt faktakontroll
- Kontrollera aktuella leveranskedjestandarder (NIST SSDF, SLSA) och skilj verifierbar proveniens från reproducerbarhet.
- Verifiera eventuella produkt- och regelverksbundna krav för AI-agenters användning och riskstyrd publicering i senare faktagranskning.


## Källgranskning r0056 – aktuell status per 8 november 2026

- Se `docs/kallregister-arbetsutkast.md` (K001–K010) och `docs/reviews/faktakontroll-och-kallhantering-r0056.md` för verifierat urval, avgränsningar och kvarstående risker.
- **Uppdaterad OWASP-status:** Den äldre kontrollpunkten om OWASP 2025 ovan är historisk. OWASP GenAI Security Project publicerade en ny Top 10 för LLM-applikationer den 4 augusti 2026. För framtida faktakontroller används 2026-utgåvan [K004], samtidigt som äldre källspår behålls som historik.
- **Källstyrka:** NIST, DORA, OWASP, Kubernetes, OpenTelemetry, FinOps Foundation och SLSA ger stöd för särskilda tekniska principer. De verifierar inte bokens fyra generationer som extern standard eller att alla framtida G4-lösningar är säkra.
- **Öppna blockerare:** rättsliga verksamhetsbeslut och mandat; AI-agenters säkerhet och kvalitet i praktisk miljö; källhänvisningarnas placering i boktexten; oberoende fackgranskning; avtalsspecifika licens- och driftsgarantier.
- **Bedömning:** Första sak- och källkontrollpass genomfört. Inga kapitel ännu slutligt faktagodkända.

## Revision r0059 – samlad kritisk sakgranskning

Intern genomgång av alla 17 kapitel, selektiv extern källkontroll och riktade preciseringar i kapitel 06, 08 och 17. Två nya referenser K011–K012. Se `docs/reviews/kritisk-sakgranskning-r0059.md` för kapitelmatris och kvarstående juridiska, tekniska och ekonomiska osäkerheter. Detta ersätter inte extern oberoende granskning eller ett formellt godkännande.
