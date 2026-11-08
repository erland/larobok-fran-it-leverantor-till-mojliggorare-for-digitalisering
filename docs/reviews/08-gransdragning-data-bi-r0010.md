# Redaktionell gränsdragning – CAP-IT-04 och CAP-IT-05 (r0010)

## Ställningstagande

**CAP-IT-04 (datahantering):** tillhandahåller data warehouse, data lake, lakehouse och deras datalagring, dataflöden, tekniska datamodeller, kvalitets- och metadatahantering. Frågefunktioner som är inbyggda i samma produkt förvaltas praktiskt tillsammans, men deras konsumtion för analys beskrivs under CAP-IT-05.

**CAP-IT-05 (analys/BI):** tillhandahåller analysåtkomst, fråge- och beräkningsmöjligheter, BI-miljö, visualisering, semantiska mått, rapportpublicering, distribution samt sök- och AI-funktioner. Plattformen äger inte rapporternas verksamhetsbetydelse.

## Ansvarsmatris

| Del | Förmåga | Ansvar |
|---|---|---|
| Datainläsning, historik, warehouse/lakehouse, dataavtal | CAP-IT-04 (med CAP-IT-06 för utbyte) | Data-/plattformsteam och dataansvarig |
| BI-verktyg, rapportmotor, publiceringsyta, semantiskt modellstöd | CAP-IT-05 | BI-/analysplattformsteam |
| Gemensamma mått och definitioner | CAP-IT-05 som tekniskt stöd, verksamheten beslutar | Informations-/måttägare, tvärfunktionellt förvaltade |
| Lokal BI-rapport, tvärgående dashboard eller lagstadgad rapport | CAP-IT-05 som tekniskt stöd | Rapportägande team/verksamhet, med relevanta kontrollkrav |
| Rapporter i transaktionssystem | CAP-IT-05 för återanvändbara analysbyggblock, CAP-IT-01 för presentation | Applikations-/produktteam |
| Realtids-/operativ uppföljning direkt från transaktionsdata | CAP-IT-04 för datagrund, CAP-IT-05 för analys | Produktteam, krav på prestanda/aktualitet |

## Bedömning av rapportbehov

1. **Gemensam BI/ledningsrapportering:** stabil datagrund från warehouse/lakehouse; styrda mått, certifierade datakällor och behörighetsstyrd publicering.
2. **Självbetjänad/ad hoc-analys:** godkända datamängder, åtkomsträttigheter och isolerade arbetsytor; utforskande resultat är inte automatiskt officiella mått.
3. **Schemalagda/regulatoriska rapporter:** reproducerbara definitioner, kontroll, signering eller godkännande efter krav, versionering och spårbarhet.
4. **Operativa rapporter:** kan ligga nära verksamhetssystemets transaktionsdata när aktualitets- och svarstidskrav gör ett batchbaserat warehouse olämpligt.
5. **Verksamhetsskapade rapporter i G4:** enkel självbetjäning från godkända datakällor, men tydligare kontroll när rapporter delas eller påverkar beslut.

## Redaktionell konsekvens

- Kapitel 08 är nu uppdaterat. Originalkällkapitel och YAML-modeller har inte ändrats.
- Kapitel 07 är planerat men inte skrivet; avsnittet om warehouse/lakehouse ska formuleras utifrån samma gräns.
- Undvik att göra tekniskt integrerade sviter till artificiellt åtskilda produkter.
- Källa till produktillustration: Microsoft Learn, *Data storage options in Microsoft Fabric*, https://learn.microsoft.com/en-us/fabric/fundamentals/store-data (åtkomst 2026-11-08). Detta stödjer att integrerade lösningar omfattar både lagring, SQL-frågor och semantiska BI-modeller; vår CAP-indelning är ett redaktionellt arkitekturbeslut.

**Granskningsstatus:** redaktionellt arbetsutkast. Ingen formell kapitelsignering eller extern faktagranskning.
