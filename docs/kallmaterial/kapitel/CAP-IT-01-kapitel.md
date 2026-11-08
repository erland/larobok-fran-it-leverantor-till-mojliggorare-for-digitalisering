# CAP-IT-01 – Interaktion, presentation och kanaler

*Faktabokskapitel, kritisk granskad version 2.0 · 7 november 2026*

## Vad handlar förmågan om?

Det är i mötet med användaren som ett IT-stöd till sist måste fungera. En person ska kunna förstå vad som förväntas, hitta rätt information, lämna uppgifter, upptäcka fel, följa ett ärende och få veta vad som har hänt. Det gäller oavsett om mötet sker i en webbläsare, en mobiltelefon, en fältapplikation eller en annan digital kanal. En tekniskt fungerande backend är ingen garanti för att den sammanhängande användarupplevelsen fungerar.

**Interaktion, presentation och kanaler** är förmågan att åstadkomma användbara, tillgängliga, säkra och förändringsbara digitala möten. I förmågan ingår utformning och teknikstöd för gränssnitt och kanaler, men inte ett automatiskt övertagande av verksamhetsregler, identitetskontroller, informationsägarskap eller processernas beslut. Det som syns på skärmen har ofta många ansvariga bakom sig.

Detta kapitel beskriver hur förmågan utvecklas genom fyra generationer av IT. Generationerna är analysmodeller, inte produktgenerationer eller en universell mognadstrappa. Särskilt generation 4 är ett möjligt framtidsscenario. Tyngdpunkten ligger på **generation 2**, där flera självständiga tjänster och team måste leverera en sammanhängande upplevelse. Frågan är dels vad som behöver fungera redan där, dels när återkommande behov motiverar gemensamma plattformstjänster i generation 3.

Ett genomgående exempel är en digital ansökan som startas på webben, kompletteras på mobilen och handläggs i ett annat system. Inmatning, autentisering, ärendestatus, notifieringar och dokument är tekniskt åtskilda. För användaren är det ändå **en** resa.

## Kort tillbakablick: generation 1

När IT-stödet var mer sammanhållet utvecklades gränssnitt, verksamhetslogik och data ofta tillsammans. Ett team kunde förändra en skärm och dess bakomliggande logik inom samma release. Olika system hade skilda navigationer, begrepp och komponentbibliotek. Kvalitet kontrollerades ofta manuellt och beroende av lokala specialister.

Det var inte nödvändigtvis ett dåligt tekniskt utgångsläge. En välgjord sammanhållen applikation kunde ge god tillgänglighet, robust inmatning och begriplig navigation. Grundläggande användbarhet och säkerhet är inte nya krav som börjar gälla först i generation 3. Men när systemen blev fler växte risken att varje system behövde lösa samma problem för sig.

**Förflyttningen G1→G2** innebar framför allt att gränssnitt och kanaler skulle samverka med många fler bakomliggande tjänster. Användarresan fick fler versioner, nätverksberoenden och självständiga leveransrytmer. Det gav större förändringsfrihet men gjorde konsekvens, felhantering och helhetstest svårare.

## Generation 2 – många tjänster, en användarresa

### När blir förmågan viktig?

En medborgare fyller i en ansökan. Formuläret sparas i en tjänst, bilagor hanteras av en annan, status kommer från ärendehantering och kvittens skickas via en notifieringstjänst. Allt kan vara korrekt ur de enskilda teamens perspektiv och ändå bli fel ur användarens: en knapp fastnar i laddningsläge, tidigare ifyllda uppgifter försvinner eller ett e-postmeddelande säger att ärendet är avslutat fast det bara är tekniskt mottaget.

Detta är inte i första hand ett problem med färgval eller ramverk. Det är ett **samordningsproblem med användaren som måttstock**. Ett team behöver äga den övergripande resan, samtidigt som ägare för enskilda tjänster, informationsinnehåll och behörigheter fortfarande kan vara olika.

