# Kritisk granskning – CAP-IT-03, version 2.0

*7 november 2026. Genomgång av ursprungskapitel 1.0 och tillhörande YAML. Slutsatserna är en redaktionell och arkitekturteknisk analys, inte ett utlåtande om en verklig organisation.*

## Samlad bedömning

Kapitelstrukturen är ändamålsenlig och bör behållas. G2-perspektivet, skillnaden mellan att rätta generationsarv och bygga G3-självbetjäning samt teknikneutraliteten är styrkor. Granskningen fann däremot en saklig motsägelse mellan text och YAML och flera otillräckligt konkreta verifieringskrav. Version 2.0 rättar dessa utan att ändra de två PLS-identiteterna eller PLT-kopplingen.

## Identifierade brister och genomförda ändringar

1. **Motsägelse om exakt historisk reproduktion – hög prioritet.** Kapitel 1.0 medgav att historisk indata kan ha försvunnit, men PLS-008/G1 krävde identisk omkörning. Provet kräver nu förklaring av faktiskt beslutsunderlag och bara identisk omkörning när nödvändiga beroenden finns och får användas.
2. **Otillräcklig åtskillnad mellan beslutets bevis, reproduktion och omprövning – hög.** Nytt avsnitt om regelartefakter, källvärden och bevarandebegränsningar. En hash ersätter inte sparat beslutsunderlag.
3. **Övergångsbestämmelser saknade praktiskt prov – hög.** Nytt exempel med decemberansökan och januaribeslut; gäller endast om verksamhetens rättsregel väljer relevant datum. Registreringstid respektive verksamhetsgiltig tid behandlas skilt.
4. **Beslutstyperna riskerade att blandas ihop – medelhög.** Nytt avsnitt om deterministisk regelutvärdering, mänsklig bedömning och AI-rekommendation med olika verifieringskrav. Automatiserad regelkörning ger inte i sig rättsligt mandat.
5. **YAML saknade kontroll av motorbyte och kapacitet – medelhög.** PLS-008/G3 provar belastning, isolering och fel; PLS-009/G3 provar export/import och resultatjämförelse. Ett deklarerat DMN-stöd innebär inte nödvändigtvis likvärdig runtime.
6. **G4-prioritering var för generell – medelhög.** PLS-009:s AI-assisterade funktion görs tillämplighetsstyrd, inte automatiskt kritisk i G4. Publiceringskontroll ligger fortsatt utanför prompten.
7. **Indikatorer kunde vara svåra att använda – medelhög.** Nytt test för ändrad extern källa, övergångsbestämmelse och modellportabilitet.
8. **Begreppsdubletter mot närliggande kapitel – låg.** YAML skiljer på regelversion, beslutsversion, beslutskorrelation, verksamhetsgiltig tid och registreringstid. Detta är ett förslag till bokens ordlista som behöver harmoniseras centralt.

## Separering av stöd

**Källmodellen:** CAP-IT-03 med PLS-008 Besluts- och regelkörning och PLS-009 Beslutsmodellering och simulering, båda inom PLT-002.

**Teknisk extern verifiering:** OMG:s officiella sida visar DMN 1.6 som formell version och DMN 1.7 som beta per granskningstillfället. NIST AI RMF och den generativa AI-profilen ger riskprinciper men ingen generell rättslig tillåtelse för automatiska beslut.

**Analytiska tillägg:** Testfall, prioriteringar, särskilda tidsbegrepp, felsökningsordning och val mellan lokal kod och delad plattform är rekommendationer, inte direkt källstyrda mognadskrav.

## Kvarstående frågor inför publicering

- Juridisk sakgranskning av övergångsbestämmelser, retroaktivitet, automatisk beslutsfattning, bevarande och gallring i varje faktisk verksamhetsdomän.
- Harmonisering av termer med CAP-IT-02, CAP-IT-04, CAP-IT-06 och CAP-IT-07.
- Externa sakkunnigas bedömning av testkriterier och vilken nivå av beslutsspårning som är proportionerlig för olika riskklasser.
- Kontroll av att bokens framtida exempel inte ger sken av att en viss DMN-motor är obligatorisk eller fullt portabel.

## Samlad slutsats

Version 2.0 är en bättre faktaboksmall med klarare beviskrav och mer nyanserade G4-bedömningar. Den är internt granskad, inte slutligt sakgranskad för publicering.
