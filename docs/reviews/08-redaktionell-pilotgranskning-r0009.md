# Kritisk revision av kapitel 08 – r0009

## Utgångspunkt
Användarens synpunkt: r0008 lade för stor vikt vid hur verksamheten använder och bedömer analys, och för liten vikt vid vilka gemensamma IT-tjänster utvecklingsteamen behöver. AI-avsnittet täckte inte ambitionsnivån från kapitel 2.

## Genomförda korrigeringar
- Ersatte den långa exempelberättelsen om ärendeurval med ett behovsbaserat perspektiv på utvecklingsteamens byggblock.
- Byggde om kapitlet i tre huvudsakliga funktionsgrupper: analys, sökning och AI.
- Fördjupade AI-delen med modellåtkomst/gateway, RAG och grounding, verktyg/skills, agentkörmiljö, utvärdering, spårning, kostnader och skydd.
- Skilde mellan generativ AI och traditionell maskininlärning; ingen obligatorisk egen träning eller GPU-miljö.
- Förtydligade sambandet mellan professionella team i generation 3 och verksamhetsbyggda assistenter i generation 4.
- Behöll källmodellens sakliga avgränsningar, men tog inte in dess 16 tjänster som produktkatalog i lästexten.
- Avslutade med konkreta prov av förmågan snarare än allmänna frågor om analysverksamhetens effekt.

## Källspårning och tillägg
**Befintligt projektunderlag:** `docs/kallmaterial/kapitel/CAP-IT-05-kapitel.md`, `docs/kallmaterial/modeller/CAP-IT-05-modell.yaml`, `docs/kallmaterial/granskningar/CAP-IT-05-granskning.md`. Därifrån kommer källmodellens sexton plattformstjänster, distinktionen mellan återkommande behov och valfria plattformar, kvalitetskrav, dataåtkomst och generationsinriktning.

**Extern komplettering och nutida exempel** (verifierade 2026-11-07):
- NIST AI 600-1 (2024), generativa AI-risker och riskhantering: https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence
- OWASP Top 10 for LLM Applications (2025), särskilt prompt injection, excessive agency, vektor/embedding och resursförbrukning: https://genai.owasp.org/llm-top-10/
- Microsoft Foundry Agent Service, dokumentation om agentkörmiljö, verktyg, identitet, testning, spårning, publicering och övervakning: https://learn.microsoft.com/en-us/azure/foundry/agents/overview
- Google Cloud RAG Reference Architectures, exempel på separata komponenter i kunskapssökning och grounding: https://docs.cloud.google.com/architecture/rag-reference-architectures

Dessa kompletteringar används för att kontrollera rimliga arkitekturmönster och begrepp, inte som bevis för att en specifik produkt ska införas. Resonemangen om vilka gemensamma erbjudanden organisationen bör prioritera är redaktionella/arkitektoniska rekommendationer.

## Kvalitetsbedömning
- Bättre överensstämmelse med CAP-IT-05:s avsedda **IT-förmåga** än r0008.
- AI-delen innehåller nu tillräcklig funktionell detalj för att anknyta till kapitel 2 utan att återberätta generationsmodellen.
- Risk för överlapp med CAP-IT-04/06/07/08/09/10/12 hanterad genom att dessa berörs endast som förutsättningar och hänvisas till andra kapitel.
- Fortfarande ett arbetsutkast; faktakontroll och formellt kapitelgodkännande kvarstår.
