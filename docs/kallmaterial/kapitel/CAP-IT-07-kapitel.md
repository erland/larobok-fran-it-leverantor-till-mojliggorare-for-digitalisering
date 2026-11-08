# Identitet och tillit

*CAP-IT-07 · Faktaboksunderlag · version 2.0 – kritiskt granskad · 7 november 2026*

En handläggare loggar in i ett ärendesystem som i sin tur anropar flera mindre tjänster. Inloggningen fungerar. Ändå får handläggaren ibland felaktigt tillgång till ett ärende, medan ett integrationsflöde nekas åtkomst efter ett certifikatbyte. I en annan del av miljön använder flera tjänster samma tekniska konto. När ett av systemen ska avvecklas vågar ingen stänga kontot, eftersom ingen vet vilka andra system som är beroende av det.

Detta är en typisk utmaning i **generation 2**: applikationerna har blivit distribuerade snabbare än identitetshantering, tillitsrelationer och ansvarsfördelning har anpassats. Lösningen är inte alltid att köpa en ny identitetsplattform. Först behöver organisationen avgöra vilka grundläggande kontroller som saknas, vilka tjänster som har blivit onödigt svåra att förändra och vad som faktiskt behöver erbjudas gemensamt.

## Vad förmågan handlar om

**Identitet och tillit** är förmågan att etablera och hantera digitala identiteter för människor, tjänster och andra tekniska aktörer, samt att skapa och avsluta kontrollerade tillitsrelationer. Den omfattar bland annat inloggning, identitetskataloger, federation mellan identitetsdomäner, maskinidentitet, certifikat, hemligheter, privilegierad åtkomst och tekniskt stöd för auktorisationsbeslut.

Tre begrepp är viktiga. **Identifiering** handlar om att knyta en digital identitet till en aktör; tillförlitligheten i den kopplingen varierar och måste anpassas till risken. **Autentisering** handlar om att pröva att den som använder identiteten kan styrka sin rätt att göra det. **Auktorisation** handlar om att avgöra och verkställa vad aktören får göra med en viss resurs. **Delegering** betyder att någon får handla inom ett uttryckligt avgränsat mandat för en annan aktör. Dessa moment hänger ihop men är inte utbytbara. En person kan alltså vara korrekt inloggad men sakna rätt att läsa ett visst ärende. En AI-agent kan på motsvarande sätt ha en giltig teknisk identitet utan mandat att godkänna en betalning.

Förmågan ska erbjuda tekniskt stöd för sådana beslut men **inte överta verksamhetssystemens behörighetssemantik**. Vem som enligt verksamhetens regler får besluta i ett visst ärende behöver bestämmas nära den skyddade resursen. CAP-IT-12 Cybersäkerhet tillhandahåller kompletterande skydd, CAP-IT-13 nätverkskonnektivitet och CAP-IT-06 integrationernas kontrakt. De samverkar men ersätter inte varandras ansvar.

## När är förmågan relevant?

Nästan varje fleranvändarsystem och de flesta skyddade tjänsteintegrationer behöver någon form av identitets- och åtkomstkontroll. För öppna offentliga resurser kan åtkomsten däremot vara anonym, medan ändringar och administration fortfarande behöver skyddas. Men alla organisationer behöver inte en egen central produkt för varje delområde. Behovet styrs av antalet användare och tjänster, externa parter, skyddsvärd information, administrativa privilegier och hur ofta konton, arbetslaster och behörigheter ändras. En liten, väl avgränsad tjänst kan klara sig med en hanterad identitetstjänst och systemnära rättighetskontroller. Hundratals föränderliga tjänster gör standardisering och automatiserad livscykel betydligt viktigare.

Särskilda funktioner – exempelvis elektronisk signering eller myndighetsanslutning – bör bara prioriteras där verksamheten har faktiska sådana behov. **Att en funktion är kritisk när den används innebär inte att en gemensam, egenägd plattform är obligatorisk.**

## Kort tillbakablick: generation 1 och arvet in i generation 2

