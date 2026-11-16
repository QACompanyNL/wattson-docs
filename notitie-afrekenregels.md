# Notitie afrekenregels klantsysteem

*Afdeling Finance & Billing · versie 2.3 · 15 september 2026*
*Voor: productteam Wattson Mijn, klantenservice*

Deze notitie beschrijft hoe het klantsysteem afrekent. De bedragen (tarieven, netbeheerkosten, energiebelasting, vermindering, terugleververgoeding) en de feestdagen staan op het **tariefblad**; deze notitie verwijst daarnaar. Alle tarieven op het tariefblad zijn exclusief 21% btw.

## 1. Waar gelden deze regels

De regels gelden voor de jaarafrekening, de eindafrekening en de proefafrekening. Een proefafrekening volgt exact dezelfde regels als de jaarafrekening.

## 2. Tarieven toepassen

- Een prijs geldt vanaf de ingangsdatum (inclusief) tot de volgende ingangsdatum. Vaste contracten hebben één prijs voor de hele looptijd; het variabele contract heeft een prijshistorie.
- Vaste leveringskosten worden per aansluiting per dag in rekening gebracht (elektriciteit en gas elk apart). Netbeheerkosten zijn een dagtarief per aansluiting, afhankelijk van de capaciteit.

## 3. Normaal en dal

Voor slimme meters met twee telwerken bepaalt Wattson zelf per uur of het verbruik onder normaal of dal valt:

- **Dal** geldt op werkdagen (maandag t/m vrijdag) van **23:00 tot 07:00**.
- **Dal** geldt de **hele dag** op zaterdag, zondag en op de feestdagen van het tariefblad.
- **Normaal** geldt op alle andere momenten.
- Een uur hoort bij de periode waarin het uur **begint**. Het uur 23:00–00:00 op een werkdag is dus dal; het uur 07:00–08:00 is normaal.
- Op een **feestdag** is het hele etmaal (00:00–24:00) dal, ook als de feestdag op een werkdag valt.

**Zomer- en wintertijd.** Op de dag dat de zomertijd ingaat (laatste zondag van maart) heeft het etmaal **23 uur**; op de dag dat de wintertijd ingaat (laatste zondag van oktober) **25 uur**. Elk uur verbruik wordt precies **één keer** getoond en afgerekend. Op een dag van 25 uur komt het uur 02:00–03:00 dus twee keer voor (in het uuroverzicht van het portaal gemarkeerd als "(wintertijd)" voor het tweede uur), en beide uren tellen mee in het dagtotaal en in de afrekening.

## 4. Verbruik bepalen

- Bij meters zonder slimme uitlezing wordt het verbruik tussen twee opeenvolgende standen **gelijkmatig over de dagen** verdeeld. De stand op een tussenliggende dag wordt lineair geïnterpoleerd en afgerond op 3 decimalen.
- Na de laatst bekende stand wordt het verbruik geschat met het gemiddelde dagverbruik over alle standen van die meter. Zulke schattingen worden alleen in afrekeningen gebruikt.
- **Meterwissel.** Bij een meterwissel registreert de beheerder de eindstand van de oude meter en de beginstand van de nieuwe meter op de wisseldatum. Het verbruik is de som van het verbruik op beide meters.
- Bij een meteromloop telt het verbruik over de omloop mee zoals beschreven in de story over meteromloop.

## 5. Afronding en btw

- Hoeveelheden worden berekend in kWh/m³ met 3 decimalen.
- Elke factuurregel: **bedrag = hoeveelheid × tarief**, afgerond op hele centen (rekenkundig: een halve cent wordt van nul af afgerond).
- **Btw per regel** = 21% van het regelbedrag, afgerond op hele centen. Dit geldt ook voor negatieve regels (saldering, vermindering energiebelasting).
- Totaal = som van de regelbedragen + som van de btw-bedragen.

## 6. Periode en dagen

- Een afrekenperiode loopt van een begindatum tot en met een einddatum. Het verbruik over de periode is de (geïnterpoleerde) stand aan het begin van de dag na de einddatum min de stand aan het begin van de begindatum.
- Een aansluiting telt alleen mee voor de dagen waarop zij actief was.
- Vaste leveringskosten en netbeheerkosten worden per dag berekend: aantal dagen × dagtarief.

## 7. Prijswijzigingen tijdens de periode

- Wijzigt een tarief tijdens de afrekenperiode, dan geldt de **oude prijs voor verbruik vóór de ingangsdatum** en de **nieuwe prijs voor verbruik vanaf de ingangsdatum**.
- Bij **slimme meters** wordt het werkelijke verbruik vóór en na de ingangsdatum gebruikt.
- Bij **meters zonder slimme uitlezing** wordt het verbruik **naar rato van het aantal dagen** verdeeld (hoofdstuk 4).
- Op de afrekening staat per prijsperiode een aparte regel.

