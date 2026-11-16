# Productvisie Wattson Mijn & Backoffice

*Eigenaar: product owner · versie 1.4 · laatst bijgewerkt 12 juni 2025*

## Waarom

Wattson Energie vervangt het oude klantsysteem door één nieuw platform voor klanten, medewerkers en partners. Klanten regelen hun zaken zelf in *Wattson Mijn*: meterstanden doorgeven, verbruik bekijken, termijnbedrag aanpassen, facturen inzien, verhuizen en hun contract beheren. Medewerkers werken in de backoffice. Partners en klanten met eigen software gebruiken de REST API.

Het nieuwe platform moet vooral **kloppen**: een klant moet erop kunnen vertrouwen dat elke afrekening volgens de regels is opgemaakt. De afrekenregels staan in de notitie van Finance & Billing.

## Rollen en kanalen

- **Klant**: gebruikt het portaal (*Wattson Mijn*) en de API, en ziet alleen zijn eigen gegevens.
- **Beheerder**: gebruikt de backoffice. Een klant heeft geen toegang tot de backoffice.
- **Bezoeker**: ziet de publieke pagina's (tarieven, dynamische prijzen) en kan klant worden via *Aanmelden*.

## Algemene uitgangspunten

- **Tijdzone.** Alle datums en tijden zijn in Nederlandse tijd (Europe/Amsterdam), inclusief zomer- en wintertijd.
- **Vandaag.** Overal waar "vandaag" staat, wordt de applicatiedatum bedoeld. Voor testen kan de beheerder de applicatietijd verzetten.
- **Bedragen.** Bedragen staan in euro's in Nederlandse notatie: `€ 1.234,56`. Tarieven worden met 4 decimalen getoond, dynamische uurprijzen met 5.
- **Hoeveelheden.** Elektriciteit in kWh, gas in m³, beide met een decimale komma.
- **Invoer van getallen.** Bij het invoeren van meterstanden en bedragen worden zowel een komma als een punt als decimaalteken geaccepteerd (`12345,6` en `12345.6` betekenen hetzelfde). Scheidingstekens voor duizendtallen worden niet gebruikt.
- **Btw.** Op alle kosten wordt 21% btw berekend.
- **Foutmeldingen.** Bij een onverwachte fout toont de applicatie een algemene foutpagina met een referentiecode. Invoerfouten worden in het formulier zelf getoond, in het Nederlands, zonder dat ingevulde gegevens verloren gaan.
- **Privacy.** Een klant ziet alleen zijn eigen aansluitingen, meterstanden, verbruik, afrekeningen en facturen. Dat geldt voor het portaal én voor de API.
- **Historie.** Verbruiksgegevens zijn in het portaal beschikbaar vanaf 1 januari 2025.

## Klanten, adressen en aansluitingen

- Een klant heeft één of meer adressen. Op een adres zijn één of meer aansluitingen: elektriciteit en/of gas.
- Elke aansluiting heeft een **EAN-code** van 18 cijfers. Het laatste cijfer is een controlecijfer volgens de GS1-methode: tel van rechts naar links (zonder het controlecijfer) de cijfers op, afwisselend vermenigvuldigd met 3 en 1, beginnend met 3. Het controlecijfer is het getal dat de som aanvult tot een tienvoud.
- Bij het **invoeren** van een EAN-code zijn spaties toegestaan (bijvoorbeeld `871234 567890 123456`); spaties worden genegeerd. Een code met een ander aantal cijfers of een onjuist controlecijfer wordt geweigerd met een duidelijke melding.
- Elke aansluiting heeft een netbeheerder (Netvlak Beheer, Deltastroom Netwerken of Polderlijn Netbeheer) en een capaciteit (elektriciteit 1x25A t/m 3x50A, gas G4 of G6).
- **Meters.** Elektriciteitsmeters hebben één telwerk (enkel tarief) of twee telwerken (normaal en dal). Een **slimme meter** wordt elk uur automatisch uitgelezen; de klant geeft dan geen standen door. Bij een **meter zonder slimme uitlezing** geeft de klant zelf meterstanden door.
- Klanten met **zonnepanelen** hebben extra telwerken voor teruglevering (bij slimme meters: teruglevering per uur).

## Contracten

| Contract | Code | Looptijd | Prijs |
|---|---|---|---|
| Vast 1 jaar | `vast_1j` | 12 maanden | vast voor de hele looptijd |
| Vast 3 jaar | `vast_3j` | 36 maanden | vast voor de hele looptijd |
| Variabel | `variabel` | onbepaalde tijd | kan per ingangsdatum wijzigen |
| Dynamisch | `dynamisch` | onbepaalde tijd | uurprijs plus inkoopvergoeding |

- Een contract hoort bij één aansluiting. Een klant met elektriciteit en gas heeft dus twee contracten.
- De einddatum van een contract is inclusief: een contract van 1 januari 2026 tot en met 31 december 2026 duurt 12 maanden.
- Een dynamisch contract kan niet worden gecombineerd met teruglevering (zonnepanelen).
- Klanten met een vast contract krijgen een maand voor het einde van hun contract een verlengingsaanbod.
- De prijzen staan op het tariefblad.

## E-mail

Het platform verstuurt in de test- en acceptatieomgeving geen echte e-mail. Alle uitgaande e-mail (welkom, wachtwoord herstellen, termijnbedrag gewijzigd, jaarafrekening, herinnering, aanmaning, verhuisbevestiging, verlengingsaanbod, bevestiging verlenging, bevestiging beëindiging) staat in de mailbox op **`/mailbox`**, te filteren op e-mailadres.
