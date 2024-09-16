---
title: Numerieke systemen
---

<div class="header1" id="top" markdown = "1"># Numerieke systemen
</div>

Ook al kan een computer nog zo veel, het blijft een dom ding. Een computer kan enkel met nummers werken. En zelfs niet alle nummer: enkel nul en één komen in aanmerking. Alles in het geheugen of op de harde schijf is een (zeer lange) reeks nullen en eentjes.

Natuurlijk kan een computer dat dan wel heel erg snel. Vraag hem om twee getallen te vermenigvuldigen en dat gebeurt in een fractie van een seconde. Ook al moeten die getallen eerst omgezet worden naar nullen en eentjes, dan verwerkt worden, dan terug omgezet worden naar iets dat mensen kunnen lezen.

Daarom is het ook belangrijk dat je als informaticus weet hoe een computer rekent. Mensen gebruiken decimale cijfers om te rekenen. We kennen de betekenis van de nummers 0 tot 9. En na 9 komt 10. Dit noemen we een numeriek systeem met basis 10, omdat er 10 cijfers worden gebruikt.

Wanneer je een getal ziet zoals 2357, dan weet je dat het bestaat uit:

| Decimale getallen&nbsp; &nbsp; 	| 10<sup>3</sup>&nbsp; &nbsp; 	| 10<sup>2</sup>&nbsp;&nbsp; 	| 10<sup>1</sup>&nbsp;&nbsp; 	| 10<sup>0</sup>&nbsp; &nbsp; 	|
|-------------------	|------	|------	|------	|------	|
| Decimale waarde   	| 1000 &nbsp; &nbsp;	| 100  	| 10   	| 1    	|
| Cijfer            	| 2    	| 3    	| 5    	| 7    	|
| Berekende waarde &nbsp; &nbsp; 	| 2000 &nbsp; &nbsp;	| 300  	| 50   	| 7    	|

* Het cijfer helemaal links is een duizendtal, of ook wel __10<sup>3</sup>__. Want __10 * 10 * 10 = 1000__. In dit geval staat er een twee, dus die staat voor 2000.
* Het tweede cijfer is een honderdtal, of __10<sup>2</sup>__. Het cijfer 3 betekent __3*100__, dus 300.
* Op de volgende positie staat een tiental, of __10<sup>1</sup>__. Het cijfer 5 betekent __5*10__, dus 50.
* Helemaal rechts staan de eenheden, dus __10<sup>0</sup>__. Het cijfer blijft dus 7.

Wanneer je alle cijfers optelt (__2000+300+50+7__) dan krijg je 2357. Als je dit getal ziet, dan denk je er waarschijnlijk niet zo over na, maar zo komen we aan die waarde.

Getallen met een basis 10 zijn niet handig voor computers. Ze laten heel wat plaats verloren gaan. Daarom gebruiken computers andere systemen, zoals binair en hexadecimaal.


<div class="header2" markdown = "1">## Binaire getallen
</div>

Binaire getallen hebben een basis 2. In plaats van de cijfers 0 tot en met 9, bestaan ze uit enkel 0 en 1. 

Als je nu een opnieuw een getal van vier cijfers neemt, zoals 1001, dan kan je dat op een gelijkaardige manier berekenen.

| Decimale getallen&nbsp; &nbsp; 	| 2<sup>3</sup>&nbsp; &nbsp; 	| 2<sup>2</sup>&nbsp;&nbsp; 	| 2<sup>1</sup>&nbsp;&nbsp; 	| 2<sup>0</sup>&nbsp; &nbsp; 	|
|-------------------	|------	|------	|------	|------	|
| Decimale waarde   	| 8 &nbsp; &nbsp;	| 4  	| 2   	| 1    	|
| Cijfer            	| 1    	| 0    	| 0    	| 1    	|
| Berekende waarde &nbsp; &nbsp; 	| 8 &nbsp; &nbsp;	| 0  	| 0   	| 1    	|

* Het cijfer helemaal links is een 8, of ook wel __2<sup>3</sup>__. Want __2 * 2 * 2 = 8__. In dit geval staat er een 1, dus die staat voor 8.
* Het tweede cijfer is __2<sup>2</sup>__, of 4. Het cijfer 0 betekent __0*4__, dus 0.
* Op de volgende positie staat 2, of __2<sup>1</sup>__. Het cijfer 0 betekent __0*2__, dus 0.
* Helemaal rechts staat 1, want elk getal tot met macht nul is 1. Het cijfer 1 blijft dus 1.