I en miljö med relativt få, sammanhållna system kunde identitetshanteringen ofta organiseras kring användarkonton i kataloger, systemlokala roller och centralt administrerade inloggningsmetoder. Driften visste vilka tekniska konton som användes i respektive applikation. Manuella ändringar kunde vara hanterbara om antalet system och förändringar var litet. För skyddsvärda system krävdes ändå väl fungerande autentisering och behörighetskontroll; de kraven uppstod inte först med mikrotjänster.

När samma verksamhetsfunktion delas upp i flera tjänster förändras antalet tillitsrelationer. En användares identitet kan behöva förmedlas mellan gränssnitt och API:er, medan tjänster måste identifiera varandra separat. Certifikat, token och tekniska hemligheter får egna livscykler. Ett gammalt arbetssätt där flera tjänster använder samma databaslösenord eller där avslut hanteras manuellt i varje system kan bli både riskfyllt och långsamt.

**Kvarvarande generationsarv** kan därför märkas som delade servicekonton, långlivade nycklar, manuella certifikatförnyelser, lokala behörighetslistor utan känd ägare eller avsaknad av en gemensam rutin för att avsluta tillgång. Detta är i första hand brister som behöver åtgärdas för att generation 2 ska fungera; de kräver inte automatiskt en övergång till generation 3.

## Generation 2 – identiteter över många tjänstegränser

### Vilket stöd behöver finnas?

För människor behövs en tillförlitlig inloggningskedja med riskanpassad autentisering och klara förutsättningar för federation. En tjänst som förlitar sig på en annan tjänsts autentiseringsresultat behöver kontrollera utfärdare, mottagare, giltighet och relevanta tillitsvillkor, inte bara att en token ser korrekt ut. Lokala applikationsbeslut om verksamhetsrättigheter ska fortfarande verkställas vid den skyddade resursen.

För tjänster behövs identifierbara tekniska aktörer. En integrerande tjänst bör inte använda en människas lösenord eller en delad teknisk identitet för hela systemlandskapet. Hemligheter och certifikat behöver ägare, skyddad förvaring, rotation och rutiner för återkallelse. Även administratörsbehörigheter behöver kunna granskas och tidsbegränsas där riskerna motiverar det.

Det måste också gå att hantera identitetslivscykeln över flera miljöer. När en person slutar, byter roll eller får ett avslutat uppdrag behöver organisationen veta vilka tillgångar som faktiskt påverkas. Att radera en katalogpost är inte tillräckligt om nedströms system behåller lokala behörigheter, giltiga token eller aktiva sessioner. Här behövs både tekniska mekanismer och verksamhetsägare som kan avgöra vilka rättigheter som ska dras tillbaka.

NIST SP 800-63-4 ger vägledning för identitetssäkring, autentisering och federation för mänskliga användare. Den ska inte användas som om den ensam reglerade maskinidentiteter eller AI-agenter. För sådana risker är bland annat OWASP:s vägledning om icke-mänskliga identiteter relevant. För OAuth-baserade integrationsflöden ger RFC 9700 särskild säkerhetsvägledning; bland annat behöver man kontrollera tokenens avsedda mottagare och skydda mot återspelning.

### Ansvar och vanliga fallgropar

IAM-specialister kan äga identitetskatalog, federation och tekniska tillitsmekanismer. Applikationsteamet ansvarar för att använda mekanismerna korrekt, kontrollera token och verkställa resursnära åtkomstbeslut. Verksamhetens beslutsägare avgör vilka roller och uppdrag som ger rätt att utföra en verksamhetsåtgärd. Säkerhetsfunktionen fastställer principer och granskar risker och undantag.

En fallgrop är att beskriva central inloggning som ett färdigt behörighetssystem. En annan är att lägga alla detaljerade verksamhetsregler i en gemensam IAM-produkt som saknar information om ärendets tillstånd eller känslighet. En tredje är att specialister måste godkänna varje liten teknisk kontoförändring eftersom grundläggande livscykelmekanismer saknas.

### Indikatorer på att förmågan ger tillräckligt stöd

