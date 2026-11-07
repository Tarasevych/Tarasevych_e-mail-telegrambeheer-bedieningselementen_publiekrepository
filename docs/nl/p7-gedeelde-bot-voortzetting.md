# P7: kosteloze voortzetting met gedeelde bot
<!-- SID:p7-title -->

## Geldend eigenaarsbesluit
<!-- SID:p7-authority -->

Het voortzettingsbesluit van de eigenaar heeft het SHA-256-controlegetal `f439fe6a280d543eea3353e6e727356aeda7005fcecd8136ddb51c8a9b512575`. Facturering is bewust gesloten en mag niet worden aangemaakt, opnieuw geactiveerd of gekoppeld. Nieuwe uitgaven bedragen 0 euro.

## Grens van de gedeelde bot
<!-- SID:p7-shared-bot -->

De bestaande beschermde botverwijzing wordt gedeeld door Versie 1 en Versie 2. Git bevat geen toegangssleutel, gespreks-ID of persoonlijke inhoud. Een nieuwe bot en het intrekken, opnieuw aanmaken of wisselen van de toegangssleutel zijn verboden.

## Inactieve kandidaatversie van de routeringseenheid
<!-- SID:p7-router -->

De aanbiedersonafhankelijke routeringseenheid vergelijkt ingestelde beschermde koppelingen voor eigenaar, account, gesprek en onderwerp, scheidt `/v2_<action>` en `v2:<action>`, staat uitsluitend de uitdrukkelijke handeling `help` toe, slaat geen terugroepargumenten op en weigert vermeldingen van een andere bot. Een toekomstige geverifieerde inkomende poort moet het aan serverzijde afleiden van de koppelingen nog bewijzen. De eenheid bewaart ondeelbaar een onveranderlijk `bot_ref + update_id`-routerecord met vingerafdruk, tijdelijke vergrendeling, volgordegrens en herhaalbestendige afleververwijzing. Herbezorging na uitval hervat dezelfde versieroute met een hogere volgordegrens; uitsluitend een vastgelegd duplicaat geldt als afgerond en opschoning verwijdert alleen verlopen records met status `COMMITTED`. De terugvaloptie naar Versie 1, de veilig sluitende noodschakelaar, de schaduwmodus en de per eigenaar stabiele proefuitrol blijven behouden. De routeringseenheid voert geen verwerker uit en is niet verbonden met een actieve inkomende poort.

## Kosteloze grens
<!-- SID:p7-zero-cost -->

Paden voor Cloud Run, Pub/Sub en geheimenbeheer die actieve facturering vereisen hebben de status `DEFERRED_BY_ZERO_COST_POLICY`. Lokale en kunstmatige controles worden niet voorgesteld als aanvaarding voor de cloud-acceptatieomgeving.

## Controlepoort voor de productieomgeving en terugdraaien
<!-- SID:p7-production -->

Vóór bevordering naar de actieve omgeving moet de verwerker de bevestigingsregel bewijzen: bevestiging of positieverschuiving bij Telegram vindt pas plaats na herhaalbestendige duurzame overdracht en afronding binnen de volgordegrens. Een actieve weboproep of ophaaldienst, opdrachten en menu's, Gmail-bewaking, omschakeling van de inkomende poort van Versie 1 of elke gedragsaanpassing van de gedeelde bot vereist uitdrukkelijke goedkeuring van de eigenaar voor de productieomgeving op een onveranderlijke vastlegging. Terugdraaien houdt in dat Versie 1 als hoofdroute behouden of hersteld blijft, de noodschakelaar ingeschakeld staat en de toegangssleutel ongewijzigd blijft.
