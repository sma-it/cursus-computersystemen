---
title: Mainboard
---

In dit hoofdstuk leer je over mainboards, inclusief de verschillende typen en hoe je de componenten kan herkennen. Een aanzienlijk deel van de hardware in een computer zit op het mainboard. Het bepaalt in grote mate de capaciteiten en de snelheid van het systeem. Het mainboard bevat ook de firmware -- wat we het *Basic Input/Output System* (BIOS) of de nieuwere *Unified Extensible Firmware Interface* (UEFI) noemen -- die nodig is om de computer te starten. Via de BIOS of UEFI kan je hardware-instellingen bekijken en aanpassen. Dit hoofdstuk toont je hoe dat moet. Je leert ook enkele problemen oplossen die verband houden met het mainboard en de BIOS/UEFI.

<div class="header1" id="top" markdown = "1"># Mainboard
</div>

Het mainboard is het belangrijkste onderdeel van je computer. Het maakt het mogelijk dat alle componenten, zoals CPU, geheugen, schijven en uitbreidingskaarten samen kunnen werken.

Mainboards worden gemaakt volgens *form factors* die de grootte en de componenten die je kan aankoppelen vastleggen. We zagen al dat de vorm van een kast bepaald wordt door de mainboards die het ondersteunt. Nu leer je meer over het mainboard zelf.

<div class="header2" markdown = "1">## Componenten herkennen
</div>

Alle relevante onderdelen van een mainboard worden voorgesteld in dit hoofdstuk. De figuur toont je een schema van een mainboard met de belangrijkste onderdelen aangeduid. Je zal die onderdelen niet op elk mainboard op dezelfde plaats tegenkomen, maar met een beetje ervaring kan je ze snel herkennen.

![image]({{ site.baseurl }}/img/motherboard.png)

*Schema van een mainboard*

1. __Connectoren en jumpers__ Connectoren zijn beschikbaar om de speaker, de ventilatoren en de aan/uit-knop op het frontpaneel aan te sluiten. Ze kunnen op verschillende plaatsen zitten.
2. __Uitbreidingsslots__ Slots voor uitbreidingen laten je toe om extra kaarten aan een mainboard toe te voegen. Verschillende soorten slots zijn mogelijk, zoals PCIe, die tegenwoordig de standaard is voor uitbreidingskaarten, waaronder videokaarten.
3. __Externe connectoren__ Deze connectoren zitten zo op het mainboard dat ze toegankelijk zijn via de achterkant van de computer. Hier vind je bijvoorbeeld uitgangen voor geluid en video, ingangen voor het toetsenbord en de muis, en meer.
4. __CPU 12V connector__ Een plug met 4 pinnen gaat van de voeding naar deze connector om stroom te voorzien voor de CPU. Op systemen met meer dan 1 CPU kunnen dit 2 plugs met 4 pinnen, of 1 plug met 8 pinnen zijn.
5. __CPU ventilator__ CPU's genereren veel hitte, dus het is standaard om er een ventilator op te zetten. Deze connector voorziet de ventilator van stroom. Deze ventilatoren werken dikwijls op variabele snelheid zodat ze sneller kunnen draaien wanneer de CPU warmer wordt.
6. __Chipset__ Dit bestaat uit een of meerdere chips die de CPU verbinden met de andere componenten van het systeem. Chipsets worden ontworpen om te kunnen werken met specifieke CPU's en zitten vast gesoldeerd op het mainboard. Ze kunnen zeer warm worden en dikwijls zitten er "heat sinks" op die de warme lucht helpen ontsnappen.
7. __CPU__ Het meeste werk in een computer wordt gedaan door de processor. Het mainboard bevat een socket waarop de CPU ingeplugd kan worden. En de CPU zelf bevat een heat sink en een ventilator.
8. __SATA connectoren__ De meeste computers bevatten tegenwoordig Serial Advanced Technology Attachment (SATA) schijven. SATA connectoren hebben een duidelijk herkenbare *L* vorm. Ze komen in verschillende versies, die je kan herkennen aan hun kleur. De kleuren zijn wel niet standaard, dus ze kunnen verschillen bij verschillende merken van mainboards.
9. __M.2 en NVMe connectors__ Moderne computers gebruiken vaak M.2 of NVMe SSD's voor snellere gegevensoverdracht. Deze worden rechtstreeks op het mainboard aangesloten en bieden aanzienlijk snellere laadtijden dan SATA-schijven.
10. __Batterij__ De batterij levert stroom aan de BIOS of UEFI zodat die bepaalde settings kan onthouden. Meestal is het een ronde batterij, maar het kan soms ook een cilinder zijn.
11. __BIOS/UEFI jumper__ Er zit vaak een jumper dicht bij de batterij. Door de twee pinnen van de jumper kort te sluiten kan je het BIOS/UEFI-wachtwoord resetten en de instellingen terugzetten naar de fabrieksstandaard.
12. __RAM__ Mainboards hebben meestal minstens 2 RAM slots, en velen hebben er vier of zes. RAM slots komen in verschillende vormen en je zal er enkel geheugen in kunnen steken dat voldoet aan de specificaties van het mainboard.
13. __P1 stroom connector__ De primaire power connector van de voeding is of een 20-pin connector, of een 24-pin connector.

<div class="header2" markdown = "1">## Afmetingen
</div>

Computer cases zijn er in heel wat afmetingen, maar voor mainboards zijn er standaarden waaraan ze dienen te voldoen. Dit zijn enkele van de meest voorkomende:

- __Advanced Technology Extended (ATX)__ Dit is de standaard sinds 1995 en ATX wordt ook vandaag nog veel gebruikt.
- __Micro-ATX (mATX of $$\mu$$ATX)__ Dit is een kleinere versie van ATX die veel voor desktop computers gebruikt wordt. Dit mainboard kan ook in een ATX case geplaatst worden en heeft dezelfde connectoren voor de voeding. Omdat het kleiner is, zijn er wel minder uitbreidingsslots.
- __ITX__ ITX mainboards komen in verschillende vormen en ontwerpen. Het zijn "embedded boards" en ze verbruiken erg weinig stroom in vergelijking met ATX borden. Ze moeten ook niet gekoeld worden door ventilatoren.
   - __Mini-ITX__ Deze worden gebruikt in home theater systemen en compacte gaming-pc's. Ze passen ook in een ATX case.
   - __Nano-ITX__ Deze borden zijn ontwikkeld voor kleinere devices zoals digitale video recorders en slimme IoT-apparaten.
   - __Pico-ITX__ Dit zijn extreem kleine mainboards die in mobiele devices gebruikt worden.
   - __Mobile-ITX__ Dit is de kleinste form factor tot hier toe. Het ontwerp dateert van 2009 en is vooral bedoeld voor medische, transport en militaire doeleinden.

![image]({{ site.baseurl }}/img/itx.png)

*ITX form factors*
