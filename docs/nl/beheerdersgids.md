# Beheerdersgids

<!-- SID:preflight -->
## Voorcontrole

Bevestig de geldende fasebevoegdheid, de enige schrijver, de onveranderlijke kandidaatversie en het terugdraaidoel vóór elke externe handeling. Facturering moet bewust gesloten blijven: maak deze niet aan, activeer haar niet opnieuw en koppel haar niet.

<!-- SID:runtime -->
## Uitvoering

De lokale kandidaatversie voor de gedeelde bot is geen actieve berichtverwerker. Het standaardbeleid is: inkomende poort en Versie 2 uitgeschakeld, noodschakelaar ingeschakeld, schaduwmodus uitgeschakeld en aandeel voor proefuitrol `0`. De begrensde ontleder haalt beschermde eigenaarsverwijzingen na aanmeldcontrole uit de serverinstellingen en vertrouwt de JSON-gegevens van Telegram niet. De coördinator geeft uitsluitend `ACK_SAFE` terug na een herhaalbestendige vastlegging in het beschermde postvak voor berichtladingen en een bijpassende ondeelbare overdracht met volgordegrens; de statussen `ROUTED` en `FAILED`, een verouderde volgordegrens en een dubbelzinnige uitkomst geven `RETRY`. Wijziging van de toegangssleutel van de gedeelde bot, het aanmaken van een nieuwe bot, `setWebhook`, `deleteWebhook`, `getUpdates`, het starten of stoppen van een ophaaldienst, wijziging van opdrachten en menu's en Gmail-bewaking zijn verboden vóór uitdrukkelijke goedkeuring voor de productieomgeving. Van facturering afhankelijke uitrol van Cloud Run, Pub/Sub en geheimenbeheer wordt niet uitgevoerd.

<!-- SID:incident -->
## Storingen en incidenten

Bevestig een actief duplicaat nooit als een voltooide handeling: wacht op het verlopen van de tijdelijke vergrendeling of op regulier herstel. Een duplicaat met status `COMMITTED` is alleen veilig om te bevestigen wanneer een bijpassend duurzaam ontvangstbewijs de terugleescontrole doorstaat; een vastgelegde status zonder overdracht is een integriteitsincident. Laat bij een afwijking in aanmelding of eigenaar, bij een tegenstrijdigheid in identiteit of overdracht of bij een onverwachte route de noodschakelaar ingeschakeld, bewaar geschoond samenhangs- en statusbewijs en zet de hoofdroute terug naar Versie 1. Herhaal nooit een onbekende wijziging in de actieve omgeving. Het terugdraaidoel voor de productieomgeving is de bestaande verwerker van Versie 1 met een ongewijzigde toegangssleutel van de gedeelde bot.
