# Ochtendtaak

Elke dag rond 6u (Europe/Brussels) draait een geplande taak die:

1. de items van `todo.pakjes` leest;
2. Gmail en iCloud Mail alleen-lezen doorzoekt op verzend- en leveringsmails van de laatste 2 dagen;
3. nieuwe pakjes toevoegt (`todo.add_item`), bestaande bijwerkt en afgeleverde afvinkt (`todo.update_item`, status `completed`);
4. een melding stuurt via `notify.<jouw_mobiele_app>` bij afgeleverd, klaar in een afhaalpunt of nieuw onderweg;
5. verder niets in Home Assistant wijzigt en niets verwijdert.

Verversen op verzoek kan altijd: vraag om "update mijn pakjes".

## Formaat van een item

- `item`: `Vervoerder · omschrijving`
- `description`: `trackingnummer · status · volglink`
- Afgeleverd of afgehaald betekent status `completed`, zodat de afgevinkte items het archief vormen.

## Volglinks

| Vervoerder | Link |
|---|---|
| bpost | `https://track.bpost.cloud/btr/web/#/search?lang=nl&itemCode=<code>&postalCode=<POSTCODE>` |
| DPD | `https://tracking.dpd.de/parcelstatus?query=<nr>&locale=nl_BE` |
| DHL | `https://www.dhl.com/be-nl/home/tracking.html?tracking-id=<nr>` |
| GLS | de MyGLS-link uit de mail |
