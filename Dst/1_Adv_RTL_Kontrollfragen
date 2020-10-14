
[comment]: <> (Open the markdown window with CTRL+SHIFT+M)


# Dst
## Kontrollfragen Dst Advanced RTL
### HS 2020 - Luca Krummenacher

## CDC - Clock Domain Crossing
1. Erklären Sie das Phänomen von Metastabilen Zuständen bei Flipflops und warum
diese in der Digitalen Schaltungstechnik unerwünscht sind.
-  Bei Clockflanken kann es zu metastabilen Zuständen kommen, das ist ein
unzulässiger logischer Ausgangspegel eines FF’s (Also zwischen 0 und 1)
Diese unzulässigen Ausgangspegel können nicht korrekt weiterverarbeitet werden
und führen dabei zu Problemen.  Ausserdem ist der weiterverarbeitet Zustand
eine zufälliger Wert, also LOW oder HIGH.

2. Wann kommt es zu Metastabilen Zuständen bei Flipflops?
-  Wenn es in einer Schaltung mehrere Clocks gibt, kann es bei den Clockübergängen
 zu metastabilen Zuständen kommen. 
- Ein nicht synchronisiertes Signal kann einen unzulässigen Zustand auslösen
Innerhalb eines bestimmten Setup / Hold - Windows muss das Eingangssignal stabil
sein. Ein Wechsel in dieser Zeit bewirkt metastabile Zutände.

![](Invalid.png)

3. Wie helfen einem ein RTL Simulator oder ein Statischer Timing Analyzer bei der
 Suche nach Metastabilen Zuständen?
- Das Synthesetool muss die Anforderungen des Users kennen, damit es das Design
 nach den Anforderungen überprüfen kann. 

4. Welche Elemente der folgenden Formel kann man beeinflussen, und wie?
- Tck-Q + Tmet + Tdly < Tperiod – Tsu 

5. Welche Gefahren lauern bei SRL (Shieberegister) und Bock RAM (BRAM)?  


6. Welche Synthese Constraints sollte man bei 2-FF Synchronizer definieren?  

7. Welche Problematik kommt hinzu, wenn ganze Datenbusse synchronisiert werden müssen?  

8. Wie werden Datenbusse geeignet synchronisiert (mehrere Varianten)?  

9. Welche Synchronisationsmethoden gibt es bei den Reset-Signalen? 
- synchronisierter asynchroner reset eigener reset pro clock domain
 asynchronous assertion, synchronous  deassertion (THEY WAY TO GO!) 
intern generierter Reset



## CORDIC

1. Erklären Sie das Konzept des Cordic Algorithmus. 

2. Welche Zusammenhänge bestehen zwischen tan(φ) und 2-i?
 
3. Was hat es auf sich mit den Skalier-Faktoren 0.6073 und 1.647? 

4. Was ist der Unterschied zwischen dem Rotations-Mode und dem Vector-Mode? 

5. Was ist der Unterschied zwischen dem Zirkulären Mode und dem Linearen Mode? 

6. Wie wird ein Vektor um 90 Grad gedreht? 

7. Wie wird ein Vektor um 180 Grad gedreht? 

8. Aus welchen Elementen besteht die Hardware, um eine Cordic-Iteration zu berechnen?
 
9. Skizzieren die Hardware für eine Cordic-Iteration.
