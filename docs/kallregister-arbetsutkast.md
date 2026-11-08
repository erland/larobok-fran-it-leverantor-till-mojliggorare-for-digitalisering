# Källregister – första verifierade urvalet (r0056)

**Status:** Redaktionellt arbetsregister för källverifiering, ännu inte en publicerad bibliografi. Granskningen utfördes 8 november 2026. Käll-ID:n följer projektets källpolicy. Länkarna går till officiella publikationer eller deras huvudansvariga organisationer. Registrering här betyder inte att alla påståenden i angivna kapitel är verifierade.

| ID | Primärkälla | Utgivningsår/version | Relevanta kapitel | Kontrollerat stöd och begränsning |
|---|---|---|---|---|
| K001 | NIST, *Secure Software Development Framework (SSDF) Version 1.1*, SP 800-218. https://csrc.nist.gov/pubs/sp/800/218/final | 2022 | 12, 13 | Dokumenterar allmänna säkerhetspraktiker i utvecklingslivscykeln. Inte garanti att kod blir säker eller en föreskriven teknikstack. |
| K002 | DORA, *Platform engineering*. https://dora.dev/capabilities/platform-engineering/ | Hämtad 2026-11-08 | 2, 3, 5, 13, 17 | Plattform som intern produkt med självbetjäning, automatisering och användarfokus. Bevisar inte bokens fyra generationer. |
| K003 | NIST, *AI RMF: Generative Artificial Intelligence Profile*, AI 600-1. https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence | 2024; webbsida uppdaterad 2026 | 2, 8, 12, 17 | Frivilligt, riskbaserat ramverk för generativ AI, utvärdering och styrning; inte ett generellt rättsligt krav. |
| K004 | OWASP GenAI Security Project, *Top 10 for Large Language Model Applications*, utgåva 2026. https://github.com/GenAI-Security-Project/GenAI-LLM-Top10 | 2026-08-04 | 8, 10, 12, 13 | Primär risköversikt för bl.a. prompt injection, informationsläckage, excessive agency och obunden förbrukning. Risklista, inte certifiering eller juridisk standard. Föregående 2025-utgåva är numera historisk. |
| K005 | Kubernetes Documentation, *Resource Quotas*. https://kubernetes.io/docs/concepts/policy/resource-quotas/ | Löpande dokumentation; kontrollerad 2026-11-08 | 14 | Bekräftar namespace-kvoter och begränsning av sammanlagd resursförbrukning. Kvoter löser inte alla isoleringsproblem eller extern API-belastning. |
| K006 | Kubernetes Documentation, *Multi-tenancy*. https://kubernetes.io/docs/concepts/security/multi-tenancy/ | Löpande dokumentation; kontrollerad 2026-11-08 | 14, 12 | Beskriver flerlagersisolering, noisy-neighbor-risk och begränsningar i enbart kvoter. Kubernetes är ett illustrativt teknikexempel, inte bokens föreskrivna plattform. |
| K007 | NIST, *Zero Trust Architecture*, SP 800-207. https://csrc.nist.gov/pubs/sp/800/207/final | 2020 | 9, 10, 12, 15 | Stöd för att nätverksplacering ensam inte ger implicit tillit; identitets- och åtkomstprövning behövs. Föreskriver inte att alla lösningar ska vara zero-trust-produkter. |
| K008 | OpenTelemetry, *Documentation*. https://opentelemetry.io/docs/ | Löpande dokumentation; kontrollerad 2026-11-08 | 14, 16 | Bekräftar begreppen loggar, mätvärden och distribuerade spårningar samt leverantörsneutral instrumentering. Ställer inte generella tjänstenivåkrav. |
| K009 | FinOps Foundation, *FinOps Principles*. https://www.finops.org/framework/principles/ | Löpande ramverk; kontrollerat 2026-11-08 | 3, 8, 13, 17 | Underbygger kostnadstransparens, gemensamt men decentraliserat kostnadsansvar och optimering efter verksamhetsvärde. Styr inte faktiska licensvillkor. |
| K010 | SLSA Framework, *Build Provenance*. https://github.com/slsa-framework/slsa/blob/main/spec/build-provenance.md | Löpande specifikation; kontrollerad 2026-11-08 | 13 | Proveniens beskriver var, när och hur en artefakt byggts. Proveniens är inte liktydigt med reproducerbar byggprocess eller säker programvara. |

## Källornas avsedda användning

Källorna ger **tekniskt och begreppsligt stöd** för delar av bokens rekommendationer. Bokens fyra generationer, tretton förmågor, tre former av G4-självständighet och risknivåer är **redaktionella analysmodeller**, inte innehåll som dessa källor definierar eller intygar. Konkreta organisationsexempel är konstruerade illustrationer.

Inga nya citat från källorna eller Kxxx-hänvisningar har förts in i läsarkapitlen i denna revision. Placering av källregister sist i den färdiga boken och källhänvisningar per påstående kräver ett separat beslut i publiceringsfasen.