I generation 2 behöver organisationen därför kunna beskriva en hel användarresa: från inloggning och inmatning via väntelägen och fel till mottagningsbekräftelse och uppföljning. Det ska vara möjligt att avgöra när något gått fel, vems ansvar det är och vilken hjälp användaren får. En gemensam designmanual räcker inte om gränssnitten har olika verkligt beteende.

### Tillgänglighet är en del av funktionen

En användare kan inte genomföra ett steg om fokus hamnar bakom en dialog, om felmeddelanden bara uttrycks i färg eller om den enda möjliga handlingen kräver precisionspekning. Sådana problem måste hanteras där de uppstår och provas i den verkliga användarresan. Semantisk HTML, synlig fokusmarkering, korrekt tangentbordsordning, textalternativ och begriplig felåterkoppling är centrala utgångspunkter för webbgränssnitt.

WCAG 2.2 ger teknikneutrala, testbara framgångskriterier och WAI-ARIA Authoring Practices ger mönster för exempelvis dialoger och tangentbordsnavigering. Automatisk testning är viktig men räcker inte ensam: verkliga användare, tangentbord, skärmläsare, förstoring, olika skärmstorlekar och begripliga texter behöver också prövas. Exakt vilket krav som gäller rättsligt beror på verksamhet, jurisdiktion och tjänst; ett standarddokument utgör inte ensamt en juridisk bedömning.

En central komponent som en gång varit tillgänglig garanterar inte att en hel applikation är det. Användningen kan introducera felaktiga etiketter, dålig fokusordning eller otydlig information. Plattformen kan erbjuda goda byggblock; produktteamet måste säkerställa resultatet.

### Webb, native mobil och specialiserade klienter kräver olika prov

Ett webbgränssnitt kan bedömas med WCAG 2.2 som huvudsaklig teknisk referens. För native mobilapplikationer och specialiserad programvara behövs även kontroll av den aktuella plattformens tillgänglighetsfunktioner: exempelvis VoiceOver eller TalkBack, systemets textstorlek och zoom, dynamisk layout, riktiga tillgänglighetsetiketter och stöd för alternativa inmatningssätt. W3C:s *WCAG2ICT* ger vägledning för att tillämpa WCAG-principer på icke-webbaserad programvara, men är en informativ vägledning, inte ett separat bindande regelverk. En specialiserad fältterminal kan dessutom ha fysisk inmatning, särskilda arbetssituationer och hjälpmedelsbegränsningar som inte framgår av ett vanligt webbläsartest.

Prova alltså samma väsentliga verksamhetsuppgift med de hjälpmedel och enheter som faktiskt används. Dokumentera vilka kontroller som delas mellan kanalerna och vilka som kräver egna prov. Det vore missvisande att använda en lyckad webbtillgänglighetsgranskning som bevis för att även en fristående native-app är tillgänglig. Juridisk tillämplighet bedöms separat.

### Kanalsamordning kräver mer än samma utseende

En konsekvent digital tjänst behöver gemensamma begrepp för ärenden, fel, status och tillåtna handlingar. Men likadana knappar på två skärmar innebär inte att samma affärshändelse har genomförts. Användaren ska kunna se om uppgifter endast är lokalt sparade, mottagna av en tjänst eller faktiskt registrerade i verksamhetssystemet. Ett kvitto från en notifieringskanal är inte ett bevis på att processens beslut är fattat.

Även trygg sessionshantering behöver utformas sammanhängande: vad händer när sessionen går ut mitt i ett formulär, när nätet bryts eller när användaren växlar enhet? Inloggning och åtkomstregler hör huvudsakligen till identitets- och säkerhetsförmågorna, men interaktionen måste förklara och hantera deras tillstånd utan att vilseleda användaren.

### Ett diagnostiskt exempel: en ansökan i tre kanaler

