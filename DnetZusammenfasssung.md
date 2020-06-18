# Dnet
Modul Digitale Netze FHNW - Zusammenfassung

## OSI LAYER

Layers |	Protocol Data Unit (PDU)
--- | ---
Layer 7 | Application	Data
Layer 6 | Presentation	Data
Layer 5 | Session	Data
Layer 4 | Transport	Segment / Datagramm
Layer 3 | Network	Packet
Layer 2 | Data Link	Frame
Layer 1 | Physical	Symbol

Remember it with the simple sentence: **P**lease **D**o **N**ot **T**hrow **S**alami **P**izza **A**way!

### Physical Layer
- Übertragung von Symbolen
- Modulation (Analog / Digital) (Bsp. 1V = logisch 1, 0V = logisch 0)
- Der Feind: Das Rauschen, SNR = Signal to Noise Ration,de: Signalrauschabstand
- Kanal: definiert die maximale physikalische Datenübertragungsrate

### Data Link
- Verarbeitung ```digital``` (keine Symbole mehr)
- Media Access Control: MAC
- Multiple Access: 1 Leitung, viele Stationen
- Carrier Sense: Sendet grad jemand? Darf jetzt gesendet werden?
- Flow Control: Bei Datenstau oder Überlastung Pause machen.
- Error Detection
- Retransmission (optional) oft nur wenn physikalische Eigenschaften schlecht sind (z.B. WiFi)
- Ack (optional)

### Network
- Addressierung von Paketen
- ... global oder lokal
- Routing von Paketen im Internet
- Strukturierung von Netzwerken (Subnet)
- Datagramme (verbindungslos)
- Error Detection

### Transport
- Datagramme, verbindungslos (UDP)
- Verbindungsorientiert (TCP)
- Zusäztlich **Ports**
- Bei TCP: timeouts, retransmit, sequencing
- Basis für praktisch alle Applikationen (im Minumum UDP)
- API praktisch immer im Betriebssystem

### Session and Presentation
- Session: Management von Token etc.
- Presentation: Datenformate mit Parser etc.

> Wird heute praktisch alles im Application Layer abgehandelt

### Application
- Interface via Sockets (```TCP``` und ```UDP```)
- Frameworks und Sprachen
- Python, C / C++, PHP, JS, Java, etc.
- HTTP (```www``` + Browser)
- SSL / TLS Security
- VPN

## Linux
- ```ls```, ```ls``` ```-al``` : Files auflisten
- ```ps```, ```ps aux``` : Prozesse anzeigen
- ```cd``` : Change Directory
- ```rm```, ```rm -r```, ☠️ ```rm -rf``` : Löschen
- ```pwd``` : Momentanes Working Directory anzeigen
- ```man``` : man pages
- ```mkdir``` : Directory erstellen
- ```mv``` : verschieben
- ```cp``` : kopieren