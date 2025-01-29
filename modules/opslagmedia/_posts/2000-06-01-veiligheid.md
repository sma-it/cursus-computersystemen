---
title: Veiligheid
---

<div class="header1" id="top" markdown="1"># Veiligheid en encryptie
</div>

In een wereld waarin data een van de belangrijkste bedrijfsmiddelen is geworden, is **encryptie** een cruciaal onderdeel van gegevensbescherming. Of het nu gaat om een laptop, een NAS of een externe schijf, het versleutelen van data voorkomt dat onbevoegden kunnen meekijken of bestanden kunnen misbruiken. In dit hoofdstuk bekijken we de principes van disk-encryptie, belangrijke encryptie-oplossingen en aandachtspunten bij het implementeren van encryptie.

---

<div class="header2" markdown="1">## Basisprincipes van encryptie
</div>

Bij **encryptie** (versleuteling) wordt je data onleesbaar gemaakt voor iedereen die niet de juiste sleutel heeft. Wanneer je de data wilt lezen of bewerken, moet je deze weer **decrypteren** (ontsleutelen) met dezelfde of een bijpassende sleutel.

1. **Symmetrische encryptie**  
   - Maakt gebruik van één gedeelde sleutel. Dezelfde sleutel versleutelt én ontsleutelt de data.  
   - Veelgebruikt voor volledige schijfversleuteling (bijv. AES-256).  

2. **Asymmetrische encryptie**  
   - Maakt gebruik van een *publieke* en een *private* sleutel.  
   - Ideaal voor situaties als het uitwisselen van encryptiesleutels, maar minder geschikt voor volledige schijfencryptie vanwege de hogere rekenlast.  

In de praktijk zie je dat **schijfencryptie** meestal met symmetrische encryptie werkt, omdat dat sneller is.

---

<div class="header2" markdown="1">## Disk-encryptie in de praktijk
</div>

### Besturingssysteem-gebaseerde oplossingen
- **BitLocker (Windows)**  
  - Ingebouwd in de Pro- en Enterprise-versies van Windows.  
  - Gebruikt standaard AES-encryptie en kan ook een TPM (Trusted Platform Module) gebruiken voor veilig sleutelbeheer.  
- **FileVault (macOS)**  
  - Ingebouwd in macOS. Gebruikt XTS-AES-128 (effectief AES-256) en kan een Apple T2-chip als beveiligde enclave gebruiken.  
- **Linux Unified Key Setup (LUKS)**  
  - Veelgebruikte oplossing in Linux. Integreert met dm-crypt op kernel-niveau en ondersteunt diverse cryptografische algoritmen.  

### Hardware-encryptie
- **Self-Encrypting Drives (SED)**  
  - Sommige harde schijven en SSD’s ondersteunen *TCG Opal*-standaarden. De encryptie vindt in de controller van de schijf plaats.  
  - Voordeel: Het versleutelen/ontsleutelen gebeurt in hardware, dus de CPU wordt nauwelijks belast.  
  - Nadeel: Je bent afhankelijk van de implementatie van de schijffabrikant.  

<div class="note opmerking"><p>
Sommige hardware-encryptie-implementaties bleken in het verleden kwetsbaar. Het is daarom belangrijk om firmware-updates en betrouwbare fabrikanten te gebruiken, of eventueel software-encryptie bovenop de schijf te draaien.
</p></div>

---

<div class="header2" markdown="1">## Encryptie bij externe en netwerkopslag
</div>

- **Externe USB-schijven**  
  - Kun je laten versleutelen door BitLocker To Go (Windows) of vergelijkbare software op macOS of Linux.  
  - Er zijn ook externe schijven met ingebouwde encryptie en een pincode-invoer via een klein toetsenpaneel.  

- **NAS-oplossingen**  
  - Veel NAS-systemen (Synology, QNAP, enz.) bieden volume-encryptie of mapgebaseerde encryptie.  
  - Let op bij het herstellen van een NAS: als de encryptiesleutel niet goed is opgeslagen, kan je data ontoegankelijk worden.  

- **Cloudopslag**  
  - Het is mogelijk om je bestanden lokaal te versleutelen voordat je ze naar de cloud stuurt (bijv. met tools als Cryptomator of Boxcryptor). Hierdoor is je data versleuteld, zelfs als de cloudprovider zelf geen end-to-end encryptie biedt.  

---

<div class="header2" markdown="1">## Belang van sleutelbeheer en back-ups
</div>

Encryptie is maar zo goed als het beheer van de sleutels. Als je de sleutel kwijtraakt:
- **Kun je zelf niet meer bij je eigen data**.  
- Een schijf- of systeemcrash kan dan leiden tot permanent verlies.  

<div class="note opmerking"><p>
Sla back-upcodes of herstelsleutels altijd op een veilige plek op (bijvoorbeeld in een kluis of een wachtwoordkluis zoals KeePass/1Password/Bitwarden). Bij BitLocker kun je bijvoorbeeld een herstelsleutel opslaan in je Microsoft-account of afdrukken.
</p></div>

**Regelmatige back-ups** blijven essentieel, want encryptie beschermt niet tegen hardware-uitval, brand, diefstal of onbedoelde verwijdering van bestanden. Een back-up versleutelen kan eveneens verstandig zijn om diefstal van de back-updrive tegen te gaan.

---

<div class="header2" markdown="1">## Secure Erase bij SSD’s
</div>

Wanneer je een oude schijf of SSD wilt wissen, is **Secure Erase** (of *ATA Secure Erase*) vaak de veiligste methode. Hiermee wordt:
- De schijf naar fabrieksinstellingen teruggezet, inclusief wissen van alle flash-cellen.  
- Bij hardware-encryptie kan ook simpelweg de encryptiesleutel worden overschreven, waardoor de data onleesbaar wordt.  

**Tip**: Gewone formatteer- of *delete*-commando’s verwijderen alleen de indexen naar je bestanden, niet de daadwerkelijke data. Op een SSD kan *TRIM* helpen, maar voor absolute zekerheid is een *Secure Erase* of fysieke vernietiging van de schijf betrouwbaarder.

---

<div class="note opmerking"><p>
**Kort samengevat**: Encryptie is een onmisbaar onderdeel van moderne dataveiligheid, maar het is niet voldoende zonder goed sleutelbeheer en regelmatige back-ups. Combineer encryptie, back-ups, fysieke beveiliging en up-to-date software om je data optimaal te beschermen.
</p></div>