Anta att en ansökan påbörjas i webben, kompletteras via en fältapp och följs upp genom ett meddelande. Vid en intermittent anslutning kan fältappen visa *sparat*, trots att data ännu inte synkroniserats. När anslutningen återkommer har handläggaren redan uppdaterat samma uppgift. Därefter skickas en avisering byggd på äldre status.

Börja med att identifiera det faktiska användarutfallet: vilka uppgifter såg användaren, vilka ändrades i vilken kanal, vad var lokalt sparat och vad var bekräftat av systemet? Spåra sedan kontrakt, versionsstöd, konfliktregler, notifieringshändelse och användargränssnittets återkoppling. Gör om provet med avbruten anslutning och två konkurrerande ändringar. Om applikationen har tveksamma konfliktregler hjälper varken ett nytt designbibliotek eller en ny synkplattform utan vidare.

Detta exempel skiljer också mellan *funktion som måste fungera* och *gemensam tjänst som kan behövas*. Konsekvent återkoppling och säker informationshantering behövs redan i generation 2. En gemensam mobil synkplattform kan bli värdefull när flera appar behöver samma komplexa funktionalitet, men inte om det bara finns en liten lösning med ett hanterbart lokalt behov.

### Offline är ett tillstånd, inte en försäkran om synkronisering

För fältarbete måste gränssnittet kunna skilja mellan *endast lagrat på enheten*, *väntar på överföring*, *mottaget av servern*, *avvisat* och *konflikt som måste lösas*. Varken webbläsare eller mobiloperativsystem garanterar att bakgrundssynk körs inom en viss tid; vissa miljöer saknar motsvarande stöd. En kö som ligger kvar när appen stängs behöver därför kunna återupptas vid nästa säkra tillfälle och visa ett begripligt läge för användaren.

En delad, tappad eller utbytt fältenhet skapar andra problem. Vem kan läsa utkastet? Vad händer när en anställd loggar ut, enheten byter ägare eller en token blir ogiltig? Krypterad lagring kan minska exponeringen men ersätter inte dataminimering, lämplig lokal lagringstid, ny autentisering, behörighetskontroll vid återanslutning och en realistisk metod för spärrning eller radering där plattformen faktiskt stödjer det. Redan kopierade uppgifter kan inte alltid återkallas. För särskilt känsliga åtgärder kan systemet behöva förhindra offlineverkställande helt.

### Två skilda förbättringsspår i generation 2

**Spår A – åtgärda generationsarvet.** Kartlägg kritiska användarresor, gemensamma begrepp, fel- och väntelägen, tillgänglighet, API-kontrakt, säkerhetsgränser och ansvar. Testa användarens mål över flera tjänster. Dessa brister behöver hanteras oberoende av om en ny plattform ska införas.

**Spår B – undersök behovet av gemensamt stöd.** Mät hur ofta team bygger samma formulärkomponent, återimplementerar inloggningsflöden, löser liknande notifieringsproblem eller skapar egna offlineprotokoll. Mät även kostnaden för att uppgradera, stödja och avveckla dessa lösningar. Återkommande, likartade problem är starkare motiv för en gemensam tjänst än ett önskemål om likformighet i sig.

Tecken på fungerande G2 är bland annat att användaren kan slutföra centrala uppgifter även vid hanterbara fel, att brutna resor upptäcks, att fokus och status är begripliga och att teamen kan ändra sina respektive delar utan oförutsedda kanalbrott. Tecken på teknikproblem är däremot exempelvis ett komponentbibliotek vars kontroll inte kan göras tillgänglig, en formulärmotor som inte klarar erforderliga tillstånd eller en offlinefunktion utan stöd för datakonflikter. Innan en produkt döms ut bör det undersökas om orsaken ligger i felaktig användning, konfiguration, integrationskontrakt eller otydligt ansvar.

## Generation 3 – förvaltade kanalbyggblock som interna produkter

