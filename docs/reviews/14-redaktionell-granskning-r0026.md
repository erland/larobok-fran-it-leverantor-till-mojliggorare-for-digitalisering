# Redaktionell granskning – kapitel 14, r0026

## Underlag

Utgår från det granskade källkapitlet `docs/kallmaterial/kapitel/CAP-IT-08-kapitel.md`, dess granskningsrapport och YAML-modell, samt läsarmanus för kapitel 7–9 och 13 i r0025. Detta är en redaktionell intern granskning, inte oberoende teknisk sakgranskning.

## Viktigaste val

- Förmågan erbjuder körprofiler för VM, applikationsserver, container, batch och specialiserad beräkning. Ingen profil utpekas som obligatorisk eller synonym med en generation.
- Tekniska krav omfattar isolation, resurser, patchning, miljökonfiguration, felsökning och avveckling. Uppgifter som datalagring, byggkedja och operativ incidentledning placeras inte i körmiljöförmågan.
- Generation 3 konkretiseras som självbetjänad etablering och drift av arbetslaster utan central manuell ändringskö; ett team får inte automatiskt ansvar för den delade plattformens säkerhet och uppgraderingar.
- Generation 4 beskriver behovsstyrd tilldelning av körprofil snarare än att verksamheten ska förstå teknisk exekvering. Tre användningsnivåer illustreras kort; deras publiceringsprocess återberättas inte från kapitel 13.
- SaaS-assistenter kräver inte nödvändigtvis någon ny egen körmiljö; detta undviker antagandet att varje verksamhetsskapad lösning måste driftsättas i organisationens infrastruktur.

## Kritisk korsgranskning

- Kapitel 13 äger skapande, tester och leveransprocess; kapitel 14 äger exekvering och runtime-profiler. Exempel på återställning av programkod kopplas inte samman med databasåterställning.
- Kapitel 7 äger beständig datalagring; körmiljön äger inte själv datalagringsprofiler.
- Kapitel 8 äger AI-modelltjänster och agenternas AI-specifika orkestrering. Kapitel 14 omfattar teknisk exekvering av arbetslaster när organisationen faktiskt behöver drifta dem.
- Kapitel 9 äger informationsutbyte, inte teknisk drift av exekverande tjänster.
- Driftbarhet och motståndskraft ska senare beskriva monitorering, incidenter och återhämtning; körmiljöförmågan måste tillhandahålla signaler, health checks och ändringsmöjligheter, utan att ersätta driftbarhetens erbjudande.

## Återstående kontroller

- Sakgranska tekniska detaljpåståenden och aktuella produkter inför publicering.
- Kontrollera runtime-profiler och övervakningsansvar igen efter att kapitlet *Driftbarhet och motståndskraft* skrivits.
- Formellt kapitelgodkännande saknas; manus är ett arbetsutkast.
