# P2 — bewijs voor het lokale fundament

Versie: `1.0`

Status: `LOCAL VERIFIED; PR/CI/REMOTE READBACK PENDING`

<!-- SID:scope -->
## Bereik

Dit verslag geldt uitsluitend voor de lokale broncode-kandidaatversie. Het bewijst geen aanvaarding voor echte voorzieningen, de acceptatieomgeving of de productieomgeving en stelt niet dat voorzieningen voor cloud, OAuth, Gmail of Telegram zijn gekoppeld.

<!-- SID:inputs -->
## Invoer

Het actieve hoofddocumentpaar herziening `1.0.0`, 35 canonieke eisen, het herstelbewijs van fase 1, de besloten initiële `main`-vertakking en de alleen-lezen terugdraailijn van Versie 1.

<!-- SID:tasks -->
## Uitgevoerde taken

De aanbiedersonafhankelijke kern voor contracten en betrouwbaarheid, een kunstmatige minitoepassing in het Oekraïens (`uk`) en Nederlands (`nl`), tien afzonderlijke startpunten voor achtergrondtaken, standaard uitgeschakelde OpenTofu-sjablonen, een volledige migratieproef, alleen-lezencontroles en een eenduidig bronmanifest zijn opgesteld.

<!-- SID:outputs -->
## Opbrengsten

Broncode van de toepassing, van versies voorziene schema's en testgegevens, gekoppelde beheerdershandleidingen, statische infrastructuurcontracten, eenheidstests, eisenherleidbaarheid, herkomstregistratie van hulpmiddelen en gereedschap voor het onveranderlijke bronmanifest.

<!-- SID:tests -->
## Controles

25 eenheidstests voor achtergronddienst en bestuur, 2 migratietests, 6 statische infrastructuurtests, controles voor testen, typecontrole en opbouw van de minitoepassing, controle op documentgelijkheid, controle op bestuursregels en afwezigheid van geheimen, evenals OpenTofu-opmaakcontrole, geldigheidscontrole en het standaard uitgeschakelde proefplan.

<!-- SID:evidence -->
## Bewijsgrens

Kunstmatige testgegevens bevatten geen persoonsgegevens of geheimen. Het controlegetal van het OpenTofu `1.10.10`-archief en de vergrendeling van aanbieder `7.41.0` zijn geverifieerd. De exacte vastlegging, het samenvoegingsverzoek, de uitvoer van de continue controle en de terugleescontrole op afstand worden buiten de naar zichzelf verwijzende broncodeboom vastgelegd.

<!-- SID:dod -->
## Voltooiingscriteria

Het lokale deel van fase 2 is uitsluitend voltooid wanneer de werkboom schoon is, het bronmanifest slaagt, de beveiligingscontrole van de wijzigingen geen onopgeloste P0- of P1-bevindingen bevat en de continue controle van het reguliere samenvoegingsverzoek slaagt. Samenvoeging en gelijkheid op afstand voltooien fase 2.

<!-- SID:rollback -->
## Terugdraaien

De vertakking `main` verandert niet vóór de samenvoeging. De reserveverwijzingen van fase 1 en Versie 1 blijven ongewijzigd; bij een fout blijft de werkvertakking beschikbaar voor een oorzakelijke herstelwijziging zonder geforceerd overschrijven van de geschiedenis.

<!-- SID:gate -->
## Controlepoort voor toestemming

Lokaal schrijven, vastleggen, verzenden naar de besloten opslagplaats en een regulier samenvoegingsverzoek zijn toegestaan volgens hoofdherziening `1.0.0`. Nieuwe uitgaven, handmatige aanmelding en bevordering naar de productieomgeving blijven afzonderlijke controlepoorten.

<!-- SID:terminal -->
## Eindstatus

De status blijft `PENDING` tot de exacte terugleescontrole van samenvoegingsverzoek en continue integratie. Het ontbreken van aanvaarding in de echte omgeving is de verwachte grens van fase 2 en vormt geen bewijs voor latere fasen.
