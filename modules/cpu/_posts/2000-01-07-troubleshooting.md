---
title: Troubleshooting
---

<div class="header1" id="top" markdown="1"># Troubleshooting
</div>

Het kan gebeuren dat je een pc moet repareren met vage of terugkerende problemen die te maken hebben met de **CPU** of **geheugen**. Soms is het duidelijk dat er hardware kapot is, maar vaak komen de problemen slechts sporadisch voor. Dat wijst vaak op **oververhitting** of **ventilatieproblemen**. Controleer daarom eerst of de koeling en airflow in de behuizing goed zijn, en verwijder stof uit ventilatoren en koellichamen.

### Mogelijke symptomen
- **Onverwachte shutdowns**  
  Als de pc zichzelf plotseling afsluit of herstart, kan hitte een oorzaak zijn. Controleer of de ventilatoren draaien en of er geen stofophopingen in de heatsink zitten.

- **System lockups**  
  Wanneer een systeem volledig vastloopt en niet meer reageert, is oververhitting óf defecte hardware vaak een verdachte.  

- **Voortdurende reboots**  
  Herstart een pc continu en is het *niet* het gevolg van een recente software-update of driverprobleem, kijk dan of er recent hardware is vervangen, en of de CPU/gpu/ram correct in hun sockets zitten.

### Andere mogelijke oorzaken
- **Power supply (PSU)**  
  Een half defecte of overbelaste voeding kan “willekeurige” crashes veroorzaken. Gebruik een multimeter of PSU-tester om te controleren of de voltages (5V, 12V, 3.3V) stabiel zijn.

- **RAM**  
  Een gedeeltelijk defect RAM-bankje kan pas voor problemen zorgen als het systeem dat specifieke geheugenadres aanspreekt. Dat kan resulteren in onverklaarbare crashes, vastlopers of zelfs een BSOD (Blue Screen of Death). Gebruik tools zoals **MemTest86** of het ingebouwde geheugencontrolehulpmiddel van het besturingssysteem (bijv. Windows Memory Diagnostics) om je RAM te testen.

> **Tip:**  
> Treedt het probleem regelmatig op bij intensieve taken (bv. gaming, video-renderen), kijk dan extra naar koeling en voeding. Gebeurt het lukraak, dan kan RAM of zelfs een falende voeding de oorzaak zijn.

<div class="header1" id="top" markdown="1"># CPU Security: Meltdown, Spectre en microcode-updates
</div>

**CPU’s** zijn enorm complex geworden. Naast snelheid en energiezuinigheid is **security** een steeds belangrijker aandachtspunt. De ontdekkingen van **Meltdown** en **Spectre** (begin 2018) maakten duidelijk dat CPU’s kwetsbaar zijn voor zogeheten *side-channel attacks*, waarbij onbedoelde informatie via timing en caches kan worden afgeleid.

<div class="header2" markdown="1">## Meltdown en Spectre
</div>

- **Meltdown**  
  - Kwetsbaarheid die vooral Intel-CPU’s trof (maar later ook op andere architecturen werd onderzocht).  
  - Maakt het mogelijk om via een timing-aanval data te lezen uit het kernelgeheugen van het besturingssysteem.  
  - Gebruikt de manier waarop CPU’s *out-of-order execution* en **speculatieve executie** toepassen.

- **Spectre**  
  - Heeft varianten die Intel-, AMD- én ARM-CPU’s treffen.  
  - Misbruikt *speculatieve executie* en *branch prediction* om data uit afgesloten geheugenruimtes te lezen.  
  - Is over het algemeen lastiger te patchen dan Meltdown en kent meerdere varianten (Spectre-v1, v2, v4).

> **Opmerking:**  
> Zowel Meltdown als Spectre vallen onder de categorie *side-channel attacks* omdat ze gebruikmaken van subtiele timingverschillen in CPU-cache of -pijplijnen. Daardoor kan een aanvaller (onder bepaalde omstandigheden) geheugen uitlezen dat hij normaal niet zou mogen zien.

---

<div class="header2" markdown="1">## Mitigaties en performance impact
</div>

