# Redaktionell granskning – Kapitel 15, r0035

## Källor inom bokprojektet
- `docs/kallmaterial/kapitel/CAP-IT-13-kapitel.md`, version 2.0, daterad 7 november 2026.
- `docs/kallmaterial/granskningar/CAP-IT-13-granskning.md`, kritisk granskning version 2.0.
- `docs/kallmaterial/modeller/CAP-IT-13-modell.yaml` (orörd spårbarhetsmodell).
- Manuskapitel 9, 10, 12 och 14, samt redaktionella riktlinjer.

## Kritiska iakttagelser och genomförda beslut
1. **Servicelöfte:** sammanfört nätområdets tolv konceptuella tjänster till tre begripliga erbjudanden: anslutningar/trafikvägar, segmentering/extern trafik och felsökning/livscykel. Specialisttjänster för t.ex. fältkommunikation och mediedistribution behandlas inte som universella krav.
2. **G2 kontra G3:** skillnad mellan att grundläggande nätberoenden saknar ägare/dokumentation och att en fungerande men manuell tjänst behöver produktifieras för självbetjäning. Nya produkter är inte standardsvaret.
3. **Självbetjäning:** tydligt att etablering, ändring, felsökning och avveckling måste ingå. En portal som skickar manuella ärenden är inte ett fullgott G3-erbjudande.
4. **G4:** skapares behov och riskprofil styr anslutningar; agentens nätåtkomst är inte liktydig med verksamhetsmandat. Externa godkända SaaS/AI-tjänster behöver inte en separat intern nätmiljö.
5. **Konsekvens för övriga kapitel:** Nätverksförmågan ansvarar för teknisk nåbarhet och trafikpolicy, integration för kontrakt och informationsutbyte, identitet för autentisering/tillit, säkerhet för kompletterande skydd. Körmiljö ansvarar för exekveringen, även om den nyttjar nätprofiler.
6. **Proportionalitet:** ingen fullständig paketloggning eller service mesh som obligatorisk princip; nätverksredundans likställs inte med robusthet i hela applikationen.
7. **Redaktion:** inga CAP-IT/PLS-koder eller retorisk fetstil i läsarmanuset. Tekniska begrepp introduceras i verksamhetsnära sammanhang och generationsramen återberättas inte utförligt.

## Kvarstående kontroller
- Oberoende nätverks- och säkerhetsgranskning av policy-/trafikexemplen inför publicering.
- Fullständig tvärkapitelsgranskning när kapitel 11 och övriga ännu oskrivna förmågor finns.
- Formellt kapitelgodkännande saknas; detta är ett redaktionellt arbetsutkast.
- Underlagskapitlets externa källor har inte verifierats på nytt i denna revision; texten gör inga nya källberoende påståenden.