Wanneer we alle delen optellen krijgen we dus __8+0+0+1__, ofwel __9__. Het binaire getal __1001__ heeft dus de decimale waarde __9__.

<div class="header2" markdown = "1">## Hexadecimale getallen
</div>

Alhoewel binaire getallen goed werken voor computers zijn ze voor mensen iets te moeilijk. Als je iemand zegt dat het nummer je locker *201* is, dan is dat eenvoudig. Maar *1100 1001*, dat ligt wellicht iets moeilijker. Je zou echter ook de hexadecimale vorm kunnen gebruiken: *C9*.

Hexadecimalen gebruiken de cijfers `0 - 9` en de letters `A - F` om een getal weer te geven. We rekenen dus met een basis 16. Voor mensen is dit al een stuk eenvoudiger en voor een computer is het ook makkelijker om te zetten naar een binair stelsel.


<div class="note opmerking">
<p>Wanneer we binaire getallen groeperen, dan is het de gewoonte om groepen van 4 cijfers te scheiden met een spaties. We doen dat soms ook met decimale getallen. In de Engelstalige wereld wordt 123456789 meestal geschreven als 123,456,789. In Vlaanderen hebben we het om een of andere reden weer fout begrepen en schrijven we 123.456.789. In beide gevallen is het op deze manier eenvoudig om te zien dat het om 123 miljoen gaat. Zo schrijven we dus ook 1100 1001 in plaats van 11001001.
</p></div> 

* 123456789 wordt 123.456.789
* 10A5D3 wordt 10 A5 D3
* 11001001 wordt 1100 1001

Het binaire nummer *1100 1001* kan je als *C9* schrijven omdat *1100* gelijk is aan de hexadecimale *C* en *1001* gelijk aan de hexadecimale *9*. De tabel hieronder toont alle decimale, binaire en hexadecimale waarden:

| Decimaal | Binair | Hexadecimaal |
|----------|--------|--------------|
| 0        | 0000   | 0            |
| 1        | 0001   | 1            |
| 2        | 0010   | 2            |
| 3        | 0011   | 3            |
| 4        | 0100   | 4            |
| 5        | 0101   | 5            |
| 6        | 0110   | 6            |
| 7        | 0111   | 7            |
| 8        | 1000   | 8            |
| 9        | 1001   | 9            |
| 10       | 1010   | A            |
| 11       | 1011   | B            |
| 12       | 1100   | C            |
| 13       | 1101   | D            |
| 14       | 1110   | E            |
| 15       | 1111   | F            |

<div class="note opmerking">
<p>Hexadecimale getallen zijn niet hoofdlettergevoelig. Een hoofdletter C is hetzelfde als een kleine letter c, en beiden betekenen binair 1100. Ook zal een computer een hexadecimaal getal dikwijls laten voorafgaan door 0x om aan te geven dat het om een hexadecimaal getal gaat. Zo zal Windows bij een crash een blauw scherm tonen met een code zoals STOP Error 0x0000002E, of dus de hexadecimale code 2E. (In dit geval duidt de code op een probleem met het geheugen.)
</p></div> 

Een plaats waar hexadecimalen dikwijls gebruikt worden is het netwerk. Zo heeft elke netwerkkaart een 48-bit uniek adres (MAC-id) zoals 6C-62-6D-BA-73-6C. Ook kleuren in HTML notatie zijn hexadecimalen, bijvoorbeeld \#FFFFFF voor wit en \#000000 voor zwart.

<div class="header2" markdown = "1">## Bits versus Bytes
</div>

Een enkel binair cijfer noemen we een `bit`, en acht bits maken een  `byte`. En met bytes rekenen we dikwijls verder volgens de formule  `2<sup>10</sup>`, of `2*2*2*2*2*2*2*2*2*2`. Wanneer je dat uitrekent zal je zien dat het resultaat `1024` is, ofwel *ongeveer* duizend. Hier enkele andere mogelijkheden:

* __KB__ Ongeveer duizend bytes (2<sup>10</sup>)
* __MB__ Ongeveer duizend KB of een miljoen bytes (2<sup>20</sup>)
* __GB__ Ongeveer duizend MB of een miljard bytes (2<sup>30</sup>)
* __TB__ Ongeveer duizend GB of een biljoen bytes (2<sup>40</sup>)

<div class="note protip"><p>
Rekenen met binaire of hexadecimale getallen is niet zo eenvoudig. Wanneer je de calculator op je laptop gebruikt, dan kan je via het menu overschakelen naar *programmer* mode.
</p></div>