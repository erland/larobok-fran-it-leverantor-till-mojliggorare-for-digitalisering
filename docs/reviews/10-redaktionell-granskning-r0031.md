# Redaktionell pilotgranskning – Identitet och tillit (r0031)

## Underlag
- `docs/kallmaterial/kapitel/CAP-IT-07-kapitel.md` och motsvarande granskning och YAML-modell.
- Manuskapitlen 7–9 och 13–16 samt bokprojektets redaktionella principer.

## Redaktionsbeslut
- Läsarmanuset koncentreras kring det gemensamma tjänsteerbjudandet: mänskliga identiteter, federation, auktorisationsstöd, privilegierad åtkomst, arbetslastidentiteter, certifikat, hemligheter och livscykel.
- Generation 2 ges endast som kort utgångspunkt. Generation 3 fokuserar på automatiserad självbetjäning, inte snabbare manuella beställningar.
- Generation 4 beskriver behovsstyrda identiteter och spårbar, avgränsad delegation för verksamhetsskapade assistenter och agenter. Permanent unik identitet för varje agent föreskrivs inte.
- Ansvar för verksamhetsregler och slutlig auktorisation förblir hos den skyddade resursen; integrationsplattformen äger teknisk anslutning; utvecklingsplattformen äger skapandevägen.
- Inga CAP-IT-koder eller överflödig fetstil används i läsarmanuset. Källtextens tio plattformstjänster nämns funktionellt och utan interna produkt-ID.

## Kritiska kontrollpunkter
1. Maskinidentitet är inte identisk med mänsklig inloggning; tekniska behörighetsbevis och delegerade användarmandat behöver särskiljas.
2. Central kontospärr garanterar inte omedelbar återkallelse av aktiva sessioner eller alla redan utfärdade token.
3. En agent får inte ärva obegränsade användarrättigheter; mandat måste prövas vid verkställighet.
4. Återkallelse är inte detsamma som kompensation för redan utförd åtgärd.
5. Särskild signering och extern federation är behovsstyrda, inte obligatoriska produktinköp.

## Kvarstående arbete
- Formell kapitelgranskning och oberoende IAM-/säkerhetssakgranskning återstår.
- Vid slutlig faktagranskning: kontrollera identitetsstandarder och publiceringsdatum för NIST SP 800-63-4, RFC 9700 och OWASP:s vägledning om icke-mänskliga identiteter; dessa är källmaterialets referenser och definierar inte generationsmodellen.
- Helhetsgranska slutligen terminologin identitet, auktorisation, tillit och delegation genom boken.