- En person som avslutar ett uppdrag förlorar relevanta rättigheter i de berörda systemen inom riskbaserat fastställda tidsmål. Provet skiljer mellan spärr av nya inloggningar, återkallelse av åtkomst i nedströms system och hantering av redan utfärdade token eller sessioner. Avslut i katalogen innebär inte automatiskt omedelbar ogiltighet överallt.
- En giltigt autentiserad användare nekas en skyddad verksamhetsåtgärd när den saknar mandat, även vid direkt API-anrop utan användargränssnitt.
- En tjänst kan inte utge sig för att vara en annan genom ett delat eller felaktigt tekniskt konto. Kritiska tekniska identiteter har ägare och avvecklingsrutin.
- Certifikat och hemligheter kan förnyas eller roteras utan okända beroenden eller oplanerade längre avbrott.
- Privilegierad nödåtkomst är möjlig men tillräckligt begränsad, spårbar och faktiskt övad.

### Indikatorer på olämplig teknik eller plattform

**Funktion:** Plattformen kan inte hantera nödvändiga federationsprotokoll, säker autentisering eller separata identiteter för tjänster. Testa ett representativt integrationsflöde innan slutsatsen blir produktbyte.

**Säkerhet och livscykel:** Det saknas stöd för rimlig rotation, återkallelse eller uppdateringar, eller produkten är utanför leverantörens support. Kontrollera om bristen ligger i produkten eller i sättet den konfigurerats.

**Automatiserbarhet:** Konton och certifikat måste skapas och tas bort manuellt även i frekventa standardfall. Pröva befintliga API:er, federation eller kopplingar till identitetskällor innan ny plattform väljs.

**Kostnad och skala:** Licenser, manuella identitetsärenden eller komplexa katalogkopplingar växer snabbare än antalet användare och tjänster. Jämför faktisk total kostnad och ledtid, inte bara pris per användare.

**Inlåsning:** Identitetsdata, roller eller tillitspolicyer kan inte exporteras och migreras på ett kontrollerat sätt. En planerad migrering bör också omfatta hur beroende applikationer fortsätter fungera.

Inget av dessa tecken är på egen hand ett skäl till ett generellt teknikbyte. Börja med att undersöka om felet gäller **produkt, konfiguration, integration, arkitektur eller ansvar**.

### Två förbättringsspår i generation 2

**Spår A – Få generation 2 att fungera säkert.** Inventera tekniska identiteter och deras ägare, avskaffa delade privilegier där de skapar risk, säkra tokenvalidering och inför fungerande kontoavslut och nyckelrotation. Prova de mest kritiska flödena. Det är grundläggande arbete oavsett långsiktig plattformsstrategi.

**Spår B – Förbered generation 3.** Identifiera återkommande identitets- och tillitsbeställningar: ny applikation, tjänstekonto, certifikat, accesspaket eller extern förbindelse. Om normalfallen är många och likartade finns skäl att göra dem till förvaltade, automatiserade erbjudanden. Det arbetet bör bygga på en fungerande säkerhetsbas, men delar av A och B kan genomföras tillsammans.

### Ett diagnostiskt prov: vad är fel och vad bör ändras?

Välj ett konkret fall: en konsult lämnar ett uppdrag samtidigt som en tjänst byter certifikat. Följ förändringen genom identitetskälla, federation, katalog, verksamhetsapplikationer och tekniska tillitsrelationer. Kontrollera om en tidigare behörig aktör fortfarande kan nå ett skyddat API, om aktiva sessioner består och om andra tjänster oväntat påverkas av certifikatbytet.

Om felaktig åtkomst kvarstår är det en **grundläggande kontrollbrist** som måste rättas i generation 2. Om samma välförstådda livscykelåtgärd däremot upprepas manuellt i många system, trots att processen fungerar korrekt, kan den **standardiseras som plattformstjänst**. Om produktens protokoll eller livscykelgränssnitt hindrar båda åtgärderna finns skäl att pröva komplettering eller teknikbyte.

## Övergången från generation 2 till 3

I generation 3 ändras inte kravet att kunna identifiera och auktorisera aktörer. Det som förändras är **hur tilliten levereras**. En utvecklare eller plattformskonsument ska kunna använda en godkänd identitetsprofil med förutsägbara säkerhetsegenskaper utan att ett specialistteam behöver handlägga varje normalfall. Det kräver standardiserade gränssnitt, förvaltat produktansvar, versionshantering, säkerhetsgränser och en fungerande livscykel från onboarding till avveckling.

