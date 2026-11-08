# Identitet och tillit

När många IT-stöd samverkar behöver organisationen veta inte bara vem som är inloggad, utan också vilken tjänst som anropar en annan och med vilken rätt. Förmågan *Identitet och tillit* erbjuder gemensamma tjänster för att styrka identiteter, etablera tillit och hantera åtkomst för människor och tekniska aktörer. Den ska inte överta verksamhetssystemens beslut om vilka verksamhetsåtgärder som är tillåtna.

## Vad det gemensamma erbjudandet behöver omfatta

### Identiteter och inloggning

Identitetskataloger, kontolivscykel, riskanpassad autentisering, federation och gemensam inloggning behöver fungera även när användare och tjänster finns i flera miljöer eller organisationer. När en person byter uppdrag eller slutar ska åtkomst kunna avslutas inom fastställda tidsramar. Att spärra ett konto i katalogen gör dock inte automatiskt alla redan utfärdade token och aktiva sessioner ogiltiga.

### Behörighetsstöd och privilegierad åtkomst

Förmågan behöver erbjuda återanvändbara mekanismer för att förmedla identitetsuppgifter, hantera rättighetstilldelning och vid behov utvärdera åtkomstpolicyer. En korrekt inloggad användare har ändå inte automatiskt rätt att läsa ett visst ärende. Den skyddade tjänsten måste verkställa behörighetskontrollen utifrån tillförlitliga uppgifter och aktuella verksamhetsregler. Administrativ åtkomst behöver särskilt skydd, begränsad giltighet, spårbarhet och fungerande nödåtkomst. [K007]

### Tekniska identiteter och tillitsrelationer

Applikationer, integrationsflöden och byggpipelines behöver identifiera sig utan delade användarlösenord eller okontrollerade permanenta servicekonton. Det gemensamma erbjudandet omfattar arbetslastidentiteter, certifikat, skyddad hemlighetshantering och automatisk förnyelse och återkallelse. Kortlivade behörighetsbevis bör användas där de passar. Tjänsterna behöver också ge överblick över ägare, tillitsrelationer och beroenden, så att ändringar och avveckling inte orsakar okända avbrott. Särskilda tjänster för exempelvis elektronisk signering tillkommer när verksamhetskraven motiverar det.

## Generation 3 – identitet som självbetjänad plattformstjänst

I generation 2 kan fungerande identitetskataloger ändå innebära att specialister måste skapa varje tekniskt konto, certifikat och federationskoppling manuellt. I generation 3 erbjuder identitetsteamet i stället godkända standardprofiler genom dokumenterade gränssnitt och automatiserade livscykler.

Ett utvecklingsteam ska själv kunna ansluta inloggning, ge sin applikation en avgränsad arbetslastidentitet och använda certifikat och hemligheter som förnyas och tas bort kontrollerat. Plattformsteamet ansvarar för tjänsternas säkerhet och tillgänglighet; produktteamet ansvarar för att tillämpa rätt behörighetskontroller i sin applikation. En portal som bara skickar vidare samma manuella beställning är inte tillräcklig självbetjäning.

## Generation 4 – identitet och mandat för verksamhetsskapade lösningar

En verksamhetsmedarbetare som bygger en assistent eller automation ska inte behöva konfigurera federation, servicekonton eller API-nycklar. Den godkända skapandemiljön behöver kunna använda förvaltade identitets- och åtkomstprofiler utifrån lösningens uppgift och risk.

Här behöver förmågan skilja mellan lösningens tekniska identitet, vem som gett den ett uppdrag och vilket mandat som faktiskt gäller. En assistent kan identifieras som en viss arbetslast, men får inte därigenom användarens samtliga rättigheter. Ett avgränsat mandat behöver kunna representeras med tillförlitliga uppgifter om funktioner, resurser och giltighetstid och kunna återkallas. Mandatet kan bygga på delegering från en användare eller ett särskilt beslutat uppdrag; vilket uppdrag som är tillåtet avgörs av behörig verksamhetsfunktion, inte av identitetsplattformen. För känsliga ändringar kan ytterligare godkännande krävas, och den skyddade tjänsten måste kontrollera den aktuella rätten vid verkställighet, även när anropet förmedlas via en integration.

En verksamhetsskapad assistent som först bara sammanställer ärendeunderlag kan senare få rätt att skapa utkast. Då behöver mandatet prövas på nytt. När lösningen delas, byter ägare eller avvecklas ska åtkomsten kunna ändras eller återkallas; redan genomförda åtgärder kan däremot inte göras ogjorda enbart genom att åtkomsten stängs.

## Gräns mot övriga förmågor

Identitetsförmågan styrker aktörer och gör mandat möjliga att begränsa och återkalla. Ett anrop kan förmedlas genom *Integration och informationsutbyte*, men den mottagande verksamhetstjänsten verkställer sina egna behörighets- och åtgärdsregler.