I generation 3 blir det möjligt att erbjuda vanliga kanalbehov som återanvändbara, dokumenterade och underhållna plattformstjänster. Exempel är designsystem, standardiserad webbgrund, formulärstöd och notifieringsdistribution. Karttjänster, medieströmning och offline-synkronisering blir aktuella när verksamhetens behov och skala motiverar dem; de krävs inte bara för att en organisation går vidare till generation 3.

Det avgörande är inte att det finns ett gemensamt bibliotek eller en portal. Ett fungerande erbjudande behöver installations- och införandestöd, kända versioner, kompatibilitetslöften, testsviter, säkerhetsuppdateringar, förändringsinformation, support och en väg bort från äldre versioner. Nyttan för konsumerande team behöver mätas: kan de införa en förbättring utan att återimplementera samma lösning? Kan ett säkerhets- eller tillgänglighetsfel rättas i rimlig tid i många produkter? Kan tjänsten avvecklas utan att osynliga beroenden lever kvar?

### Plattformsansvar och produktansvar måste hållas isär

Plattformsteamet kan äga en knappkomponents teknik, tillgänglighetsmönster och versionslivscykel. Det innebär inte att plattformsteamet äger vilken knapp som ska finnas i ett verksamhetsflöde eller vad ett tryck ska betyda. Motsvarande kan en formulärplattform erbjuda säker fälthantering, men verksamheten behöver äga vilka uppgifter som får efterfrågas och vilken giltighet som krävs.

Denna skillnad skyddar mot två motsatta problem: att varje produktteam tvingas bygga allt från början och att en central plattform blir en flaskhals för varje användarupplevelse. En gemensam tjänst behöver stödja motiverade variationer och tydliga undantag, annars riskerar den att skapa egna parallella lösningar.

### Uppgraderingar måste fungera hos konsumerande produkter

En uppdatering i ett centralt komponentpaket är inte samma sak som en uppdatering hos alla produkter som använder det. Plattformen behöver publicera påverkan, stödda versioner, migreringsvägar, säkerhets- och tillgänglighetsrättningar samt datum då äldre varianter upphör att stödjas. Konsumerande team måste ha möjlighet att prova kritiska flöden före införande. Kräv särskild analys när en uppgradering ändrar formulärdata, felmeddelandets betydelse, interaktionsmönster eller integritetshantering; ett automatiskt beroendebyte kan då inte antas vara säkert.

Ett bra plattformsprov är att låta två olika produkter uppgradera samma komponent, behålla ett verkligt pågående användarflöde och därefter avveckla den äldre versionen utan förlorad funktion. Mät inte enbart hur snabbt det nya paketet kan publiceras, utan hur lång tid det tar innan konsumenterna faktiskt kan använda rättningen.

### Hur mäter man att plattformen fungerar?

Skilj mellan tre slags mått: **användarutfall** (andel som klarar uppgiften, tid till slutförd uppgift, återhämtning efter fel och användarens förståelse av status), **kvalitet** (observerade tillgänglighetshinder, förlorade utkast och felaktiga bekräftelser) och **plattformseffekt** (ledtid och kostnad för införande och uppgradering). Mät för relevanta användargrupper, enheter och hjälpmedel; jämför med utgångsläget och var uppmärksam på att hög genomförandegrad kan dölja att vissa användare inte kan genomföra uppgiften alls.

Mät bland annat tid från nytt projekt till fungerande och tillgänglig första vy, andel produkter som kan uppgradera en delad komponent utan handpåläggning, tid från rapporterad tillgänglighetsbrist till åtgärd hos konsumenterna, hur ofta formulär kan förändras utan dubbla implementationer och om supportärenden återkommer trots standardlösningen. Bedöm det i relation till plattformens kostnad, inte bara antalet installationer.

**Självbetjäning betyder också förändring och avveckling.** En tjänst som gör det lätt att skapa ett nytt gränssnitt men svårt att uppgradera eller säkert avveckla det har inte löst hela livscykelproblemet.

