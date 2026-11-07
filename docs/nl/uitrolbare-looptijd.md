# Uitrolbare looptijd
<!-- SID:runtime-title -->

## Geïmplementeerde grens
<!-- SID:runtime-scope -->

Het programmabeeld voor de uitvoeringsomgeving bevat veilig sluitende omgevingskoppeling, transactionele Firestore-opslag, begrensde koppelingen voor Gmail REST en uitgaande Telegram-berichten, Google OIDC-controle, een WSGI-ontvangsteindpunt uitsluitend voor Gmail en een via een toelatingslijst beveiligd startpunt voor Cloud Run-taken. De routeringseenheid voor de gedeelde bot, de begrensde ontleder van de kandidaatversie en de coördinator voor duurzame overdracht bestaan uitsluitend als inactieve broncode-onderdelen en zijn niet gekoppeld aan HTTP, weboproepen, ophaaldiensten, achtergrondtaken of een Telegram-toegangssleutel.

## Bescherming van externe handelingen
<!-- SID:runtime-effects -->

De Telegram-koppeling staat uitsluitend het aan een geheim gekoppelde privégesprek toe, voegt een bewerkingskenmerk toe en behandelt een ontbrekende zoekuitkomst nooit als toestemming om opnieuw te verzenden. De instellingen voor de gedeelde bot houden de inkomende poort en Versie 2 standaard uitgeschakeld, de noodschakelaar ingeschakeld, de schaduwmodus uitgeschakeld en het aandeel voor proefuitrol op nul. De ontleder van de kandidaatversie bewijst met kunstmatige tests dat verwijzingen aan serverzijde worden afgeleid en dat de persoonlijke identiteit van de eigenaar exact wordt vergeleken via beschermde laders. De Firestore-schrijver kan de status `COMMITTED` uitsluitend ondeelbaar aanmaken samen met een bijpassende duurzame overdracht; losse afronding werkt uitsluitend voor teruglezen. Herbezorging na uitval hervat de oorspronkelijke route, een vastgelegd duplicaat controleert de overdracht en begrensde opschoning verwijdert het paar van route en overdracht.

## Containeromgeving en toeleveringsketen
<!-- SID:runtime-container -->

De container gebruikt een met controlegetal vastgezette Python-basisindex, volledig op versie vastgezette looptijdafhankelijkheden en het niet-beheerder-ID `999` voor gebruiker en groep. Lokaal inladen van het programmabeeld, samenhang van afhankelijkheden en looptijdtests moeten vóór vrijgave slagen. Verzending naar het beeldenregister en uitrol naar Google Cloud blijven afzonderlijke handelingen voor de acceptatieomgeving.

## Nog niet doorlopen controlepoorten
<!-- SID:runtime-gates -->

Een van externe pakketten onafhankelijke gelijktijdige nabootsing controleert ondeelbare vastlegging van route en overdracht, hervatting na uitval, afstemming bij verloren antwoorden, verouderde volgordegrenzen, opsporing van integriteitsfouten, schoning en opschoning van recordparen, maar deze broncodefase bewijst geen beschermd postvak voor berichtladingen in de echte omgeving, echte Firestore-transacties, Gmail OAuth en bewaking, bevestiging en aflevering bij Telegram, doorsturing naar Versie 1, Artifact Registry, Cloud Run of aanvaarding van het terugdraaien. Paden voor Cloud Run, Pub/Sub en geheimenbeheer die actieve facturering vereisen hebben de status `DEFERRED_BY_ZERO_COST_POLICY`. Inschakeling van de gedeelde actieve route, weboproep of ophaaldienst, opdrachten en menu's of Gmail-bewaking is een wijziging in de productieomgeving en vereist uitdrukkelijke goedkeuring van de eigenaar.