En möjlig startpunkt är automatisk identitet och certifikat för en ny workload. Nästa steg kan vara självbetjänad applikationsregistrering och standardiserad federation. Organisationen bör dock undvika att centralisera varje domänspecifik auktorisationsregel; plattformen ger verktyg och tekniska kontroller, medan den skyddade resursen verkställer den verksamhetsmässiga rätten.

**Indikatorer som motiverar förflyttningen:** ett stort antal upprepade standardbeställningar, långa väntetider för ny tjänst, återkommande fel vid kontoavslut och osäkra lokala lösningar därför att gemensamt stöd är för svårt att använda. Ett kontoavslut som inte fungerar är dock först och främst en säkerhetsbrist att rätta; det blir ett motiv för en gemensam plattform när det upprepas över många konsumenter och kan lösas med en förvaltad tjänst. Men om underliggande tillitsrelationer ännu inte är begripliga eller om ingen kan ta långsiktigt produktansvar är det för tidigt att kalla en portal för självbetjäning.

## Generation 3 – identitet som förvaltad plattformstjänst

### Vilket stöd behöver erbjudas?

Standardprofiler för mänsklig inloggning, tjänsteidentitet, certifikat, hemligheter och privilegierad åtkomst ska kunna konsumeras via dokumenterade gränssnitt, API:er eller återanvändbara leveransmallar. Vanliga livscykelåtgärder – etablering, ändring, rotation, avveckling och återhämtning – ska inte kräva upprepade manuella specialistärenden.

Tjänsterna behöver också vara begripliga för konsumenterna: vem får begära en identitet, vilka rättigheter får den, hur ändras de och vad händer när applikationen avvecklas? Undantag och högre risk måste hanteras kontrollerat utan att bromsa alla enkla normalfall. Plattformsteamet ansvarar för användbara tekniska produkter, medan applikations- och verksamhetsteam fortsatt äger sina behörighetsbeslut.

### Vanliga fallgropar, indikatorer och teknikvarningar

En välpolerad IAM-portal kan dölja manuella ärendeköer. Då har man automatiserat beställningsgränssnittet men inte livscykeln. Ett annat problem är att produktteamet försöker göra alla verksamhetsbehörigheter centrala och därmed skapar en ny flaskhals. Gemensam identitetstjänst är heller inte lika med ett enda sårbart system: tjänsten måste ha design för tillgänglighet, incidenthantering och rimliga degraderingslägen.

**Fungerande stöd** märks när ett nytt utvecklingsteam kan etablera godkänd autentisering, tjänsteidentitet och certifikathantering genom standardvägar. En kontrollerad testavveckling visar att rättigheter, hemligheter och tillitsrelationer försvinner enligt angivna regler. Ändringar är spårbara och undantag går att följa upp.

**Olämpliga plattformsval** märks om produkten inte tillåter automatiserad rotation, saknar begripliga eller stabila integrationskontrakt, medför oacceptabelt många manuella uppgifter eller kräver att alla applikationer anpassas till en central specialmodell för auktorisation. Men ett användningsproblem kan lika gärna bero på svag intern produktledning som på produkten.

## Övergången från generation 3 till 4

När verksamheten kan skapa fler lösningar och AI-assisterade arbetsflöden ökar antalet aktörer som behöver tillgång till verktyg, information och andra system. Det räcker inte att en agent 'agerar åt' en inloggad användare. Organisationen behöver uttryckligen skilja mellan **användare, agent, körning, verktyg och den skyddade resursen**.

En agentkörning behöver kunna identifieras och kopplas till ansvarig lösning och uppdragsgivare. Det kan ske med en separat teknisk identitet, en särskild delegation eller andra verifierbara attribut; en helt separat användarkontotyp är inte alltid nödvändig. Avgörande är ett avgränsat och verkställbart mandat: tillåtna åtgärder, resursomfattning, ändamål och tidsbegränsning. Högriskåtgärder kan kräva ett nytt mänskligt godkännande även om agenten redan är autentiserad. Återkallelse måste ta hänsyn till token- och sessionstider; att stänga en central agentprocess kan inte ångra handlingar som redan utförts.