## När är teknik eller plattform faktiskt olämplig?

Fyra frågor hjälper inför ett beslut. **Först:** fungerar den avsedda användarresan, inklusive tillgänglighet, säkerhet och avbrott? **Sedan:** kan dagens teknik stödja de verkliga kraven om den används och konfigureras rätt? **Därefter:** ligger hindret i ett kontrakt, ett versionsberoende eller en ansvarsfördelning snarare än i produkten? **Slutligen:** vilka kostnader, risker och förbättringar ger alternativen *behålla, komplettera, ändra användning eller ansvar, respektive ersätta*?

En gammal webbteknik kan vara fullt lämplig för en stabil, tillgänglig tjänst. Ett modernt frontendramverk kan vara olämpligt om det skapar låsning, osäkra uppdateringsvägar eller specialkomponenter som inte går att använda med hjälpmedel. En gemensam formulärmotor kan vara rätt vid omfattande återanvändning men onödig i en liten, lokal tillämpning. En offlineplattform som saknar kontrollerbar konfliktlösning kan vara ett verkligt produktproblem – men ett ofullständigt begrepp om vilken data som är auktoritativ löses inte genom att köpa ny synkteknik.

Man bör alltså dokumentera observerat problem, berörd användarresa, reproducerbart test, grundorsak, tänkbara alternativ och förväntad effekt innan ett teknikbyte beslutas.

## Generation 4 – verksamhetsnära och AI-assisterad interaktion

I ett framtida scenario kan verksamhetsnära team och AI-verktyg skapa formulär, informationsvyer, rapporter och andra gränssnitt snabbare än tidigare. Detta kan öka tillgängligheten till utvecklingskapacitet men också mängden digitala produkter som måste förstås, skyddas och förvaltas. Generering är inte detsamma som godkänd publicering, och en AI-assisterad dialog är inte automatiskt lämplig för varje användargrupp eller beslut.

En användare behöver veta när ett svar är ett AI-genererat förslag, när en uppgift har registrerats och när en faktisk verksamhetsåtgärd genomförts. Systemet ska ge fungerande alternativa sätt att utföra viktiga uppgifter. Felaktiga, tvetydiga eller otillgängliga AI-genererade gränssnitt behöver kunna upptäckas och stoppas före publicering. Risken ska bedömas utifrån uppgift och konsekvens; ett internt utkast till informationssida behöver inte samma kontrollkedja som en tjänst som kan starta betalningar eller ändra en persons rättigheter.

AI kan skapa förslag till formulär eller hjälptexter för externt innehåll, men får inte genom sitt gränssnitt kringgå autentisering, åtkomstprövning eller verksamhetsbeslut. Själva åtgärden måste kontrolleras i en betrodd backend eller annan auktoritativ kontrollpunkt. Att stoppa ett gränssnitt eller återkalla ett agentmandat gör inte nödvändigtvis redan genomförda externa handlingar ogjorda.

En hållbar generation 4 kräver därför lättillgängliga, godkända byggblock, kontrollerad publicering, ägaransvar, användartestning, kostnads- och livscykelkontroll samt begriplig möjlighet till mänsklig granskning när konsekvenserna motiverar det. Generativa AI-modellers tillförlitlighet och risker bör bedömas särskilt, exempelvis med hjälp av NIST:s AI RMF och dess profil för generativ AI. Detta är rekommenderade analysverktyg, inte ett påstående om att varje gränssnitt behöver AI.

## De sju plattformstjänsterna – uppgifter och prövning

### PLS-001 – Design System-tjänst (PLT-001)