### Software-patches
Besturingssystemen (Windows, Linux, macOS) hebben **kernel-patches** uitgebracht om de impact van Meltdown en Spectre te beperken. Deze patches kunnen echter een **performance-penalty** tot gevolg hebben, vooral bij oudere CPU’s en in specifieke workloads (bijvoorbeeld virtualisatie of intensieve I/O-taken).

### Microcode-updates
- **Wat is microcode?**  
  CPU’s hebben een laag tussen de hardware en de instructieset, de *microcode*. Dit is vergelijkbaar met firmware: door microcode-updates kan de fabrikant delen van de CPU-werking veranderen zonder de fysieke chip te vervangen.

- **Hoe krijg je microcode-updates?**  
  - Via het **besturingssysteem**, dat bij iedere boot de microcode laadt (Linux- en Windows-updates).  
  - Via een **BIOS- of UEFI-update** van het moederbord (hiermee wordt de microcode permanent ingebakken tot een volgende update).

- **Waarom microcode-updates?**  
  Bij **Spectre Variant 2** en andere kwetsbaarheden kon de CPU alleen deels worden afgeschermd met wijzigingen in de interne logica (zoals branch prediction-limieten). Microcode-updates kunnen zulke aanpassingen doorvoeren.

> **Let op:**  
> Een microcode-update kan prestaties beïnvloeden of compatibiliteitsproblemen veroorzaken bij oudere systemen. Het is echter vrijwel altijd raadzaam deze updates te installeren om beveiligingslekken te dichten.

---

<div class="header2" markdown="1">## Andere CPU-kwetsbaarheden
</div>

Sinds Meltdown en Spectre zijn er meer *speculative execution*-lekken ontdekt, zoals **Foreshadow**, **ZombieLoad** en **SRBDS (CROSSTalk)**. Elke keer rollen er **microcode-updates** en *softwaremitigaties* uit om deze te verhelpen. 

- **Foreshadow (L1TF)**  
  Richt zich op de L1-cache en kan data van andere processen lezen.  
- **ZombieLoad**  
  Maakt gebruik van *Microarchitectural Data Sampling* (MDS) om data uit buffers te lekken.  
- **SRBDS (Special Register Buffer Data Sampling)**  
  Gaat om lekken van gevoelige data uit speciale CPU-registers, vooral op Intel-chips.  

<div class="note opmerking"><p>
Veel van deze aanvallen vereisen <em>lokaal toegang</em> of het uitvoeren van <em>malafide code</em> op het systeem. Ze zijn dus niet zomaar op afstand uitvoerbaar. Toch vormen ze een risico voor multi-tenant-omgevingen (zoals <em>cloud servers</em>) en dienen ze serieus genomen te worden.
</p></div>

---

<div class="header2" markdown="1">## Best practices voor CPU-security
</div>

1. **Houd je besturingssysteem up-to-date**  
   Patches voor Meltdown en Spectre komen als OS-updates. Laat deze automatische updates aanstaan of voer ze regelmatig uit.

2. **Installeer BIOS/UEFI-updates**  
   Moederbordfabrikanten brengen updates uit die microcode kunnen bijwerken. Controleer de website van je moederbordfabrikant of de automatische tools.

3. **Wees alert op nieuwe kwetsbaarheden**  
   Blijf op de hoogte van securityblogs of officiële adviezen van Intel, AMD of Apple. Nieuwe lekken kunnen om extra mitigaties vragen.

4. **Balanceer security en performance**  
   Sommige mitigaties kun je in het besturingssysteem uitschakelen als je absoluut maximale prestaties nodig hebt (bijvoorbeeld in test- of gaming-omgevingen). Doe dat alleen als je het securityrisico aanvaardbaar vindt.

5. **Virtualisatie-omgevingen**  
   In multi-tenant-omgevingen (bijv. publieke cloud) zijn CPU-kwetsbaarheden extra gevaarlijk. Hypervisors en VM-architecturen moeten dan ook regelmatig gepatcht worden met de nieuwste mitigaties.
