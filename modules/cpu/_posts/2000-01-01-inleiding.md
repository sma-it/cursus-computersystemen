---
title: CPUs
---

<div class="header1" id="top" markdown="1"># De CPU: het brein van de computer
</div>

De processor, of CPU (Central Processing Unit), is het brein van de computer. Hij voert het meeste rekenwerk uit en is daarmee een van de belangrijkste factoren voor de systeemsnelheid. Over de jaren zijn CPU's flink geëvolueerd, en als informaticus is het essentieel de basisprincipes én de nieuwste ontwikkelingen te kennen.

Er zijn traditioneel twee grote spelers in de x86-CPU-markt: **Intel** en **AMD**. De laatste jaren is daar echter **Apple** bijgekomen met zijn eigen ARM-gebaseerde “Apple Silicon”-chips voor desktops en laptops. Ook andere fabrikanten, zoals Qualcomm, maken ARM-chips, maar die vind je vooral in smartphones en tablets.

- **Intel**  
  Intel heeft historisch gezien het grootste aandeel in de x86-CPU-markt. Ze produceren naast CPU’s ook andere componenten zoals netwerk- en opslaghardware.  

- **AMD**  
  AMD is Intels grootste concurrent in de x86-markt, met populaire lijnen als de Ryzen- en EPYC-processors. Daarnaast verkoopt AMD ook GPU’s (voorheen onder de merknaam Radeon) en andere chipset-onderdelen.

- **Apple (ARM-gebaseerd)**  
  Apple maakt sinds 2020 zijn eigen SoC’s (System on a Chip) onder de naam “Apple Silicon” (M1, M2, enz.). Deze chips combineren CPU, GPU en andere onderdelen op één pakket en gebruiken een ARM-architectuur. Hierdoor zijn ze energiezuinig en krachtig, maar niet verwisselbaar of te upgraden.

Het upgraden van je computer kan dus neerkomen op het vervangen van de CPU, maar de vraag is dan altijd: “Wat past er op mijn moederbord?” In de loop van deze cursus leer je waar je op moet letten, zoals socket-compatibiliteit en chipsetondersteuning, om de juiste CPU te kiezen.

<div class="note opmerking"><p>
ARM (Advanced RISC Machine) gebruikt een zogeheten *reduced instruction set* (RISC)-architectuur die doorgaans minder stroom verbruikt dan veel x86-chips. Je vindt ARM-oplossingen vooral in smartphones, tablets en in de Apple Silicon-lijn. In de meeste gevallen zijn deze SoC’s echter niet verwisselbaar, waardoor je ze niet kunt upgraden zoals x86-desktop-CPU’s.
</p></div>

<div class="header1" id="top" markdown="1"># 32-bit versus 64-bit
</div>

In de begintijd van personal computing hadden de meeste CPU’s, besturingssystemen en applicaties een 32-bit architectuur. Tegenwoordig is 64-bit echter de standaard. Toch is het nuttig om de achterliggende redenen te begrijpen en te weten hoe 32-bit en 64-bit zich tot elkaar verhouden.

- Een **64-bit CPU** kan probleemloos 64-bit én 32-bit software draaien.  
- Om een **64-bit besturingssysteem** te gebruiken, heb je een 64-bit CPU nodig.  
- Veel moderne besturingssystemen (bijvoorbeeld Windows 11) komen alleen nog in 64-bit.  
- Als je meer dan 4 GB RAM wil aanspreken, heb je een 64-bit CPU en OS nodig.

Het getal 32 of 64 verwijst naar de *address bus* van de CPU. Een 32-bit CPU heeft \(2^{32}\) mogelijke adressen (4 GB), terwijl een 64-bit CPU maar liefst \(2^{64}\) adressen (16 exabytes) kan aanspreken. Dat laatste is in de praktijk ver buiten het bereik van huidige hardware, maar zorgt voor veel meer speelruimte in de toekomst.

<div class="note opmerking"><p>
Bij een 32-bit besturingssysteem wordt een deel van de mogelijke geheugenruimte gereserveerd voor andere apparaten (bijvoorbeeld videokaarten). Daarom zie je vaak dat een 32-bit systeem met 4 GB RAM in de praktijk maar ongeveer 3,3 GB herkenbaar geheugen beschikbaar heeft.
</p></div>

In de loop der jaren zijn zowel besturingssystemen als software veel geavanceerder geworden en verbruiken ze meer geheugen. Om meer dan 4 GB RAM te kunnen gebruiken, is een 64-bit besturingssysteem onmisbaar.

### Terminologie
- **32-bit & x86**  
  Vaak worden 32-bit systemen aangeduid als *x86*, een verwijzing naar de oude Intel-processoren die eindigden op “86” (bijv. 8086, 80286, 80386, 80486). AMD-processors waren “x86-compatible” maar gebruikten andere namen.  

- **64-bit & x64**  
  Intel noemt zijn 64-bit technologie *Intel 64*, AMD noemt de hare *AMD64*, en software-ontwikkelaars verwijzen meestal naar *x64*. ARM-systemen (zoals Apple Silicon en smartphones) zijn eveneens 64-bit, maar hanteren een andere instructieset (AArch64).

<div class="note opmerking"><p>
Een 64-bit besturingssysteem vereist een 64-bit CPU. Het maakt daarbij niet uit of dat een Intel- of AMD-processor is (of zelfs een ARM64-CPU, mits de software daarvoor geschikt is).
</p></div>









