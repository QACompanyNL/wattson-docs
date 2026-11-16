# Wattson Energie – Quickstart testavond

**Adres van de applicatie:** elk team heeft een eigen omgeving; het adres staat in de teamlijst die je bij de start krijgt (hieronder `<adres>`).

Wattson Energie is een fictieve energieleverancier. Jullie testen het klantportaal, de backoffice en de API, met de projectdocumentatie in deze repository (begin bij `README.md`) als waarheid: elke afwijking van de documentatie is een bevinding.

## Inloggen

| Rol | E-mail | Wachtwoord |
|---|---|---|
| Beheerder | `beheer@wattson.nl` | `Welkom123!` |
| Klanten (30 accounts) | zie `testdata.xlsx`, bijv. `pieter.jansen@example.nl` | `Welkom123!` |

## Wat is er beschikbaar

| Onderdeel | Waar |
|---|---|
| Klantportaal | `<adres>/mijn` (na inloggen) |
| Backoffice | `<adres>/beheer` (inloggen als beheerder) |
| Publieke pagina's | `<adres>/tarieven`, `<adres>/dynamische-prijzen`, `<adres>/aanmelden` |
| Mailbox (alle uitgaande e-mail) | `<adres>/mailbox` |
| REST API + documentatie | `<adres>/api/docs` (token via `POST /api/v1/auth/token`) |

## Handig om te weten

- De applicatie staat op **donderdag 19 november 2026**. Als beheerder kun je onder **Tijd** de applicatiedatum en -tijd verzetten, en per klant tijd simuleren. Zo test je termijnen, herinneringen en publicatietijden zonder te wachten.
- Een klant (of de beheerder) kan via portaal, backoffice en API een **proefafrekening** maken over een periode in het verleden.
- Elk team heeft een eigen omgeving. Met **Database terugzetten** (backoffice-dashboard) zet je alles terug naar de startsituatie; ingestelde tijd en alle wijzigingen gaan dan verloren.

## Binnen scope

- Alles wat je via de browser (UI), de API en de mailbox kunt bereiken.
- Functionele fouten, rekenfouten, validatie, autorisatie (bijv. gegevens van andere klanten), toegankelijkheid en foutafhandeling.

## Buiten scope

- De server, de container of het netwerk aanvallen, of proberen toegang te krijgen tot het onderliggende systeem.
- Denial of service, load- en stresstests, of geautomatiseerd verkeer dat de omgeving onbruikbaar maakt.
- Omgevingen van andere teams.

## Werkwijze

Er is geen puntentelling en geen vast format. Hoe jullie de agents inzetten, welke modellen en tools jullie gebruiken en wat jullie opleveren, bepalen jullie zelf.