## 8. Energiebelasting

- Energiebelasting is progressief: het verbruik wordt per kalenderjaar per aansluiting over schijven verdeeld, en elke kWh of m³ wordt belast tegen het tarief van de schijf waarin hij valt. Schijven en tarieven: zie tariefblad.
- In een afrekenperiode wordt energiebelasting per aansluiting per **kalenderjaardeel** berekend. Een periode van 1 oktober 2025 t/m 30 september 2026 bestaat uit een deel 2025 (92 dagen) en een deel 2026 (273 dagen).
- De schijfgrenzen worden naar rato van het aantal dagen van dat deel verdeeld: grens × dagen / dagen in het jaar, afgerond op hele kWh of m³.
- Het belaste verbruik van een jaardeel wordt vanaf 0 over de (verdeelde) schijven verdeeld; elke kWh wordt belast tegen het tarief van de schijf waarin hij valt.
- Het belaste verbruik is het verbruik na saldering (hoofdstuk 10).

## 9. Vermindering energiebelasting

- De vermindering geldt per elektriciteitsaansluiting per kalenderjaar (niet voor gas). Jaarbedragen: zie tariefblad.
- Per elektriciteitsaansluiting, per kalenderjaardeel: jaarbedrag × aantal dagen dat de aansluiting in dat deel actief was / aantal dagen in het jaar, afgerond op centen. Dit is een negatieve regel waarover ook btw wordt verrekend.
- Dit geldt ook voor een klant die halverwege het jaar klant is geworden: hij krijgt de vermindering alleen voor de dagen vanaf zijn startdatum (**naar rato per dag**).

## 10. Teruglevering en saldering

- **Saldering.** Teruglevering wordt verrekend met verbruik **binnen hetzelfde kalenderjaar** (binnen de afrekenperiode). Eerst per telwerk: teruglevering normaal met verbruik normaal, teruglevering dal met verbruik dal. Blijft er op één telwerk teruglevering over terwijl er op het andere nog verbruik is, dan wordt dat ook verrekend.
- Gesaldeerde kWh worden gecrediteerd tegen het leveringstarief van het verbruik dat ze wegstrepen (regel "Saldering teruglevering").
- **Overschot.** Wordt er in een kalenderjaardeel meer teruggeleverd dan verbruikt, dan wordt het overschot vergoed met de **terugleververgoeding** van het tariefblad, niet tegen het leveringstarief.
- **Einde saldering.** De salderingsregeling eindigt op **1 augustus 2026** (de laatste salderingsdag is 31 juli 2026). Voor verbruik en teruglevering vanaf 1 augustus 2026 geldt: al het verbruik wordt volledig in rekening gebracht en alle teruglevering krijgt de terugleververgoeding.
- Een afrekenperiode die over 1 augustus 2026 heen loopt, wordt **gesplitst**: tot en met 31 juli wordt gesaldeerd, vanaf 1 augustus niet meer.

## 11. Dynamische contracten

- De klant betaalt per uur: verbruik × (uurprijs + inkoopvergoeding). Over het totaal (uurprijs én inkoopvergoeding) wordt 21% btw berekend.
- Op de afrekening staan twee regels per periode: "Elektriciteit dynamisch (uurprijzen)" (som van verbruik × uurprijs over alle uren, afgerond op centen) en "Inkoopvergoeding dynamisch" (totaal kWh × inkoopvergoeding). Beide regels krijgen btw.
- Uurprijzen kunnen **negatief** zijn (bijvoorbeeld op zonnige weekenddagen). Negatieve prijzen worden **doorgegeven**: een uur kan dus negatieve kosten hebben.
- Energiebelasting, vaste leveringskosten, netbeheerkosten en vermindering energiebelasting gelden zoals bij de andere contracten.

## 12. Volgorde van de regels

Per aansluiting, in deze volgorde: levering (per telwerk en prijsperiode), saldering, terugleververgoeding, vaste leveringskosten, netbeheerkosten, energiebelasting per jaardeel en schijf, vermindering energiebelasting per jaardeel.

## 13. Termijnbedrag en incasso

- De klant betaalt maandelijks een termijnbedrag, dat op de **28e** van de maand wordt geïncasseerd.
- **Geadviseerd bedrag** = verwachte jaarkosten **inclusief btw** / 12, **naar boven afgerond op hele euro's**. De verwachte jaarkosten zijn de kosten volgens deze regels over de afgelopen 365 dagen (tot en met gisteren), omgerekend naar 365 dagen als de klant korter klant is. Het geadviseerde bedrag is minimaal € 10.
- **Mislukte incasso's.** Een incasso kan mislukken. Het bedrag blijft dan verschuldigd en wordt in de afrekening apart vermeld (hoofdstuk 15).

