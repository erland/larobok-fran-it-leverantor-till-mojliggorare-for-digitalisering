# Kritisk granskning – CAP-IT-02, version 2

*7 november 2026 · Bas: CAP-IT-02 version 1.0; reviderad text och YAML 2.0*

## Samlad bedömning

**Godkänd som reviderat faktaboksunderlag, inte som slutligt publiceringsmanus.** Ursprungstexten hade en stark generation 2-orientering och rimlig ansvarsfördelning, men saknade tillräcklig behandling av samtidiga uppdateringar och operativ processmigration. Ett lokalt motexempel saknades också, vilket riskerade att favorisera workflowmotorer trots uttrycklig teknikneutralitet.

## Identifierade brister och åtgärder

| Grad | Ursprunglig brist | Åtgärd i version 2 |
|---|---|---|
| Hög | Två samtidiga ärendeuppdateringar kunde bägge accepteras utan definition av konfliktutfall. | Nytt avsnitt om förlorad uppdatering, versionskontroll, samtidiga beslut och fördröjda händelser; skärpta PLS-006- och PLS-007-prov. |
| Hög | Processdefinitionsversionering var nämnd, men verifiering av aktiva timers, uppgifter och migrering saknades. | Separat avsnitt och G3-scenario för versionssamexistens, kontrollerad migrering och avvisad migrering; PLS-005-prov skärpta. |
| Hög | Risk för att begreppet rollback uppfattades som generell möjlighet vid processversionsbyte. | Ersatt med kontroll av versionssamexistens och instansmigration; tydliggjort att migrering inte garanteras av standardformat. |
| Medel | Teknikneutraliteten saknade ett utvecklat fall där en central workflowmotor vore ett sämre val. | Nytt lokalt motexempel med tre steg i en transaktionell tillståndsmaskin. |
| Medel | Äldre händelser och upprepade ändringar hade otillräckligt definierade utfall. | Nya prov om försenad statushändelse och idempotens med auktoritativ ärendeversion. |
| Medel | Risk att arbetsköstilldelning läses som beslutsmandat. | Konkurrensprov för slutförande/omfördelning; befintlig mandatgräns behålls. |
| Medel | Notifikation kunde misstolkas som rättslig delgivning. | Ett förtydligande om att aviseringsspår inte i sig utgör bevis om rättslig delgivning. |
| Medel | G4-betydelsen av gemensam plattform blev för kategorisk för specialiserade funktioner. | Vissa tjänsters G4-plattformsbehov ändrat till situationsberoende vid faktisk användning. |
| Låg | En själv-referens till CAP-IT-02 fanns i PLS-007:s beroendelista. | Självreferensen borttagen. |

## Spårbarhet och källstatus

Källmodellens fyra direkta tjänster PLS-004, PLS-005, PLS-006, PLS-007, deras namn och PLT-002/PLT-024 bevaras. Generationsprioriteringar, nya tester och diagnosmetoder är analytiska rekommendationer och inte direkta krav i källmaterialet.

Teknisk extern kontroll: Camundas produktdokumentation om processinstansmigration och versionshantering används för att visa att migrering har verkliga begränsningar (aktiva steg, typmappning, väntelägen och versionshistorik); produkten används som **illustrativt exempel**, inte som generellt krav eller rekommendation. Tidigare referenser till OMG, saga-mönstret och NIST AI RMF kvarstår.

## Kvarvarande begränsningar före publicering

1. Juridiska krav kring beslutsfattande, diarieföring, dokumentation och delgivning är jurisdiktions- och verksamhetsspecifika och måste sakgranskas separat.
2. Alla samtidighetsstrategier passar inte alla databaser och arkitekturer. Testerna behöver göras i vald produkt och med representativ belastning.
3. Den faktiska migreringsförmågan måste verifieras per processmotor och version. Ett generellt bokkapitel kan inte lova att alla typer av instanser går att migrera.
4. Bokens terminologi (ärendetillstånd, processinstans, tjänsteåtgärd, korrelation, kvittens) bör harmoniseras mot CAP-IT-04, -06 och -07 inför slutredigering.
5. Extern verksamhets- och teknisk sakgranskning återstår.

## Verifiering

- Fyra direkta PLS och två ursprungliga PLT-kopplingar bevaras.
- Fyra generationsprofiler per tjänst bevaras.
- YAML valideras maskinellt och ZIP kontrolleras efter paketering.