**Beredskap** finns först när organisationen vet vem som äger en agentlösning, var behörigheter verkställs, hur tilliten avvecklas och hur incidenter undersöks. Denna generation är framåtblickande och ska inte framställas som en enda etablerad standardarkitektur.

## Generation 4 – verksamhetsnära och AI-assisterad användning

### Vilket stöd behöver finnas?

Identitet och tillit behöver följa lösningar som skapas och förändras snabbt, utan att skyddet urholkas. Standardprofiler kan stödja tidsbegränsade arbetsflöden, identifierbara agentkörningar, avgränsad delegering, kortlivade behörighetsbevis och resursnära policykontroller vid känsliga verktygsanrop. Lösningar med låg risk kan få mer automatiserad tilldelning, medan åtgärder med stora ekonomiska eller rättsliga effekter kan kräva tydlig mänsklig kontroll.

### Vanliga fallgropar och indikatorer

Den viktigaste fallgropen är att agenten får använda den mänskliga uppdragsgivarens breda, permanenta rättigheter utan särskild prövning av åtgärden. Andra risker är att ett verktygsanrop betraktas som tillåtet bara för att agenten är inloggad, eller att åtkomster ligger kvar efter avslutat uppdrag. Att kräva fullständig mänsklig attest för varje ofarligt anrop kan samtidigt göra lösningen oanvändbar och driva fram osäkra genvägar.

**Indikator på tillräckligt stöd:** Ett testat agentflöde kan läsa men inte ändra en skyddad post när dess mandat är läsande; ett känsligt skriv- eller beslutsscenario kräver särskilt godkännande. När tidsfönstret går ut nekas nya åtkomstförsök inom dokumenterad gräns. Testet omfattar också aktiva sessioner och giltiga token som kan leva vidare. Spårbarheten ska visa ansvarig uppdragsgivare, identifierbar körning eller teknisk aktör, tillåtet mandat och berörd resurs – utan att förutsätta att alla interna modellsteg kan rekonstrueras.

**Indikator på olämplig teknik:** De enda tillgängliga identitetsmodellerna är permanenta användarkonton eller obegränsade API-nycklar, det saknas möjlighet att begränsa delegation per verktyg eller körning, eller driftteamet kan inte återkalla tillit utan långvarigt avbrott för andra konsumenter.

### Beredskap och begränsningar i generation 4

Verksamhetsnära AI-lösningar gör inte varje identitetsfunktion till en ny produktkategori. Ofta kan befintlig federation, workloadidentitet och resursnära auktorisation användas även här. Det nya behovet är att tydligt knyta behörigheter till en viss uppgift och att kunna avgränsa handlingsutrymmet när lösningen planerar och använder verktyg självständigt. Ett känsligt beslut ska kontrolleras där det verkställs, inte bara genom instruktioner till AI-modellen.

Att återkalla ett mandat hindrar inte automatiskt ett redan genomfört externt anrop eller en verkställd verksamhetsåtgärd. Därför behöver identitetskontroller samverka med processens attest, säkerhetsloggning, transaktionskontroller och incidenthantering. Dessa ligger delvis i andra förmågor.

## Ett genomgående exempel: ett ärendeflöde

I generation 2 loggar en handläggare in via federation och öppnar ett ärende. Klienten får inte själv bestämma ärendebehörighet; tjänsten som äger ärendet måste kontrollera handläggarens mandat. Samtidigt identifierar ett separat API sig med en egen workloadidentitet när det hämtar uppgifter från en annan tjänst. När en handläggare byter roll ska både centralt administrerad och systemnära tillgång uppdateras.

I generation 3 är samma säkerhetsprinciper möjliga att använda genom gemensamma mallar: inloggningsintegration, arbetslastidentitet, certifikat och hemligheter etableras med dokumenterat stöd. Ett nytt team behöver inte uppfinna dessa mekanismer på nytt.

I generation 4 kan en AI-assistent sammanställa ärendeunderlag, men åtkomsten kontrolleras vid varje skyddad resurs så att den bara kan läsa uppgifter inom sitt mandat. Om assistenten ska fatta eller expediera ett beslut krävs en separat, kontrollerad tillåtelse och ibland mänsklig attest. Tillit för den tillfälliga agentkörningen ska avvecklas när uppdraget är avslutat.

