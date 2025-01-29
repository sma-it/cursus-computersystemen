---
title: dataherstel
---

<div class="header1" id="top" markdown="1"># Dataherstel (Data Recovery) & Levensduur SSD’s
</div>

In dit hoofdstuk gaan we dieper in op twee gerelateerde thema’s: **dataherstel** (het terughalen van verloren of beschadigde bestanden) en de **levensduur** van opslagmedia — met name SSD’s, die een ander slijtage- en falingsprofiel hebben dan traditionele harde schijven (HDD’s).

---

<div class="header2" markdown="1">## Dataherstel (Data Recovery)
</div>

**Dataherstel** richt zich op het herstellen van bestanden die om uiteenlopende redenen niet langer toegankelijk zijn. Mogelijke oorzaken zijn onder andere:
- Onbedoelde verwijdering of formattering  
- Falen van hardware (HDD/SSD)  
- Bestandscorruptie door stroomuitval of systeemcrash  
- Malware of ransomware-aanvallen  

### Recovery bij HDD’s

1. **Softwarematige recovery**  
   - Programma’s zoals *Recuva*, *PhotoRec*, *EaseUS Data Recovery Wizard*, *TestDisk* enz.  
   - Werken door nog aanwezige ‘restanten’ van bestanden op de schijf te analyseren, zelfs als de bestandsindex (bijv. MFT bij NTFS) is gewist.  
2. **Fysieke/hardwarematige problemen**  
   - Als de HDD mechanisch defect is (bijv. een vastzittende leeskop), kan een professioneel dataherstelbedrijf de schijf in een cleanroom openen en proberen de data te redden. Dit is vaak erg duur.  

### Recovery bij SSD’s

1. **TRIM en garbage collection**  
   - SSD’s verwijderen ongebruikte data proactief in de achtergrond (TRIM). Daardoor is het lastiger om per ongeluk gewiste data te herstellen, omdat de controller die blokken snel kan overschrijven.  
2. **Slijtage en defecte cellen**  
   - Slijtage kan leiden tot bad blocks. Vaak wordt dit gemaskeerd door de SSD-controller, maar als er ernstige schade optreedt, is het soms onomkeerbaar.  
3. **Professioneel herstel**  
   - Ook hier kunnen gespecialiseerde bedrijven proberen de NAND-chips direct uit te lezen. Dit is doorgaans complexer en prijziger dan bij HDD’s.  

### Best practices voor dataherstel

- **Stop meteen met schrijven** op het medium zodra je merkt dat je data kwijt bent. Elke nieuwe schrijfactie kan oude data overschrijven.  
- **Gebruik recovery-software** van een ander opslagmedium (bijv. op een usb-stick of aparte schijf).  
- **Professioneel lab** inschakelen als de data zeer kostbaar is of bij grote fysieke schade.  

<div class="note opmerking"><p>
Zelfs als dataherstel mogelijk lijkt, is het succes vaak afhankelijk van hoe snel je stopt met verdere acties op die schijf. Bij SSD’s is de tijdskritische factor nóg groter door TRIM en garbage collection. 
</p></div>

---

<div class="header2" markdown="1">## Levensduur van SSD’s
</div>

Een **Solid State Drive** kent een ander slijtagescenario dan een traditionele HDD. Waar HDD’s vooral last krijgen van mechanische slijtage (motoren, lagers, lees/schrijfkoppen), hebben SSD’s te maken met **flash-slijtage**: elke flashcel kan maar een beperkt aantal schrijfcycli doorstaan.

### Flashgeheugen en schrijfcycli

1. **NAND-technologie**  
   - SLC (Single-Level Cell): hoogste betrouwbaarheid, duurder.  
   - MLC (Multi-Level Cell): 2 bits per cel, gangbare pro/enterprise-lijn.  
   - TLC (Triple-Level Cell): 3 bits per cel, veelgebruikte consumenten-SSD.  
   - QLC (Quad-Level Cell): 4 bits per cel, lagere kosten, maar ook lagere write endurance.  

2. **TBW (Terabytes Written)**  
   - Fabrikanten geven vaak een *TBW*-specificatie aan: hoeveel terabytes er naar de SSD geschreven mogen worden voordat de schijf (statistisch gezien) onbetrouwbaar wordt.  
   - Bijv. een 500 GB-SSD kan een TBW van 150 TB hebben, wat voor veel thuissituaties voldoende is voor meerdere jaren.  

3. **Wear-leveling & Overprovisioning**  
   - **Wear-leveling**: De SSD-controller verdeelt schrijfopdrachten over alle cellen, om vroegtijdige slijtage van bepaalde cellen te voorkomen.  
   - **Overprovisioning**: Een deel van de SSD-capaciteit is gereserveerd voor systeemfuncties en vervanging van slechter wordende cellen.  

### Praktische tips voor een langere SSD-levensduur

- **Voldoende vrije ruimte** aanhouden (minstens 10-20% ongebruikt), zodat de SSD-controller kan doorwerken met wear-leveling en garbage collection.  
- **TRIM inschakelen** (standaard actief in moderne besturingssystemen).  
- **Geen defragmentatie** gebruiken: bij SSD’s levert het geen winst op en kan het extra slijtage veroorzaken.  
- **Firmware-updates**: Houd de firmware van je SSD bij, want updates kunnen bugs fixen en de levensduur verlengen.

<div class="note opmerking"><p>
De levensduur van een SSD hangt sterk af van het gebruikspatroon. Bij normaal kantoor- en thuisgebruik gaan moderne SSD’s vaak langer mee dan de verwachte gebruiksduur van de computer zelf. Bij intensieve server- of videobewerkingsworkloads (honderden GB’s aan dagelijkse writes) is de slijtage groter. 
</p></div>

---

<div class="header2" markdown="1">## Conclusie
</div>

- **Dataherstel** is een vak apart. Bij kleine softwarematige problemen kun je met recovery-software vaak (een deel van) de data redden. Bij grote fysieke schade is professionele hulp nodig.  
- **SSD’s slijten anders dan HDD’s**, maar door wear-leveling, overprovisioning en TRIM kunnen SSD’s in gewone gebruiksscenario’s jarenlang meegaan zonder problemen.  
- **Regelmatige back-ups** blijven de beste verzekering tegen dataverlies. Hoe geavanceerd je opslagtechnologie ook is, een kopie op een aparte locatie is onmisbaar voor de veiligheid van je data.
