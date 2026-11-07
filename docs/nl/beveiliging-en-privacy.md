# Beveiliging en privacy

<!-- SID:secrets -->
## Geheimen

Broncode en Git bevatten uitsluitend een beschermde verwijzing naar de bestaande gedeelde bot voor Versie 1 en Versie 2. De toegangssleutel, het ID van het privégesprek, OAuth-gegevens en berichtinhoud worden nooit gekopieerd. Een nieuwe bot, het intrekken, opnieuw aanmaken of wisselen van een toegangssleutel en het aanmaken van een nieuwe geheimversie vallen buiten deze fase.

<!-- SID:access -->
## Toegangsbeheer

De inactieve ontleder van de kandidaatversie verifieert een kunstmatig transportgeheim, het exacte privégesprek en de identiteit van de eigenaar via beschermde laders en bouwt daarna een bijwerking uitsluitend op met de ingestelde verwijzingen `bot_ref`, `account_ref`, `chat_ref` en `subject_ref`. De berichtlading van de cliënt is niet gezaghebbend voor deze verwijzingen. Versie 2 heeft afzonderlijke naamruimten voor opdrachten en terugroepacties en de standaard ingeschakelde noodschakelaar behoudt de terugvaloptie naar Versie 1. De opslag weigert tegenstrijdige vingerafdrukken, routevoorstellen of overdrachten, verouderde volgordegrenzen en de status `COMMITTED` zonder bijpassend ontvangstbewijs. Het toegangsbeheer in de cloud wordt niet gewijzigd.

<!-- SID:logging -->
## Logboekregistratie

Logboeken, het duurzame routerecord en het ontvangstbewijs van de overdracht bevatten uitsluitend een controlegetal of verwijzing, `update_id`, de onveranderlijke beslissing, de geheimvrije afleververwijzing, de afgeschermde berichtladingverwijzing, het aantal pogingen, de volgordegrens, tijdstippen en de status; ze bevatten nooit ruwe verwijzingen naar eigenaar of achtergrondwerker, e-mail- of gespreksinhoud, terugroepgegevens, toegangssleutels, gespreks-ID's of sessiegegevens. De persoonlijke berichtenvelop mag uitsluitend naar een toekomstige koppeling voor het beschermde postvak gaan, die in deze fase niet is aangesloten. Een bewaartermijn ontstaat pas na een ondeelbare vastlegging van route en overdracht en begrensde opschoning verwijdert nooit herhaalbaar werk. Kunstmatige tests en nabootstests gelden niet als aanvaarding voor de echte voorzieningen of de productieomgeving.