## Praktisk bedömning: förbättra, komplettera eller byta?

Följ ett verkligt identitetsflöde från att en användare eller tjänst skapas, via autentisering och rättighetskontroll, till ändring och avveckling. Genomför sedan ett negativt prov där en korrekt autentiserad aktör saknar den begärda rättigheten. Gör ett motsvarande test för en teknisk identitet och ett tidsbegränsat mandat. Mät inte bara om inloggningen lyckas, utan även hur fort felaktig åtkomst försvinner och hur mycket handarbete som krävs.

**Behåll** tekniken när behov och risk uppfylls. **Komplettera** när en avgränsad brist kan åtgärdas med integration eller konfiguration. **Ändra användningen** när ansvar eller processer orsakar problemen. **Ersätt** när grundläggande begränsningar omöjliggör rimlig säkerhet, livscykel eller skalbarhet. Först därefter finns ett underlag att avgöra hur stor del av behovet som bör lösas genom generation 3:s plattformstjänster.

## Plattformstjänster som kan stödja förmågan

Den konceptuella källmodellen innehåller tio stödjande plattformstjänster över fyra plattformar. De är tekniska byggblock, **inte tio obligatoriska produktinköp**. Auktorisationsbeslut kan fortsatt ligga nära resursen; en gemensam policytjänst är motiverad först när återanvändning och regelkomplexitet ger tydlig nytta. Elektronisk signering och extern myndighetsanslutning är specialiserade behov, inte generella förutsättningar för att ha god identitetshantering.

| Plattformstjänst | Typisk roll | När särskilt relevant |
|---|---|---|
| PLS-025 – Autentisering och federation | Autentisering, federation och tokenbaserad identitetsförmedling | System där människor behöver identifieras och autentiseras; anonym läsåtkomst är ett möjligt undantag |
| PLS-085 – Identitetskatalog och katalogtjänst | Teknikneutral katalog av identiteter, attribut, grupper och katalogrelationer | Anställda, konsulter och andra identitetskategorier |
| PLS-026 – Identity Governance och entitlement-livscykel | Identitetslivscykel, access requests, entitlements och periodiska access reviews | Organisationer med flera system och livscykel-/revisionkrav |
| PLS-030 – Auktorisationsbeslut och policyexekvering | Tekniskt beslutstöd för relations-, attribut- eller policybaserad auktorisation utan domänägarskap | System med komplexa eller återanvändbara åtkomstpolicyer |
| PLS-063 – Privileged Access Management | Privilegierad åtkomst med JIT/JEA, elevation, skyddade sessioner och administrationslivscykel | Administratörer, operatörer och privilegierade automationsflöden |
| PLS-027 – Service- och workloadidentitet | Tekniska identiteter och kortlivade credentials för workloads och komponenter | Distribuerade tjänster, pipelines, maskiner och AI-agenter |
| PLS-028 – PKI och certifikattjänst | Certifikatutfärdande, certifikatlivscykel och trust anchors | TLS, mTLS, signerings- och certifikatbaserad tillit |
| PLS-029 – Secrets Management | Säker lagring, distribution och rotation av tekniska hemligheter och credentials | System som behöver lösenord, token, API-nycklar eller andra hemligheter |
| PLS-068 – Elektronisk signering, stämpel och tidsstämpling | Elektroniska underskrifter, stämplar och betrodda tidsstämplar med spårbar tillitskedja | Processer som kräver signering, stämpling eller tillförlitlig tidsbevisning |
| PLS-079 – Säker extern system- och myndighetsanslutning | Kontrollerad extern onboarding, trust, konnektivitet och informationsutbyte utan att ersätta bakomliggande tekniker | System med externa samarbetspartner, myndighetsutbyten eller B2B |


### Prövning av tjänsterna

Tjänsternas prioritet måste alltid vägas mot den egna miljön. Följande prov illustrerar vad ett fungerande erbjudande bör kunna visa, utan att föreskriva en viss produkt:

