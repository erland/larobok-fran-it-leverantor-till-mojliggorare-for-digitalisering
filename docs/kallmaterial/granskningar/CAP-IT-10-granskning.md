# Kritisk granskning av CAP-IT-10 – version 1 till 2

*7 november 2026 · intern redaktionell och teknisk granskning*

## Samlad bedömning

Kapitlet har en begriplig och konsekvent G2-centrerad struktur. Det visar hur monoliternas samlade releaseprocess kan leva kvar som flaskhals när tjänsterna blir fler, och varför en verklig G3-förflyttning handlar om förvaltade, självbetjänade erbjudanden snarare än ett specifikt verktyg. Det var lämpligt att revidera kapitlet före fortsatt arbete.

## Identifierade brister och ändringar

| Område | Brist/risk i v1 | Ändring i v2 |
|---|---|---|
| Reproducerbarhet och proveniens | Dokumenterat ombyggbart, bitidentiskt reproducerbart och verifierat ursprung låg för nära varandra | Begreppen skiljs uttryckligen; skyddad byggmiljö och verifiering tillkommer |
| Generationsneutralitet | Specialiserade AI-tjänster kunde få för stark G1/G2-kritikalitet i strukturerad modell | G1/G2 görs situationsberoende och endast tillämpligt vid faktisk användning |
| Generation 3 | Självbetjäning vid skapande var tydligare än undantag och fortsatt förvaltning | Undantag, uppgraderingar och frivillig användning förs in som bedömningskriterier |
| Generation 4 | Indikatorer för tillräckligt stöd och olämpliga teknikval var inte tillräckligt fristående | Ny undersektion med verifierbara exempel, inklusive begränsade agentmandat |
| Mobilappar | Rollback kunde uppfattas som lika enkel som serverrollback | Tjänsteprov ändrat till incidentbegränsning och korrigerande release, utan löfte om omedelbart återkallande |
| Säkerhetstest | Testhemlighet kunde misstolkas | Använd bara syntetisk indikator i isolerad miljö |
| Mätetal | Risk för otydliga eller oförenliga definitioner | Preciserat ledtid, felandel, återhämtning och kravet att definiera måtten konsekvent |
| Källornas aktualitet | SLSA v1.1 användes fast officiella webbplatsen anger v1.2 som aktuell | Uppdaterad hänvisning till SLSA v1.2; NIST SSDF-utkast tydliggjort |

## Viktiga styrkor som bevarats

- G1→G2 behandlas som ett kvarvarande generationsarv, inte en obligatoriskt färdig etapp.
- G2 skiljer grundläggande tillförlitlig leverans från skälen att produktifiera gemensamma utvecklingstjänster.
- Exemplet med ärendehantering gör gränsöverskridande kontrakt och teamansvar konkreta.
- Teknik- och plattformsvarningar leder till undersökningar, inte automatiska produktbyten.
- Alla tio tjänster och rätt förmågegränser är kvar.

## Fortfarande kvarstående begränsningar

1. Kapitlet är en referensbeskrivning, inte ett värderat nuläge för någon viss organisation.
2. Risknivåer, avtalskrav och säkerhetsregler måste anpassas till faktisk verksamhet och jurisdiction.
3. Generationsmodellen är pedagogisk och inte en officiell mognadsstandard.
4. Extern ämnesgranskning och slutlig källkontroll återstår inför publicering.
5. Plattformstjänsternas ID:n och den fulla tabellen kan flyttas till bilaga när den slutliga boken redigeras.

## Bedömning

**Godkänd som arbetsunderlag för nästa kapitel**, inte slutligt publiceringsgodkänd. Den gemensamma kapitelmodellen behöver inte ändras, men kontroll av tjänsternas *tillämplighet* ska vara obligatorisk när förmågor innehåller specialiserade tjänster.
