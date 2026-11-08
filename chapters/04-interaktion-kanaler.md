# Interaktion, presentation och kanaler

Användaren möter ett IT-stöd genom formulär, sidor, mobilappar, dialoger och meddelanden – inte genom de bakomliggande tjänsterna. En ansökan som påbörjas på webben, kompletteras i mobilen och följs upp genom ett meddelande måste därför upplevas som ett sammanhängande förlopp. Förmågan *Interaktion, presentation och kanaler* erbjuder gemensamma funktioner för begripliga, tillgängliga och förändringsbara användargränssnitt och kommunikationskanaler. Den äger inte därmed verksamhetsprocessen, uppgifternas innebörd eller besluten bakom gränssnittet.

## Vad den gemensamma förmågan behöver erbjuda

### Återanvändbara gränssnitt och formulär

Ett gemensamt designsystem kan erbjuda tillgängliga komponenter och mönster för navigation, dialoger, formulär, felmeddelanden och återkoppling. En webbapplikationsgrund kan ge utvecklingsteam rekommenderad klientarkitektur, startmallar och stöd för grundläggande kvalitet och uppdateringar. Formulärstjänster kan erbjuda formulärdefinitioner, inmatningskontroller, utkast och versionshantering. Det behöver vara möjligt att använda dessa tjänster utan att ett centralt team bygger varje enskild sida eller varje formulär.

Komponenter ska vara versionerade och förvaltade så att konsumerande lösningar kan uppdateras utan oväntade avbrott. En gemensam formulärmotor bör kunna hantera teknisk fältvalidering och inmatningsstöd; processförmågan använder formuläret i rätt ärendesteg, medan beslutsregler och handläggning hör hemma i *Regler och beslut* respektive *Process, workflow och ärendehantering*. Även ett vältestat komponentbibliotek kan användas fel. Utvecklingsteamet ansvarar för att den färdiga användarupplevelsen fungerar.

### Kanaler, meddelanden och specialiserad interaktion

Gemensamma kanaltjänster kan stödja webb, mobil och andra klienter samt leverans av meddelanden till människor genom exempelvis e-post, SMS eller pushnotiser. Ett ärendeflöde kan bestämma när en påminnelse behövs, medan kanaltjänsten hanterar själva utskicket. Tjänsten bör skilja mellan ett leveransförsök, ett tekniskt levererat meddelande och att mottagaren faktiskt tagit del av innehållet. Det är något annat än integrationsförmågans meddelandeköer mellan system. När geografiska vyer eller mediedistribution återkommer i många lösningar kan även karttjänster, geokodning, skyddad mediedistribution och strömning vara motiverade gemensamma erbjudanden. De behövs inte i alla organisationer.

För fältarbete kan en förvaltad mobil grund erbjuda lokal lagring och synkronisering. Användaren måste då kunna se skillnaden mellan lokalt sparat, väntande överföring, serverbekräftat och uppgifter som kräver konfliktlösning. En avbruten uppkoppling, en stängd app eller två samtidiga ändringar får inte tyst skapa en felaktig ärendestatus. Lokal lagring kräver dessutom skydd och lämplig radering när en enhet tappas bort, byter ägare eller användaren loggar ut. Offlinearbete är därför mer än att en webbsida kan visas utan nätverk.

### Användbarhet och tillgänglighet i hela användarresan

Tjänsterna bör ge stöd för tydlig navigation, hanterbara fel, tangentbordsanvändning, skärmläsare, förstoring och begripliga texter. Webb och native mobil behöver prövas mot sina respektive tekniska förutsättningar och användarnas hjälpmedel; ett godkänt webbtest bevisar inte att en mobilapp fungerar. Automatiska kontroller hjälper men ersätter inte verkliga användarprov. Tillgänglighet är ett krav på den färdiga interaktionen, inte bara en egenskap hos en komponent.

Gränssnittet behöver också skilja ett sparat utkast från ett mottaget ärende och ett regelresultat från ett fattat beslut. Sådan återkoppling måste bygga på tillförlitlig status från det system som faktiskt äger ärendet eller beslutet; en lyckad formulärinlämning eller API-kvittens bevisar inte att handläggningen är slutförd. Gemensamt utseende skapar inte i sig en sammanhängande användarresa.

## Generation 3 – utvecklingsteamen levererar sina egna gränssnitt

I generation 2 kan det finnas både separata gränssnitt hos olika systemteam och centrala specialister som bygger gemensamma formulär, portaler eller kanalanpassningar åt andra. När många team behöver samma hjälp kan den centrala funktionen bli en flaskhals. Det är samtidigt viktigt att åtgärda grundläggande problem med tillgänglighet och användarflöden; en ny plattform löser inte automatiskt bristande verksamhetsbegrepp eller felaktiga statusuppgifter.

I generation 3 erbjuder plattformsteamet förvaltade designkomponenter, formulärstöd, klientgrunder och relevanta kanaltjänster som interna produkter. Professionella utvecklingsteam kan själva skapa, konfigurera, testa, publicera, uppdatera och avveckla sina användargränssnitt inom gemensamma ramar. De ska inte behöva beställa varje nytt formulär eller enskild kanalförändring hos en central specialist. Plattformsteamet ansvarar för byggblockens kvalitet, säkerhet, tillgänglighetsstöd och uppgraderingsvägar; respektive produktteam ansvarar för den egna användarresan och för hur komponenterna används.

En fungerande självbetjäning kräver dokumenterade gränssnitt, versionerade komponenter, stöd för migrering och tillräcklig isolering mellan teamens lösningar. Om en gemensam portal inte tillåter att team ändrar sina egna vyer utan att riskera andras, behöver ansvar eller teknik anpassas. Plattformens värde märks inte främst i antalet återanvända komponenter utan i om teamen snabbare kan leverera begripliga och tillgängliga gränssnitt och uppdatera dem utan beroendeköer.

## Generation 4 – verksamheten skapar och förändrar många gränssnitt själv

I generation 4 bör verksamhetsmedarbetare själva kunna utforma, prova, publicera, följa upp och vidareutveckla exempelvis interna formulär, informationsvyer och enklare appar. Godkända visuella verktyg och AI-stöd kan hjälpa dem att välja lämpliga komponenter, anpassa texter och skapa gränssnitt som ansluts till befintliga ärendeflöden och verksamhetsfunktioner. En medarbetare som utformar ett nytt kompletteringsformulär ska i normalfallet inte behöva programmera en frontend eller begära att ett centralt kanalteam genomför förändringen.

Erbjudandet behöver därför innehålla begripliga och förvaltade gränssnittsbyggblock samt möjlighet att prova ett helt användarflöde innan det delas. Simulering och test behöver använda skyddade provuppgifter och testanslutningar, så att gränssnittets knappar inte oavsiktligt ändrar verkliga ärenden eller skickar meddelanden till riktiga mottagare. Tillgänglighet, korrekt återkoppling och ägaransvar gäller även gränssnitt som skapats med AI. För enkla interna gränssnitt kan verksamheten genomföra normala ändringar själv. Gränssnitt med högre risk behöver mer omfattande användar- och tillgänglighetsprov. En AI-genererad dialog får inte ge sken av att en åtgärd är genomförd när systemet bara har föreslagit den. Rätten att publicera ett gränssnitt ger inte rätt att förändra ärendets verksamhetsregler eller att fatta beslut för användaren.

Förmågan erbjuder byggblock för interaktion och kanaler. Den gemensamma skapande- och publiceringsvägen beskrivs i *Utveckling och teknisk leverans*; behörighet till verksamhetsåtgärder prövas i de tjänster som utför dem.
