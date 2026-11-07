# P8: inactieve kandidaatversie voor duurzame overdracht
<!-- SID:p8-title -->

## Fasegrens
<!-- SID:p8-scope -->

Fase 8 is uitsluitend een lokale kosteloze broncode-kandidaatversie. Deze voegt geen Telegram-eindpunt, actieve verwerker, aanbiedersregistratie, toegang tot de toegangssleutel, Gmail-bewaking, clouduitrol of factureringswijziging toe. Het Google Apps Script van Versie 1 en de bestaande inkomende poort van de gedeelde bot blijven alleen-lezen en ongewijzigd.

## Geverifieerde afleiding aan serverzijde
<!-- SID:p8-auth -->

De begrensde ontleder verifieert eerst een kunstmatig transportgeheim in constante tijd en controleert het exacte privégesprek en de identiteit van de eigenaar via laders uit de beschermde opslag. De verwijzingen `bot_ref`, `account_ref`, `chat_ref` en `subject_ref` zijn uitsluitend afkomstig uit serverinstellingen; gelijknamige velden in cliënt-JSON worden genegeerd. De standaard uitgeschakelde stand stopt de verwerking vóór elke toegang tot het beschermde geheim.

## Duurzame overdracht en veilige bevestiging
<!-- SID:p8-handoff -->

De aanbiedersonafhankelijke coördinator doorloopt de stappen: afleiding van verwijzingen → onveranderlijke routeclaim → herhaalbestendig beschermd postvak voor berichtladingen → ondeelbare vastlegging van route en overdracht met volgordegrens. `TelegramHandoffRecord` koppelt een geheimvrije afleververwijzing, bijwerkingsvingerafdruk, afgeschermde berichtladingverwijzing, oorspronkelijke route met actie en exacte volgordegrens. Losse afronding uit eerdere fasen dient uitsluitend voor teruglezen en kan geen status `COMMITTED` aanmaken. Alleen een bijpassend duurzaam ontvangstbewijs levert `ACK_SAFE` op; een actieve, verouderde, mislukte, tegenstrijdige of dubbelzinnige uitkomst levert `RETRY` op.

Het opgeslagen routerecord is leidend voor `delivery_ref`, route, actie en volgordegrens. De huidige achtergrondwerker kan geen op zichzelf kloppende overdracht vastleggen met een afwijkende betekenis van de route; herhaling van een bestaand ontvangstbewijs vereist eveneens de oorspronkelijke achtergrondwerker, de volgordegrens en volledige gelijkheid tussen route en overdracht. Dit wordt op identieke wijze gecontroleerd voor zowel de geheugenreferentie als het pad met nagebootste Firestore-transacties.

## Lokale verificatie
<!-- SID:p8-tests -->

Kunstmatige geheugentests en van externe pakketten onafhankelijke tests met nagebootste Firestore-opslag dekken aan serverzijde afgeleide koppelingen, onjuiste geheimen, gesprekken, gebruikers of groepen, misvormde of te grote berichtenveloppen, gelijktijdige eenmalige overdracht, uitval vóór vastlegging, verloren vastleggingsantwoorden, verouderde achtergrondwerkers of volgordegrenzen, routevervanging binnen dezelfde volgordegrens, aantasting van aflevering, route, actie of volgordegrens na vastlegging, vastgelegde status zonder overdracht, botsingen en schoning. Deze tests vormen geen aanvaardingsbewijs voor echte Firestore-opslag, Telegram-aflevering, de acceptatieomgeving of de productieomgeving.

## Resterende controlepoorten
<!-- SID:p8-gates -->

Vóór aanvaarding voor de productieomgeving zijn beschermde opslag van berichtladingen in de echte omgeving, het exacte transport van de gedeelde inkomende poort, getypeerde HTTP-koppeling voor definitieve bevestiging zonder neveneffect tegenover tijdelijke herhaling, doorsturing naar Versie 1 met behoud van accountscheiding, herbezorging door de aanbieder, echte Firestore-transacties, herstel volgens hersteltijd- en herstelpuntdoelen, oefeningen voor limieten en intrekking van inloggegevens, terugleescontrole van toegangsbeheer en privacy, controle van werking en toegankelijkheid in de acceptatieomgeving, beproefd terugdraaien, een onveranderlijk uitrolmanifest en onafhankelijke terugleescontrole van de omgeving vereist. Facturering blijft gesloten, nieuwe uitgaven bedragen 0 euro en de controlepoort voor de productieomgeving staat op `UNASKED`.
