# Kritisk granskning och revidering – CAP-IT-06

*7 november 2026 · Version 2.0 · granskningsresultat och spårbar ändringslogg*

## Samlad bedömning

**Godkänd som reviderat faktaboksunderlag, ännu inte som slutligt publiceringsklart kapitel.** Grundstrukturen i version 1 har behållits: kort G1-bakgrund, G2 som huvudperspektiv, tydlig skillnad mellan generationsarv och G3:s produktifierade självbetjäning samt en villkorad analys av G4. Alla åtta källmodellstjänster och fyra PLT-anknytningar är bevarade.

## Vad granskningen fann och ändrade

1. **Hög – saknat dubbelskrivningsproblem.** Kapitelversion 1 beskriver retries och dubbletter men inte konsekvenserna när ett databascommit och en brokerpublicering inte sker atomiskt. Ett nytt avsnitt förklarar förlorade och duplicerade händelser, transaktionell utkorg och alternativ samt provar två separata avbrottspunkter. YAML har fått ett särskilt G2-scenario och kompletterade kontroller för PLS-021 och PLS-024.
2. **Hög – otydliga gränser för 'exactly once'.** Version 1 var försiktig men explicit åtskillnad saknades mellan brokerintern leverans/transaction, lokal konsumtion och extern verksamhetseffekt. Detta förtydligas utan att hävda en generell exakt-en-gång-garanti; exempel visas i PLS-021 och PLS-022.
3. **Medel – API-retries och idempotensnycklar.** Text och PLS-020 kompletteras med nyckelns giltighetstid, omfattning och hantering av samma nyckel med nytt innehåll. Det specificerar avtalat beteende snarare än en viss implementation.
4. **Medel – återspelning och felkö.** Dead-letter queue får uttryckligt krav på åtkomst, retention, utredningsansvar och säkert återspelningstillstånd. Strömmars ordningsgaranti förtydligas som kontextberoende (ofta per partition/nyckel).
5. **Medel – filkvittens och kontrollsumma.** Kontrollsumma skiljs från avsändarautentisering och mottagarens verksamhetsacceptans. PLS-023-provet ändras i samma riktning.
6. **Medel – indikatorer kan misstolkas.** Andel tekniska fel är inte samma mått som verksamhetsfel. Diagnosen kompletteras med tekniskt utfall, faktisk effekt, återhämtningstid och ansvar. Inga godtyckliga mognadsprocent införs.
7. **Medel – kontraktskompatibilitet.** PLS-080 testar nu uttryckligen att tekniskt kompatibel struktur kan ändra verksamhetsbetydelse. G3-kapitlet hänvisar till *kända* konsumenter – upptäckt av okända konsumenter kan inte garanteras.
8. **Medel – G4:s verktygstillit.** Maskinläsbara verktygsbeskrivningar kan vara felaktiga eller opålitliga. Beskrivningen kompletteras med källa, godkännande och verkställighet vid betrodd kontrollpunkt; befintlig nyansering av köade och redan utförda uppdrag behålls.
9. **Låg – risk för generationsdeterminism.** Separata bedömningar av funktion, plattform och automation behålls. Alla tjänster är fortsatt tillämplighetsstyrda; ingen ny obligatorisk teknik eller leverantör införs.
10. **Källtransparens.** Två externa, tydligt märkta tekniska referenser om dual-write och transaktionsgarantier har tillförts. Ursprungliga identiteter, terminologi och baseline v1.1 behålls.

## Källgrund och externa tillägg

**Bevarat från användarens underlag:** definitionen CAP-IT-06, de åtta PLS-ID:na, deras PLT-kopplingar, generationernas ram och gränsdragning mot andra CAP-IT. Detaljerade tekniska diagnoser och generationsprioriteringar är analytiska tillägg, inte givna källkrav.

**Externt verifierat stöd:** AWS Prescriptive Guidance, *Transactional outbox pattern*, https://docs.aws.amazon.com/prescriptive-guidance/latest/cloud-design-patterns/transactional-outbox.html, beskriver dual-write-fel och mönstrets förutsättningar. Spring for Apache Kafka, *Exactly Once Semantics*, https://docs.spring.io/spring-kafka/reference/kafka/exactly-once.html, beskriver en transaktionsgaranti för en definierad read-process-write-kedja, inte generellt alla externa affärseffekter. Dessa är exempel på tekniska lösningar och garantigränser – inte rekommendationer om viss leverantör.

## Kvarvarande osäkerheter och publiceringskontroller

- Gå igenom varje verksamhetskontrakts juridiska och semantiska innebörd; detta går inte att avgöra utifrån generisk referensmodell.
- Kvalitetssäkra försäkringar om faktisk meddelandeleverans, retention och ordning mot den specifika brokern, dess konfiguration och systemets driftvillkor.
- Bedöm CAP-IT-02:s ansvar för processorkestrering mot integrationsadaptering. Överlappet är medvetet men behöver harmoniseras när CAP-IT-02 skrivs.
- Kontrollera om offline-synkroniseringens PLS-075-gräns mot dataägarskap i CAP-IT-04 ska illustreras gemensamt.
- Språklig harmonisering, indexering av idempotens/leveransgaranti, extern sakgranskning och publiceringsgranskning återstår.

## Verifiering

YAML:s struktur, bevarade ID:n och 4 generationer per tjänst kontrolleras maskinellt. Kapiteltext och ZIP valideras vid paketering.
