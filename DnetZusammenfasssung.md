# Dnet
Modul Digitale Netze FHNW - Zusammenfassung

## OSI LAYER

Layers |	Protocol | Data Unit (PDU)
--- | --- | ---
Layer 7 | Application |	Data
Layer 6 | Presentation |	Data
Layer 5 | Session	| Data
Layer 4 | Transport	| Segment / Datagramm
Layer 3 | Network	| Packet
Layer 2 | Data Link	| Frame
Layer 1 | Physical | Symbol

Remember it with the simple sentence: **P**lease **D**o **N**ot **T**hrow **S**alami **P**izza **A**way!

### Physical Layer - Layer 1
- Übertragung von Symbolen
- Modulation (Analog / Digital) (Bsp. 1V = logisch 1, 0V = logisch 0)
- Der Feind: Das Rauschen, SNR = Signal to Noise Ration,de: Signalrauschabstand
- Kanal: definiert die maximale physikalische Datenübertragungsrate
- DC-frei

### Data Link - Layer 2
- Verarbeitung ```digital``` (keine Symbole mehr)
- Media Access Control: MAC
- Multiple Access: 1 Leitung, viele Stationen
- Carrier Sense: Sendet grad jemand? Darf jetzt gesendet werden?
- Flow Control: Bei Datenstau oder Überlastung Pause machen.
- Error Detection
- Retransmission (optional) oft nur wenn physikalische Eigenschaften schlecht sind (z.B. WiFi)
- Ack (optional)

**Frame** 
- Preamble
- Header (Len, Flags)
- Payload
- Trailer (CRC, End of Frame)
- Inter Frame Spacing
  
CSMA Collision Avoidance (CSMA/CD): Basis für heutiges Ethernet



### Network - Layer 3
- Addressierung von Paketen
- ... global oder lokal
- Routing von Paketen im Internet
- Strukturierung von Netzwerken (Subnet)
- Datagramme (verbindungslos)
- Error Detection



### Transport - Layer 4
- Datagramme, verbindungslos (UDP) (User datagram protocol)
- Verbindungsorientiert (TCP) (Transmission control protocol)
- Zusäztlich **Ports**
- Bei TCP: timeouts, retransmit, sequencing
- Basis für praktisch alle Applikationen (im Minumum UDP)
- API praktisch immer im Betriebssystem

**DHCP**
Das Dynamic Host Configuration Protocol (DHCP) ist ein Kommunikationsprotokoll in der Computertechnik. Es ermöglicht die Zuweisung der Netzwerkkonfiguration an Clients durch einen Server. Verteilt Adressen für die UDP Übertragung. DHCP ist eine Layer 7 Applikation. 

**IP**
Das Internet Protocol (IP) ist ein in Computernetzen weit verbreitetes Netzwerkprotokoll und stellt die Grundlage des Internets dar. Es ist die Implementierung der Internetschicht des TCP/IP-Modells bzw. der Vermittlungsschicht (engl. Network Layer) des OSI-Modells. IP ist ein verbindungsloses Protokoll, das heißt bei den Kommunikationspartnern wird kein Zustand etabliert. 
IP kann seine Segmentgrösser regulieren (Segmentierung).

**ICMP (Internet Control Message Protocol)**
Das ICMP dient in Rechnernetzwerken dem Austausch von Informations- und Fehlermeldungen über das Internet-Protokoll in der Version 4 (IPv4). Für IPv6 existiert ein ähnliches Protokoll mit dem Namen ICMPv6. 
Ping verwendet ICMP.

**SSH** 
Secure Shell oder SSH bezeichnet ein kryptographisches Netzwerkprotokoll für den sicheren Betrieb von Netzwerkdiensten über ungesicherte Netzwerke.[1] Häufig wird es verwendet, um lokal eine entfernte Kommandozeile verfügbar zu machen, das heißt, auf einer lokalen Konsole werden die Ausgaben der entfernten Konsole ausgegeben und die lokalen Tastatureingaben werden an den entfernten Rechner gesendet. Genutzt werden kann dies beispielsweise zur Fernwartung eines in einem entfernten Rechenzentrum stehenden Servers.

