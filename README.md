# PackageTracker

Haalt trackingnummers uit leveringsmails (Gmail en iCloud Mail) en toont de pakjes op een Home Assistant-dashboard. Vervoerders: DHL, GLS, DPD, bpost, Mondial Relay (en wat er verder in de mail zit, zoals PostNL, FedEx en Amazon).

## Hoe het werkt

- Opslag: een Local To-do-lijst `todo.pakjes`. Een open item is een lopend pakje, een afgevinkt item staat in het archief.
- Dashboard: `dashboard-pakjes` met de lijst en knoppen naar de volgpagina van elke vervoerder. Config in [`dashboard/dashboard-pakjes.json`](dashboard/dashboard-pakjes.json).
- Verversen: dagelijks rond 6u en op verzoek, zie [`docs/ochtendtaak.md`](docs/ochtendtaak.md).
- Meldingen: naar de mobiele app van de eigenaar bij afgeleverd, klaar in een afhaalpunt of nieuw onderweg.
- Live status via een API (DHL-sleutel, 17TRACK of Ship24) is bewust nog niet toegevoegd. De status komt uit de mails.

## Installeren

1. In Home Assistant: Instellingen, Apparaten en diensten, Integratie toevoegen, **Local To-do**, naam `Pakjes` (geeft `todo.pakjes`).
2. Dashboard aanmaken met url `dashboard-pakjes` en de config uit `dashboard/dashboard-pakjes.json` plakken. Vervang `<POSTCODE>` door je postcode.
3. Geplande taak instellen volgens `docs/ochtendtaak.md`.

## Terugdraaien

Verwijder het dashboard `dashboard-pakjes` en de Local To-do `Pakjes`. Andere dashboards en lijsten worden niet aangepast.

## Privacy

Er staan geen echte trackingnummers, adressen of sleutels in deze repo. De voorbeelddata in `data/` is verzonnen. Zet API-sleutels nooit in de repo of in een dashboard, maar server-side.
