# Besluitenlijst productteam Wattson Mijn

*Bijgehouden door de product owner. Nieuwste besluit onderaan. Bij tegenstrijdigheid met andere documenten geldt het meest recente besluit.*

| Nr | Datum | Status |
|---|---|---|
| B-01 | 20-01-2025 | Genomen |
| B-02 | 03-02-2025 | Genomen |
| B-03 | 14-04-2025 | Genomen |
| B-04 | 09-09-2025 | Genomen |
| B-05 | 03-11-2025 | Genomen |
| B-06 | 10-03-2026 | Genomen |
| B-07 | 21-04-2026 | Genomen |
| B-08 | 19-05-2026 | Genomen |
| B-09 | 16-06-2026 | Afgewezen |
| B-10 | 28-09-2026 | Genomen |
| B-11 | 12-10-2026 | Genomen |

---

### B-01 · 20-01-2025 · Eén tijdzone

**Besluit.** Alle datums en tijden in portaal, backoffice, API en afrekening zijn Nederlandse tijd (Europe/Amsterdam), inclusief zomer- en wintertijd.
**Aanleiding.** Het oude systeem rekende deels in UTC; dat gaf verschillen tussen portaal en factuur.

### B-02 · 03-02-2025 · Eigen feestdagenlijst

**Besluit.** Voor de tariefperioden hanteert Wattson een eigen feestdagenlijst. Finance beheert die lijst op het tariefblad.

### B-03 · 14-04-2025 · Testomgeving zonder echte e-mail

**Besluit.** In test- en acceptatieomgevingen wordt geen echte e-mail verstuurd. Alle uitgaande e-mail komt in de mailbox van de applicatie.

### B-04 · 09-09-2025 · Gasverbruik per gasdag

**Besluit.** De verbruikspagina en de API tonen gasverbruik per gasdag (06:00–06:00), zoals netbeheerders dat doen. De afrekening blijft op kalenderdagen. Klantenservice neemt dit op in de FAQ.

### B-05 · 03-11-2025 · Plausibiliteitsgrens

**Besluit.** De plausibiliteitswaarschuwing bij het doorgeven van een meterstand verschijnt bij een gemiddeld dagverbruik van meer dan **3 keer** het gemiddelde dagverbruik van die meter.
**Aanleiding.** Klanten typten een cijfer te veel en kregen geen waarschuwing.

### B-06 · 10-03-2026 · Wachtwoordeisen

**Besluit.** Een wachtwoord heeft minimaal **8 tekens**, met ten minste één letter en één cijfer. Bestaande wachtwoorden blijven geldig.
**Aanleiding.** Uitkomst van de beveiligingsaudit van februari 2026.

### B-07 · 21-04-2026 · Startdatum bij aanmelden

**Besluit.** Bij aanmelden kan de startdatum liggen tussen vandaag en **3 maanden** vooruit.
**Aanleiding.** Nieuwe klanten met een lopend contract bij een andere leverancier willen eerder vastleggen.

### B-08 · 19-05-2026 · Verlengingsaanbod

**Besluit.** Het verlengingsaanbod voor een vast contract komt vanaf **60 dagen** vóór de einddatum.
**Aanleiding.** Klanten vergelijken eerder dan we dachten.

### B-09 · 16-06-2026 · Gewijzigd termijnbedrag direct laten ingaan

**Voorstel.** Een gewijzigd termijnbedrag direct laten ingaan, ook voor de incasso van de lopende maand.
**Besluit.** **Afgewezen.** Een gewijzigd termijnbedrag gaat in op de eerste dag van de volgende maand.
**Aanleiding.** De incassobestanden voor de lopende maand liggen dan vaak al bij de bank.

### B-10 · 28-09-2026 · Migratie naar het nieuwe klantsysteem

**Besluit.**
- Wattson stapt op **2 oktober 2026** over op het nieuwe klantsysteem.
- Jaarafrekeningen die vóór die datum zijn opgemaakt, blijven in het oude systeem en zijn niet in het portaal te zien. De afrekendatum van de klant is bij de migratie wel doorgeschoven.
- Verbruiksgegevens zijn in het portaal en de API beschikbaar vanaf **1 september 2025**. Ook een proefafrekening kan niet vóór 1 september 2025 beginnen.

**Aanleiding.** Oudere meetgegevens zijn niet betrouwbaar gemigreerd.

### B-11 · 12-10-2026 · Lengte proefafrekening

**Besluit.** Een proefafrekening mag maximaal **731 dagen** lang zijn.
**Aanleiding.** Klanten willen twee jaar met elkaar kunnen vergelijken.
