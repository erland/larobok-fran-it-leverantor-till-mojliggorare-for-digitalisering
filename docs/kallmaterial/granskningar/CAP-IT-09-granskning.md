# Kritisk granskning – CAP-IT-09, faktaboksunderlag v2

*Granskad och reviderad till version 3.0, 7 november 2026*

## Samlat omdöme

Kapitlet är en bra grund för faktaboken: generation 2 får rätt tyngd och den viktiga skillnaden mellan kvarvarande G1→G2-brister och behovet av G2→G3 framgår. Det är ännu mer ett kvalificerat fackkapitel än en helt nybörjarorienterad introduktion. Rekommendationen är att **behålla dispositionen**, förtydliga några sakliga gränser och skärpa bedömningsstödet, inte att bygga om allt.

## Identifierade brister och åtgärder

| Bedömning | Iakttagelse i v2 | Åtgärd i v3 |
|---|---|---|
| Hög | Återställning riskerar att låta som att hela distribuerade tillståndet kan spolas tillbaka | Skiljer auktoritativa data, återbyggbara index och irreversibla externa händelser; kräver avstämning/kompensation |
| Hög | Generation 4 antyder att felaktiga agenthandlingar går att återställa med versionsåtergång | Skiljer rollback av programversion från kompensation av affärshändelse |
| Medel | Kopplingen mellan kritikalitet och återställningsprofil behöver bli prövbar | Introducerar RPO/RTO och kopplar mål till verksamhetens krav och prov |
| Medel | Funktionsindikatorer kan tolkas som enstaka lyckade demonstrationer | Betonar jämförbara incidenter, återkommande övningar, personaloberoende och faktiska prov |
| Medel | Förmågan kunde uppfattas som ansvarig för all teknisk resiliens | Förtydligar beroendet till applikationsarkitektur, runtime och datahantering |
| Medel | Tekniska brister blandas ibland ihop med leverans- och organisationsproblem | Nytt beslutsstöd med tre kontrollfrågor före produkt- eller generationsbeslut |
| Låg | Metatext i inledningen riktad till bokprojektet | Ersatt med läsarorienterad ingress |
| Låg | Vissa fackord introduceras utan tydlig innebörd | Lägger till operativa exempel för SLI/SLO och definition av RPO/RTO |

## Styrkor att bevara

- Generation 1 är kort och fungerar som igenkänningsbakgrund.
- Generation 2 är tyngdpunkten med två separata förbättringsspår.
- Indikatorer på fel teknik/plattform är inte likställda med automatiska utbytesbeslut.
- Generation 4 markeras som framåtblickande snarare än säker prognos.
- PLS-/PLT-spårbarheten finns utan att huvudtexten blir en tjänstekatalog.

## Öppna redaktionella frågor inför nästa kapitel

1. Hur mycket fackterminologi målgruppen ska förväntas förstå: i v3 definieras några termer, men begreppsregister för hela boken behövs.
2. Referenserna i slutet är huvudsakligen principstöd. Koppla i bokarbetet källorna mer exakt till påståenden och särskilj normativ egen analys från formell standard.
3. En genomgående figur över ärendeflöde/incidentkedja kan senare öka pedagogiken, men bör planeras för hela boken i stället för att adderas ad hoc.
4. Granska nästa förmåga med samma checklista för att upptäcka om modellens sex indikatorperspektiv fungerar även utanför driftområdet.

## Källkontroll

Primärmodellens CAP-IT-09 och tjänsterna PLS-035, PLS-036, PLS-037, PLS-038, PLS-070 bibehålls. Externt verifierades att Google SRE behandlar övervakning av distribuerade system, att OpenTelemetry har dokumentation om semantiska konventioner och att NIST SP 800-61 Rev. 3 avser specifikt hantering av cybersäkerhetsincidenter. Inget av dessa dokument ensamt bevisar generationsmodellen, som är en syntes.

## Beslut

**Rekommenderad status: bra som mall för nästa kapitel efter redaktionell granskning, men inte slutligt publiceringsgodkänd faktabokstext.**
