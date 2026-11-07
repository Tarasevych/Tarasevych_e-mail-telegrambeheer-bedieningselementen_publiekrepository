# Migratie, terugdraaien en herstel

<!-- SID:export -->
## Uitvoer

Voer `mail_migrate.py export` uit met één `--account-id`. Het archief bevat de schemaversie, bronbytes, een SHA-256-manifestbestand en een uitzonderingsregister voor verwijderingsmarkeringen.

<!-- SID:verify -->
## Verificatie

Voer `verify` uit vóór het inlezen. Gebruik `--dry-run` om het verwerkingspad zonder schrijven te bewijzen; een afwijking in het controlegetal of het account stopt de bewerking onmiddellijk.

<!-- SID:restore -->
## Herstel en terugdraaien

Voer `restore` uit naar een nieuw doel en vergelijk de SHA-256-controlegetallen. Leg vóór elke omschakeling van de gedeelde inkomende poort het herstel van het duurzame Telegram-routerecord, het bijpassende ontvangstbewijs van de overdracht en de beschermde berichtladingverwijzing als één samenhangend geheel vast en verifieer deze: onveranderlijke vingerafdruk en beslissing, status, aantal pogingen, volgordegrens en bewaartermijngegevens zonder ruwe berichtlading. De status `COMMITTED` zonder bijpassende overdracht is een integriteitsfout; records met status `ROUTED` en herhaalbare `FAILED` mogen nooit als verlopen eindgegevens worden opgeschoond. De huidige kunstmatige tests vormen geen aanvaardingsbewijs voor echt herstel volgens hersteltijd- en herstelpuntdoelen. Terugdraaien betekent terugkeren naar het vooraf vastgelegde doel, het bewaren van bewijs en het vermijden van verborgen overschrijving.
