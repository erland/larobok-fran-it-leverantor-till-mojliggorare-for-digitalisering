# Kritisk korsgranskning och revision – kapitel 7, r0017

## Underlag
- Tidigare manus r0016, ursprungligt granskat kapitel och YAML-modell för *Datahantering och informationslagring*.
- Ursprungligt kapitel för *Integration och informationsutbyte* och bokmanusets kapitel 8.
- Externt stöd: Microsoft Azure Architecture Center, *Understand Data Models* / *Choose a Data Store*; AWS, *Choosing an AWS Database Service* (2026). Externa vägledningar beskriver databasmodeller och val efter arbetslast, inte vår generationsmodell.

## Granskning och ändringar
1. Förstärkt förmågan som leverantör av operativa databaser och lagring, inte bara analytiska data.
2. Tagit med relations-, dokument-, nyckelvärdes/cache-, graf- och tidsseriedatabaser samt fil/objektlagring, men klargjort att kategorierna inte är en rekommendation att införa en av varje.
3. Synliggjort skillnaden mellan databastjänst och underliggande lagringsinfrastruktur samt kravstyrda tjänsteprofiler.
4. Beskrivit ETL/ELT som huvuddel av dataplattformens inläsning och förädling, med *Integration och informationsutbyte* som leverantör av överföringsmekanismer vid behov.
5. Konkretiserat generation 3 med ett centralt data warehouse-team som går från obligatorisk utförare av varje pipeline till leverantör av självbetjänade pipelineverktyg och gemensamma villkor.
6. Generation 4 fokuserar på godkända datamängder och proportionerlig, begränsad lagring för verksamhetsskapade lösningar utan rå åtkomst till produktionsdatabaser som standard.
7. Bevarat skillnaden mellan dataförmågan och BI/analys/AI samt korsreferenser med kursiverade namn; inga interna CAP-IT-koder i läsarmanuset.

## Särskilda reservationer
- Flera lagringsmodeller kan tillhandahållas av samma produkt. Databasval avgörs av arbetslast, skyddsbehov, livscykelkostnad och driftskompetens; generation 3/4 kräver inte specifika produkter.
- Radering och åtkomståterkallelse kan inte garantera omedelbar borttagning av alla befintliga kopior; sektorsspecifik juridisk granskning återstår.
- Formellt kapitelgodkännande och extern faktagranskning återstår.

## Referenser för ny komplettering
- Microsoft, *Understand Data Models*, https://learn.microsoft.com/en-us/azure/architecture/data-guide/technology-choices/understand-data-store-models
- AWS, *Choosing an AWS database service* (uppdaterad 2026-06-02), https://docs.aws.amazon.com/decision-guides/latest/decision-guides/databases-on-aws-how-to-choose.html
