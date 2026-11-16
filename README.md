# Documentatie Wattson Mijn & Backoffice

Wattson Energie is een (fictieve) leverancier van elektriciteit en gas. Deze repository bevat de documentatie van het klantportaal (*Wattson Mijn*), de backoffice en de API, zoals het productteam die in de loop van het project heeft vastgelegd. Alle tarieven, belastingen, netbeheerders en feestdagen zijn fictief.

Waar de applicatie afwijkt van deze documentatie, is dat een bevinding.

Praktische informatie voor de testavond (adres van de applicatie, inloggen, scope) staat in `QUICKSTART.md`.

| Document | Eigenaar | Inhoud |
|---|---|---|
| `productvisie.md` | Product owner | Doel, rollen, algemene uitgangspunten, klanten, aansluitingen en contracten |
| `backlog-export.csv` | Productteam | Export van de backlog: epics en user stories met acceptatiecriteria |
| `notitie-afrekenregels.md` | Finance & Billing | Hoe er wordt afgerekend: tariefperioden, verbruik, energiebelasting, teruglevering, termijnbedragen, jaar- en proefafrekening, opzegvergoeding |
| `tariefblad.xlsx` | Finance & Billing | Tarieven, netbeheerkosten, energiebelasting, vermindering, terugleververgoeding en feestdagen |
| `beslislog.md` | Productteam | Besluiten die tijdens het project zijn genomen |
| `faq-klantenservice.md` | Klantenservice | Vragen van klanten over gedrag dat zo bedoeld is |
| `testdata.xlsx` | Testteam | Testaccounts en vrije adressen voor aanmelden en verhuizen |

De API is gedocumenteerd in de applicatie zelf: **`/api/docs`** (OpenAPI-specificatie op `/api/openapi.json`).

## Hoe lees je deze documentatie

- De documenten vullen elkaar aan; geen enkel document is volledig.
- Documenten zijn op verschillende momenten geschreven en niet altijd bijgewerkt. **Bij tegenstrijdigheid geldt het meest recente besluit in `beslislog.md`.**
- Alleen stories met status **Done** zijn opgeleverd.
