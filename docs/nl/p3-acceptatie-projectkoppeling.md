# P3: koppeling van het project voor de acceptatieomgeving
<!-- SID:p3-title -->

## Geverifieerde staat
<!-- SID:p3-state -->

De afzonderlijke, door de eigenaar beheerde projectomhulling `mail-telegram-v2-stg-250725` is gekoppeld aan de instelling `mail-telegram-v2-staging` in regio `europe-west1`. Geverifieerde terugleescontrole bevestigde één eigenaar en de afwezigheid van dienstaccounts, Pub/Sub-onderwerpen en -abonnementen of looptijdvoorzieningen van Versie 2. Facturering is uitgeschakeld.

## Wijzigingsgrens
<!-- SID:p3-boundary -->

Deze koppeling geeft geen toestemming voor het koppelen van facturering, het toepassen van de uitvoeringsomgeving, het inschakelen van programmahoofdkoppelingen, het aanmaken van geheimen, Gmail-bewaking, een Telegram-weboproep of verkeer in de productieomgeving. De instellingen `enable_billable_resources=false` en `enable_scheduling=false` blijven veilig gesloten. Nieuwe uitgaven bedragen 0 euro.

## Afgewezen hergebruik
<!-- SID:p3-reuse -->

Het project `gmail-telegram-mail-client` wordt niet gebruikt voor de acceptatieomgeving van Versie 2, omdat uit lokaal herkomstonderzoek een bestaande OAuth-cliënt en terugroepkoppeling van Versie 1 bleken. Dit voorkomt vermenging met actieve berichtverwerkers.

## Volgende controlepoort
<!-- SID:p3-next -->

Een route die actieve facturering vereist wordt niet toegepast en krijgt de status `DEFERRED_BY_ZERO_COST_POLICY`; er wordt niet opnieuw om een factureringsbesluit gevraagd. Het onafhankelijke bereik van de lokale gedeelde routeringseenheid wordt voortgezet met een onveranderlijke vastlegging, regressietests en terugdraaien naar Versie 1.