Erbjuder återanvändbara visuella och semantiska komponenter, mönster och designprinciper. I G2 är det viktigare att de mest använda kontrollerna fungerar enhetligt än att alla gränssnitt har identiskt utseende. Vid många team kan G3 ge versionerade komponentpaket, testade uppgraderingar och aktiv förvaltning. **Verifiera:** använd samma dialog i två produkter, uppgradera den och testa fokus, tangentbord, skärmläsare och felåterkoppling. Prova både komponenten isolerat och det verkliga formulärflödet, i webben och separat på native mobil där sådan finns. Plattformen äger inte hela användarresan.

### PLS-002 – Webbutvecklingsgrund (PLT-009)

Ger återanvändbar grund för klientarkitektur, projektstart, säker baseline och telemetri. Den förutsätter inte ett enda frontendramverk. **Verifiera:** ett nytt team skapar ett godkänt webbstöd, hanterar beroendeuppdatering och får fungerande felhantering och kvalitetstester utan unika beställningar. Låt två befintliga klienter uppgradera samma grund och kontrollera migrationsarbete, kända beroenden och äldre webbläsarstöd där det krävs. Denna tjänst är inte liktydig med CI/CD eller körmiljöerna i CAP-IT-10 och CAP-IT-08.

### PLS-003 – Formulärstjänst (PLT-002)

Ger formulärdefinition, återanvändbar validering och formulärmotorik. **Verifiera:** obligatoriska fält, fel, sparade utkast och sessionsavbrott fungerar i ett realistiskt flöde, även med tangentbord och hjälpmedel; inför därefter en versionsändring och kontrollera pågående utkast, datafält och felåterkoppling i två konsumerande produkter. Plattformen kan validera format och enkla regler men övertar inte automatiskt alla verksamhetsregler eller rättsliga kontroller.

### PLS-004 – Notifikations- och meddelandeleverans (PLT-024)

Ger kontrollerad leverans till människor via exempelvis e-post, SMS, push eller meddelande i tjänsten. **Verifiera:** mäta köläggning, försökt leverans, leveransutfall och rätt mottagare; ändra en meddelandemall och kontrollera kopplade kanalversioner, tillgänglighet och säkert utfasningsförfarande utan att felaktigt likställa teknisk leverans med mottagen, läst eller rättsligt delgiven information. Distinktionen mot meddelandeköer mellan system i CAP-IT-06 ska vara tydlig.

### PLS-074 – Geospatial informations- och karttjänst (PLT-015)

Ger kartlager, geokodning och spatiala frågor för verksamheter som behöver geografisk information. **Verifiera:** kontrollera kartans precision och källuppgifter, behörighet till känslig platsinformation och alternativ för användare som inte kan använda den visuella kartan. Central geografisk plattform är **situationsberoende**, inte något alla generationer måste innehålla.

### PLS-089 – Mediedistribution och streaming (PLT-016)

Ger distribution, cache och strömning av medieinnehåll där detta är ett återkommande behov. **Verifiera:** åtkomst till skyddat innehåll, hantering av utgående länkar, olika uppkopplingskvaliteter, textning och tillgängligt alternativ. Behovet är beroende av faktiska medieflöden; mer avancerad strömning är inte ett generellt mognadskrav.

### PLS-075 – Mobil fältapplikationsgrund och offline-synkronisering (PLT-025)

Ger säkert lokalt datastöd, offlinearbete och synkronisering för fältapplikationer. **Verifiera:** avbryt nätet, skapa och ändra uppgifter, låt en annan klient göra en konkurrerande ändring och kontrollera konfliktbeslut och återkoppling när synk inte startar automatiskt. Upprepa efter appavslut, utloggning och överlämning av enheten: kontrollera köstatus, obehörig läsning, möjlighet att spärra åtkomst, lagringstid och säker återanslutning. En cachad sida är inte samma sak som säkert offlinearbete; mobiloperativsystem och webbläsare kan dessutom begränsa bakgrundskörning.

## Förflyttningarna mellan generationerna

**G1→G2: kortfattat.** Från systemnära gränssnitt till en användarresa som korsar fler tekniska gränser. Det kräver tydligare kontrakt, ägarskap och gemensamma kvalitetsprov – inte nödvändigtvis en central kanalplattform.

