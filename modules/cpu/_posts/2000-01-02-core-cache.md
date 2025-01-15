---
title: Core & Cache
---

<div class="header1" id="top" markdown="1"># CPU Cores
</div>

In moderne CPU’s (zowel Intel, AMD als ARM) vind je doorgaans meerdere *cores* op één fysieke chip. Elke core is in feite een volledige processor, waardoor de CPU meerdere taken (threads) parallel kan verwerken. Dit resulteert in een sneller en responsiever systeem.

Voor het besturingssysteem lijkt elke core op een aparte processor. Heb je bijvoorbeeld een 8-core CPU, dan zie je in Taakbeheer (Windows) of Activiteitenweergave (macOS) acht afzonderlijke grafieken of CPU-threads. 

![Windows Task Manager met 8 cores op een CPU]({{ site.baseurl }}/img/cores.png)

<div class="note protip"><p>
Hoewel een CPU met meerdere cores één fysiek onderdeel is, bestaan er ook moederborden (voornamelijk voor servers) met meerdere *fysieke* CPU-sockets. In een typische desktop-pc heb je echter maar één CPU-socket.
</p></div>

### big.LITTLE (Heterogene Cores)
Bij recente Intel-processors (vanaf de 12e generatie ‘Alder Lake’) en bij ARM-chips (zoals Apple Silicon) kom je een **big.LITTLE**-ontwerp tegen, waarbij performance-cores (P-cores) en efficiency-cores (E-cores) samen op één chip zitten. Hierdoor kan de CPU energie besparen bij lichte taken en toch hoge prestaties leveren bij zware taken.

---

<div class="header1" id="top" markdown="1"># Hyper-Threading
</div>

**Hyper-Threading** (HT) is een technologie van Intel waarmee elke fysieke core zich presenteert als twee ‘logische’ cores (threads). Het besturingssysteem kan het verschil niet zien en ziet dus twee keer zoveel CPU’s. Bij AMD heet deze technologie **Simultaneous Multithreading (SMT)**, maar het principe is vergelijkbaar.

<div class="note protip"><p>
Hyper-Threading (of SMT) moet soms ingeschakeld worden in de UEFI/BIOS-instellingen. Je vindt meestal een optie in het <em>CPU Technology Support</em> of <em>Advanced CPU Configuration</em> menu.
</p></div>

Wanneer je Hyper-Threading activeert op een quad-core Intel CPU, herkent het besturingssysteem bijvoorbeeld acht logische processors. Hieronder zie je een schermafdruk van Windows waarin dit zichtbaar is:

![Voorbeeld van een quad-core CPU met acht logische threads dankzij Hyper-Threading]({{ site.baseurl }}/img/ht.png)

<div class="note opmerking"><p> 
Hyper-Threading zorgt niet voor een *volledige* verdubbeling van de performance, omdat de twee threads de fysieke resources van dezelfde core delen. Toch kan de algehele efficiëntie flink verbeteren, vooral bij software die goed gebruikmaakt van parallelle verwerking.
</p></div>

<div class="header1" id="top" markdown="1"># CPU Cache
</div>

Veel mensen kennen het concept *cache* al uit de webwereld: een browser onthoudt eerder opgevraagde webpagina’s, zodat ze sneller opnieuw kunnen worden geladen. De CPU gebruikt ook een cache, maar in tegenstelling tot de browsercache (die op je harde schijf staat), is CPU-cache een speciaal, snel geheugen (SRAM) dat fysiek in of dichtbij de processor is geïntegreerd. Hoe dichter bij de core en hoe sneller de cache, hoe minder de CPU hoeft te wachten op data uit het (tragere) RAM-geheugen.

<div class="header2" markdown="1">## CPU Cache types
</div>

Een moderne CPU heeft vaak meerdere niveaus cache:

- **L1-cache**  
  Dit is het *snelste* en *kleinste* stukje cache, direct gekoppeld aan elke core. Een CPU met 8 cores heeft dus 8 aparte L1-caches. Door de hoge snelheid kan de CPU extreem snel data en instructies ophalen.

- **L2-cache**  
  L2-cache is groter, maar iets langzamer dan L1. Soms heeft iedere core zijn eigen L2-cache; soms wordt deze gedeeld door een paar cores. De trend is dat L2-cache op moderne CPU’s nog steeds “per core” is, maar dat verschilt per ontwerp.

- **L3-cache**  
  L3-cache is doorgaans gedeeld door alle cores. De capaciteit kan variëren van enkele MB’s tot tientallen MB’s. Hoewel L3 iets trager is dan L2, is het nog altijd veel sneller dan het RAM. Het vormt daarmee een extra buffer om veelgebruikte data bij de hand te houden.

![Voorbeeld van de cache-hiërarchie in een CPU]({{ site.baseurl }}/img/cpucache.png)

<div class="note protip"><p>
> Sommige (vooral high-end of mobiele) CPU’s hebben ook een **L4-cache** of **eDRAM-cache**. Dit komt minder vaak voor, maar kan de performance in grafische toepassingen of complexe workloads verbeteren. Bij Apple Silicon (M1, M2) zie je bijvoorbeeld een *system-level cache* die voor alle cores beschikbaar is.
</p></div>

<div class="header2" markdown="1">## Waarom is cache zo belangrijk?
</div>

Zonder cache zou de CPU alles uit het (relatief trage) RAM moeten halen. Gezien de CPU tegenwoordig op snelheden van meerdere gigahertz werkt, kan elk beetje vertraging door het RAM een bottleneck worden. SRAM (de cache-technologie) is veel sneller, maar ook duurder en ingewikkelder te produceren. Daarom is de totale hoeveelheid cache in een CPU een compromis tussen prijs, prestatie en fysieke ruimte.

### Typische groottes
- **L1-cache**: varieert van 32KB tot 128KB per core, vaak opgesplitst in aparte secties voor data en instructies (bijv. 32KB data + 32KB instructies).  
- **L2-cache**: varieert van enkele honderden kilobytes tot een paar megabytes per core (bijv. 512KB of 1MB per core).  
- **L3-cache**: kan uiteenlopen van 2MB tot boven de 64MB, afhankelijk van het CPU-model. AMD staat bijvoorbeeld bekend om (relatief) grote L3-caches bij hun Ryzen- en EPYC-processors.

<div class="note protip"><p>
Bij het lezen van CPU-specificaties zie je soms “Total Cache” als optelsom, of juist een uitsplitsing in L1, L2 en L3. Zo kan een CPU omschreven worden als “32MB L3-cache” of “2 × 512KB L2 per core.” Let dus goed op hoe de fabrikant het communiceert en wat je precies koopt.
</p></div>
