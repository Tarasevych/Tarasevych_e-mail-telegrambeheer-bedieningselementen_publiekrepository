# Snelstart voor Versie 2

<!-- SID:scope -->
## Afbakening

Dit zijn uitsluitend plansjablonen. Voorzieningen staan standaard uit en toepassen is verboden zonder de uitdrukkelijke bevestiging van de eigenaar.

<!-- SID:prepare -->
## Voorbereiding

Controleer de werkvertakking en voer `python3 tools/verify_governance.py`, `python3 tools/verify_doc_parity.py` en de migratietests uit. Plaats nooit geheimen in bestanden van de opslagplaats.

<!-- SID:plan -->
## Plancontrole

Beoordeel de map `infra/` met `enable_billable_resources=false`. Bevestig regio `europe-west1`, gegevenslocatie `EU`, grenzen voor aantallen instanties en verbruikslimieten.

<!-- SID:handoff -->
## Overdracht

Bewaar uitsluitend geschoonde ID's en planningsbewijs in het kandidaatmanifest. Aanvaarding voor de echte omgeving of de acceptatieomgeving wordt hiermee niet bewezen.
