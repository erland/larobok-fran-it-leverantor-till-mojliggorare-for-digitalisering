# Kritisk samgranskning av förmågekapitel 7, 8, 9 och 13 – r0025

## Underlag och metod

Granskade samtliga fyra läsarmanus i r0024 i sin helhet, med projektets redaktionella canon och tidigare granskningar som jämförelse. Fokuserade på tjänsteansvar, utvecklings- och verksamhetsperspektiv i generation 3 och 4, återkommande exempel, teknisk precision och läsbarhet. Det är en intern redaktionell och arkitektonisk granskning, inte en oberoende sakgranskning.

## Bedömning

Den övergripande fördelningen håller och bör bevaras:

| Förmåga | Äger det gemensamma erbjudandet för | Äger inte |
|---|---|---|
| Datahantering och informationslagring | Databaser, lagring, analytiska dataplattformar, ETL/ELT, dataförvaltning | BI-rapporter, AI-modeller eller verksamhetsapplikationers leveransprocess |
| Analys, sökning och intelligent informationsbearbetning | Sökindex, BI-/analystjänster, modellåtkomst, AI-utvärdering och agentrelaterade stödtjänster | Dataplattformens källdata, applikationernas publiceringsprocess eller mandat i källsystem |
| Integration och informationsutbyte | API:er, köer, händelser, filutbyte, systemkontrakt och anslutna verksamhetsfunktioner | Analytisk bearbetning eller ägarskap av processregler |
| Utveckling och teknisk leverans | Skapande, versionshantering, bygg, test, leveransväg, spårbar överlämning och avveckling | All applikationsdrift eller tekniskt ägande av integrerade data-, AI- och integrationstjänster |

## Identifierade problem och justeringar

1. **Dubbla AI-exempel i kapitel 8 och 13.** Båda beskrev personlig assistent kontra åtgärdsagent, risknivåer och vem som kan publicera. Kapitel 13 har nu huvudansvaret för publiceringsnivåer och överlämning; kapitel 8 beskriver endast de AI-specifika tjänsterna och deras integration i leveransvägen.
2. **Otydlig gräns kring AI-utvärdering.** Kapitel 13 låter nu utvecklingsförmågan kräva och ta emot resultat vid publicering, medan kapitel 8 tillhandahåller utvärdering av modellbeteende. AI-stödd kodgranskning skiljs från utvärdering av AI-funktioners svar och verktygsanrop.
3. **Risk för att utvecklingsplattformen sägs äga hela körmiljön.** Gränsen mot *Applikationsexekvering och körmiljö* och *Driftbarhet och motståndskraft* behålls. Kapitlet avslutas med en kortare ansvarsfördelning, inte ytterligare en teknikkatalog.
4. **Överlämning från verksamhetsskapad lösning var alltför optimistiskt formulerad.** Det framgår nu tydligare att överförbara artefakter och beroenden är mål, medan teknisk ombyggnad kan behövas.
5. **Risknivå kan förändras över tid.** Kapitel 13 nämner nu uttryckligen att en från början personlig lösning kan kräva ny prövning när användare eller data förändras.

## Kontrollpunkter utan textändring

- Kapitel 7 och 9 behöver inte revideras denna gång: ETL/ELT och systemtransport har tydliga gränser och kompletterar utvecklingskapitlets ansvar.
- Analys-/BI-rapportpublicering i kapitel 8 är en förmågespecifik funktion; godkännande och leverans av en *verksamhetsapplikation* ligger i kapitel 13. Dessa olika publiceringsbegrepp bör hållas isär även i kommande kapitel.
- Ordet *agentkörmiljö* i kapitel 8 avser AI-specifik modell-/verktygsorkestrering. Infrastruktur för att köra en hel applikation behöver senare avgränsas i *Applikationsexekvering och körmiljö*.
- Sökindexering och dataplattformens ETL/ELT skiljs redan åt tillräckligt tydligt; inga ytterligare långa förklaringar behövs.
- De tre risknivåerna i kapitel 13 är exempel på erbjudandets nivåer, inte formella generationsgränser eller separata plattformskrav.

## Öppna granskningsbehov

- Vid skrivande av kapitlen om körmiljö, driftbarhet, identitet och cybersäkerhet: kontrollera åter risk- och livscykelansvar, åtgärdsmandat, observerbarhet, backup och återhämtning.
- Inför publicering: sakgranska aktuella påståenden om AI-plattformar, agenternas mandatkontroll, supply-chain-säkerhet och dataåtkomst mot primärkällor.
- Formellt kapitelgodkännande återstår.

## Redaktionellt resultat

Kapitlen har nu en tydligare fördelning: data och integration ger tjänsterna, analys/AI ger sina specialiserade funktioner och utvecklingsförmågan erbjuder den sammanhängande vägen att skapa och leverera lösningar. Generation 3 innebär självständighet för professionella team; generation 4 tillför behovsstyrt skapande och en kontrollerad livscykel för verksamhetsskapade lösningar. Inget nytt generellt generationsresonemang har förts in.
