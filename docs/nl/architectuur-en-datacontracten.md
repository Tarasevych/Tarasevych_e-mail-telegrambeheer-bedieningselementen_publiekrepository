# Architectuur en datacontracten

<!-- SID:components -->
## Onderdelen

De aanbiedersonafhankelijke toepassingskern bevat stromen voor Gmail en het postvak voor uitgaande berichten, een inactieve routeringseenheid voor de gedeelde bot en een inactieve coördinator voor duurzame overdracht. Een begrensde ontleder van de kandidaatversie kan een berichtenvelop verifiëren en een geschoonde `TelegramUpdate` opbouwen, maar de huidige WSGI-uitvoeringsomgeving heeft geen Telegram-eindpunt en geen actieve verbinding. Sjablonen voor Cloud Run, Pub/Sub, de wachtrij voor onbestelbare berichten en Firestore blijven standaard uitgeschakeld en het van facturering afhankelijke pad is uitgesteld.

<!-- SID:contracts -->
## Datacontracten

Elk post- en uitgaand berichtrecord heeft een `account_id` en een eenduidige eenheid. `TelegramUpdate` bevat ingestelde beschermde verwijzingen `bot_ref`, `account_ref`, `chat_ref`, `subject_ref`, een numerieke `update_id`, een tijdstip en één in omvang begrensde bericht- of terugroeplading. De lokale ontleder haalt verwijzingen uitsluitend uit beschermde serverinstellingen na kunstmatige aanmeldcontrole en exacte vergelijking van de persoonlijke identiteit van de eigenaar; door de cliënt meegezonden verwijzingen zijn niet gezaghebbend. De exacte V2-naamruimten zijn `/v2_<action>` en `v2:<action>` en de uitdrukkelijke toelatingslijst bevat uitsluitend `help`. `TelegramRouteDecision` geeft `V1`, `V2` of `DUPLICATE` terug; `TelegramHandoffRecord` en `TelegramHandoffReceipt` koppelen een geheimvrije afleververwijzing, vingerafdruk, afgeschermde berichtladingverwijzing, route met actie en volgordegrens zonder ruwe inhoud.

<!-- SID:boundaries -->
## Datagrenzen

Eén ondeelbare Firestore-transactie maakt een bijpassende geschoonde overdracht aan of controleert deze herhaalbestendig en zet het onveranderlijke routerecord op `COMMITTED`; zonder overdracht is die toestand onbereikbaar via de schrijfkoppeling en geldt deze bij terugleescontrole als een integriteitsschending. Een actief duplicaat is niet veilig om te bevestigen; een verlopen record of een record met status `FAILED` hervat de oorspronkelijke route met een hogere volgordegrens, terwijl een bijpassend duplicaat met status `COMMITTED` veilig kan worden bevestigd zonder nieuwe overdracht. De bewaartermijn geldt uitsluitend voor het paar van route en overdracht; begrensde opschoning verwijdert het paar gezamenlijk en verwijdert nooit records met status `ROUTED` of herhaalbare `FAILED`. Een afwijkende koppeling, ongeldige berichtlading, verouderde volgordegrens, tegenstrijdigheid tussen identiteit en overdracht of een dubbelzinnige uitkomst sluit veilig af als `RETRY`.