**G2→G3: det huvudsakliga utvecklingssteget.** Behåll fokus på användarresan och mät återkommande utvecklings- och förvaltningskostnader. Produktifiera de tjänster där många team får faktisk nytta av självbetjäning och versionsstyrd återanvändning. Inför support, säkerhets- och tillgänglighetskontroller, undantag och avveckling från början. Ändra inte bara tekniken, utan också vem som ansvarar för den interna plattformens användbarhet och livscykel.

**G3→G4: möjlig fortsatt utveckling.** Erbjud godkända, begripliga byggblock för fler utvecklare och AI-assisterad interaktion, men låt risk och användarbehov avgöra automatiseringsnivån. Behåll mänskligt och verksamhetsmässigt ansvar för konsekvenserna.

## Diagnostiska tester och indikatorer

| Fråga | Praktiskt prov | Tolkning |
|---|---|---|
| Fungerar en viktig användarresa? | Genomför ett ärende genom webb, mobil och notifiering med fel i ett beroende. | Brister här är ett G2-grundproblem, inte automatiskt plattformsbrist. |
| Är gränssnittet tillgängligt? | Pröva centrala flöden med hjälpmedel och verkliga användare separat för webb, native mobil och specialklienter. | Delade komponenter hjälper, men varje klient och produkt äger utfallet. |
| Gör plattformen användarna mer framgångsrika? | Jämför slutförandegrad, tid för uppgiften, felåterhämtning och upplevd begriplighet mellan användargrupper. | Komponentadoption räcker inte; verkliga användarutfall måste bli bättre. |
| Är återanvändning värdefull? | Mät återkommande implementationer och uppgraderingskostnad i flera team. | Hög, likartad upprepning kan motivera G3-tjänst. |
| Är plattformen självbetjänad på riktigt? | Skapa, ändra, uppgradera och avveckla två konsumerande produkter, även när äldre versioner används. | Svår migrering och tysta kompatibilitetsbrott avslöjar ofullständig livscykel. |
| Är offlinesynk säker? | Simulera konflikter, utebliven bakgrundssynk, utloggning och utbytt enhet. | Verifierar verksamhetssemantik, köstatus och lokalt informationsskydd – inte bara nätcache. |
| Är genererad interaktion kontrollerad? | Försök publicera otillgängligt AI-genererat formulär och utföra obehörig handling. | Kontroll ska stoppa publicering eller åtgärd vid rätt gräns. |

Mätetal ska användas med sammanhang: genomförandegrad, avbrutna användarresor, tillgänglighetsbrister som drabbar användare, ledtid för åtgärd, uppgraderingsbelastning och andel kritiska flöden med automatiska och manuella prov. Ett högt antal installerade gemensamma komponenter är inte tillräckligt bevis på en bättre användarupplevelse.

## Avgränsningar och källor

**Källmodell:** *Förmågeöversikt – tekniska IT-förmågor*; *Plattformsöversikt – konceptuella plattformar* (baseline v1.1); *Från systemdrift till digital självständighet*. De sju PLS/PLT-kopplingarna kommer från källmodellen. Generationsindikatorer, exemplen och rekommendationerna är redaktionell/arkitektonisk analys och utgör ingen nulägesinventering.

**Kompletterande referenser:** W3C, [WCAG 2.2](https://www.w3.org/TR/WCAG22/); W3C, [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/) och [WCAG2ICT (informativ vägledning för icke-webbaserad programvara)](https://www.w3.org/WAI/standards-guidelines/wcag/non-web-ict/); [MDN om offline och bakgrundsdrift](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/Offline_and_background_operation); NIST, [AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) och [Generative AI Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence). Referenserna stödjer kvalitetskriterier och riskhantering; de visar inte att en särskild arkitektur eller produkt är obligatorisk.