## 14. Jaarafrekening

- Elke klant heeft een afrekendatum. Op of na die datum maakt de beheerder de jaarafrekening op (los of in een batch).
- De afrekenperiode loopt van 12 maanden vóór de afrekendatum tot en met de dag vóór de afrekendatum (of vanaf de startdatum als de klant korter klant is).
- Na de jaarafrekening schuift de afrekendatum een jaar op, krijgt de klant een e-mail, en wordt het voorgestelde termijnbedrag het nieuwe termijnbedrag vanaf de eerste dag van de volgende maand.

## 15. Saldo en termijnen

- **Saldo** = totale kosten incl. btw − **ontvangen** termijnbedragen. Alleen incasso's met vervaldatum binnen de periode die daadwerkelijk zijn geïnd, tellen mee.
- Mislukte incasso's worden apart vermeld als "niet geïnd – nog verschuldigd" en worden **niet** van de kosten afgetrokken.
- Een positief saldo is te betalen door de klant; een negatief saldo wordt terugbetaald (creditfactuur).

## 16. Voorstel nieuw termijnbedrag

Voorstel = totale kosten **inclusief btw** van de afrekenperiode × 365 / aantal dagen van de periode / 12, naar boven afgerond op hele euro's, minimaal € 10.

## 17. Opzegvergoeding

Na de bedenktijd betaalt de klant bij het beëindigen van een **vast** contract een opzegvergoeding van **€ 50 per resterend jaar**, naar rato per **begonnen** maand: € 50 × resterende maanden / 12, afgerond op centen, plus 21% btw. De resterende looptijd loopt van de gewenste einddatum tot en met de einddatum van het contract; een begonnen maand telt als hele maand. Variabele en dynamische contracten kunnen altijd kosteloos worden beëindigd.

---

## Bijlage: rekenvoorbeelden

De voorbeelden gebruiken fictieve klanten en de tarieven van het tariefblad. Ze laten zien hoe de regels worden toegepast; ze dekken niet elke situatie.

### A. Afronding en btw per regel

Vast 1 jaar, enkel tarief, 31 dagen, 245,678 kWh, netbeheer 1x25A.

| Regel | Hoeveelheid | Tarief | Bedrag | Btw (21%) | Totaal |
|---|---|---|---|---|---|
| Elektriciteit enkeltarief | 245,678 kWh | € 0,2710 | € 66,58 | € 13,98 | € 80,56 |
| Vaste leveringskosten | 31 dagen | € 0,2300 | € 7,13 | € 1,50 | € 8,63 |
| Netbeheerkosten (1x25A) | 31 dagen | € 0,3450 | € 10,70 | € 2,25 | € 12,95 |

245,678 × 0,2710 = 66,578738 → € 66,58; btw 66,58 × 0,21 = 13,9818 → € 13,98. Het totaal is de som van de afgeronde regels, niet 21% over het afgeronde totaal.

### B. Energiebelasting over twee kalenderjaren

Vast 1 jaar, enkel tarief, periode 1 juli 2025 t/m 30 juni 2026 (365 dagen), 3.650 kWh tussen de standen op 1-7-2025 en 1-7-2026, dus 10 kWh per dag.

- Jaardeel 2025: 184 dagen → 1.840 kWh. Jaardeel 2026: 181 dagen → 1.810 kWh.
- Schijfgrenzen 2025: 2.900 × 184/365 = 1.461,92 → **1.462**; 10.000 × 184/365 = 5.041,10 → 5.041.
- Schijfgrenzen 2026: 2.900 × 181/365 = 1.438,08 → **1.438**; 10.000 × 181/365 = 4.958,90 → 4.959.

| Regel | Hoeveelheid | Tarief | Bedrag | Btw |
|---|---|---|---|---|
| Energiebelasting 2025 schijf 1 | 1.462 kWh | € 0,1088 | € 159,07 | € 33,40 |
| Energiebelasting 2025 schijf 2 | 378 kWh | € 0,0921 | € 34,81 | € 7,31 |
| Energiebelasting 2026 schijf 1 | 1.438 kWh | € 0,1124 | € 161,63 | € 33,94 |
| Energiebelasting 2026 schijf 2 | 372 kWh | € 0,0957 | € 35,60 | € 7,48 |
| Vermindering energiebelasting 2025 | 184 dagen | € 542,50 × 184/365 | € −273,48 | € −57,43 |
| Vermindering energiebelasting 2026 | 181 dagen | € 568,20 × 181/365 | € −281,76 | € −59,17 |