### Session and Presentation - Layer 5 & 6
- Session: Management von Token etc.
- Presentation: Datenformate mit Parser etc.

> Wird heute praktisch alles im Application Layer abgehandelt

### Application - Layer 7
- Interface via Sockets (```TCP``` und ```UDP```)
- Frameworks und Sprachen
- Python, C / C++, PHP, JS, Java, etc.
- HTTP (```www``` + Browser)
- SSL / TLS Security
- VPN

**Socket (von engl. Sockel, Steckverbindung oder Steckdose)**
Ein Socket ist ein vom Betriebssystem bereitgestelltes Objekt, das als Kommunikationsendpunkt dient. Ein Programm verwendet Sockets, um Daten mit anderen Programmen auszutauschen. Das andere Programm kann sich dabei auf demselben Computer (Interprozesskommunikation) oder einem anderen, via Netzwerk erreichbaren Computer befinden. Die Kommunikation über Sockets erfolgt in der Regel bidirektional, das heißt, über das Socket können Daten sowohl empfangen als auch gesendet werden. (Server - client) für Netzwerkapplikationen.

## Linux
Linux ist der Name des Betriebssystem Kerns.
- Betriebssystem
- Entwickelt von Linus Torvalds
- Free Software (not free as in free Beer, free as in without shackles) ... Open Source
- Klon von UNIX (siehe Buchautor Andrew S. Tanenbaum + Minix)
- Verbreitet in Serversystemen
- POSIX (Portable Operating System Interface)

**Wichtige Befehle**
- ```ls```, ```ls``` ```-al``` : Files auflisten
- ```ps```, ```ps aux``` : Prozesse anzeigen
- ```cd``` : Change Directory
- ```rm```, ```rm -r```, ☠️ ```rm -rf``` : Löschen
- ```pwd``` : Momentanes Working Directory anzeigen
- ```man``` : man pages
- ```mkdir``` : Directory erstellen
- ```mv``` : verschieben
- ```cp``` : kopieren

## WIFI
- ```iwcofnig``` für allgemeine Konfiguration
- ```wpa_supplicant``` um sich mit einem AP zu assoziieren
- ```iw``` für scan / stats
- ```hostapd``` als Accesspoint betreiben

## IPV 4 Adressen

Bestehen aus **Netzteil** / **Hostteil** 

Beispiel: `192.168.1.1 / 255.255.255.0`
- Der erste Teil ist die Adresse. Der zweite Teil ist die Subnetzmaske.
- die Netzadresse ist immer die erste Adresse im Adressraum des Netzes
- die Broadcastadresse ist immer die letzte Adresse im Adressraum des Netzes
- alle Adressen dazwischen sind mögliche Hostadressen

2^(Anzahl Hostbits) = Anzahl Adressen
2(Anzahl Hostbits) - 2 = Anzahl gültige Adressen (Adressen - Host und Brodcastadresse)

IPV 4 Knappheit
  - NAT (Network Adress Translation) wandelt öffentliche Adressen (begrenzt) in private um

## ARP (Address Resolution Protocol)
Das ARP ist ein Netzwerkprotokoll, das zu einer Netzwerkadresse der Internetschicht die physische Adresse (Hardwareadresse, MAC) der Netzzugangsschicht ermittelt und diese Zuordnung gegebenenfalls in den ARP-Tabellen der beteiligten Rechner hinterlegt. 

Funktioniert nur mit IPV 4, IPV 6 verwendet Neighbor Discovery Protocol (NDP).
ARP - Packete werden nicht geroutet, sind somit für den User nicht sichtbar.
ARP löst IP Adressen auf
ARP request mit ```arping```

## Diverses

**```netstat```**
Zeigt offene Ports und Verbindungen an (gelistet nach TCP UDP)