**PLS-025 – Autentisering och federation.** Kontrollera att rätt identitet etableras även vid byte av klient, att stark autentisering används enligt risk och att spärr återverkar inom definierad tid. Simulera spärrad användare, ogiltig utfärdare och felaktig tokenmottagare (audience). Mät separat hur spärr slår igenom för nya anrop respektive aktiva sessioner utan att orelaterade användare påverkas.

**PLS-085 – Identitetskatalog och katalogtjänst.** Granska hur anställningsförändringar når katalog och konsumenter och hur felaktiga attribut korrigeras. Ändra en persons organisatoriska tillhörighet eller avsluta ett uppdrag och kontrollera fördröjning, felhantering och kvarvarande åtkomst. Katalogsynkronisering är inte samma sak som uppdaterat verksamhetsmandat.

**PLS-026 – Identity Governance och entitlement-livscykel.** Mät tiden från avslutat uppdrag till borttagen åtkomst och om resurser har ansvarig beslutsägare. Avsluta ett uppdrag och kontrollera kvarvarande rättigheter i representativa nedströms system. Skilj centralt administrerade behörigheter från lokala domänbeslut och dokumentera undantag.

**PLS-030 – Auktorisationsbeslut och policyexekvering.** Testa att en korrekt autentiserad användare ändå nekas en åtgärd som saknar verksamhetsmandat. Kör positiva och negativa rättighetstester, även direkt mot API utan användargränssnitt.

**PLS-063 – Privileged Access Management.** Prova nödåtkomst och att varje privilegierad åtgärd går att härleda till ansvarig aktör. Ge tillfällig adminåtkomst, kontrollera utgångstid och verifiera loggning samt break-glass-procedur.

**PLS-027 – Service- och workloadidentitet.** Kontrollera om varje produktionsworkload har egen identitet och att fel tjänst inte kan utge sig för en annan. Starta, stoppa och återskapa en workload; fel identitet ska nekas och gamla behörighetsbevis sluta accepteras enligt dokumenterad giltighets- och återkallelsemodell. Kontrollera även identitetsåtskillnad mellan test och produktion.

**PLS-028 – PKI och certifikattjänst.** Prova förnyelse och hantering av komprometterad utfärdare innan certifikat löper ut. Utför förnyelse och en kontrollerad komprometteringsövning; mät hur förtroende kan begränsas eller avvecklas hos faktiska konsumenter. Certifikatåterkallelse kan ha fördröjning eller sakna verkan hos vissa klienter; testa verkligt beteende.

**PLS-029 – Secrets Management.** Sök efter hårdkodade hemligheter och testa rotation utan omfattande driftsstopp. Rotera en nyckel i ett testflöde; gammal nyckel ska sluta fungera inom definierat fönster och nyckeln får inte loggas.

**PLS-068 – Elektronisk signering, stämpel och tidsstämpling.** Avgör först om verksamheten faktiskt behöver rättsligt betydelsefull signering och vilken bevisning som ska bevaras. Prova signering, signaturverifikation efter tid och hantering av återkallat certifikat; kontrollera regelverk för användningsfall.

**PLS-079 – Säker extern system- och myndighetsanslutning.** Dokumentera kontaktpunkt, motpartsidentitet, certifikat och ägare samt hur tillit avslutas. Byt extern parts certifikat, neka obehörig motpart och kontrollera att avslutad anslutning inte längre fungerar.

## Källor och avgränsningar

Detta kapitel bygger på *Från systemdrift till digital självständighet*, *Förmågeöversikt – tekniska IT-förmågor* (CAP-IT-07) och *Plattformsöversikt – konceptuella plattformar* (baseline v1.1). Namn, ID och modellgränser hämtas därifrån. De fyra generationernas tillämpning, teknikvarningar, prioriteringar och tester är **arkitekturbedömningar**, inte direkt citerade krav eller uppgifter om en specifik organisation.

Kompletterande referenser: NIST SP 800-63-4 (2025) om mänsklig digital identitet, NIST SP 800-207 (2020) om Zero Trust, RFC 9700 (2025) om OAuth 2.0-säkerhet och OWASP Non-Human Identities Top 10 (2025) om risker med tekniska identiteter. Ingen av dessa källor definierar denna boks generationsmodell. Begreppet agentidentitet används som en framtidsinriktad arkitekturprincip, inte som ett påstående om en allmänt fastlagd standard.
