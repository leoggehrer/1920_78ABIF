## Objektorientierung  
### Garbage Collector
**Verantwortlicher:** Engleder Michael  
- Erl�utern Sie die Arbeits- und Funktionsweise des Garbage-Collectors  
--------------
Der Garbage Collector dient zur Laufzeit einer Applikation als automatischer Speicher-Verwaltung f�r dessen zugewiesenen Heap.  
Sobald von der C# Applikation eine Klasse instanziert wurde, muss auf dem speicherbegrenzten Heap der daf�r notwendige Speicherbereich allokiert werden.  
Wird die Klasse im sp�teren Ablauf nicht mehr verwendet, so muss dieser Speicherbereich zur anderweitigen Verwendung wieder freigegeben werden.  
Dies erfolgt durch Entfernung aller Referenzen zu diesem instanzierten Object!   
Folgende Vorteile bietet der Garbage Collector:  
- C# Anwendungen ben�tigen **keine manuelle Speicherfreigabe**
- **Effiziente Zuordnung** von Objekten am Heap
- L�scht freigegebene Speicherbereiche
- Reserviert Speicherbereiche f�r k�nftige Belegungen
- Bietet Speichersicherheit, da der dem einen Objekt zugewiesener Speicher nicht von anderen Objekt verwendet werden kann
- Defragmentiert den Heap  
