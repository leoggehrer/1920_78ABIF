## Objektorientierung  
### Garbage Collector
**Verantwortlicher:** Engleder Michael  
- Erl�utern Sie die Arbeits- und Funktionsweise des Garbage-Collectors  
--------------
Der Garbage Collector dient zur Laufzeit einer Applikation als automatischer **Speicher-Verwaltung** f�r dessen zugewiesenen Heap.  
Sobald von der C# Applikation eine Klasse instanziert wurde, muss auf dem speicherbegrenzten Heap der daf�r notwendige Speicherbereich allokiert werden.  
Wird diese Klasse im sp�teren Ablauf nicht mehr ben�tigt, so muss dieser Speicherbereich zur anderweitigen Verwendung wieder freigegeben werden.  
Die Freigabe erfolgt durch **Entfernung aller Referenzen** zu dem instanzierten Objekt!   
Folgende Vorteile bietet der Garbage Collector:  
- C# Anwendungen ben�tigen **keine manuelle Speicherfreigabe**
- **Effiziente Zuordnung** von Objekten am Heap zur Laufzeit
- **L�scht** Speicherbereiche freigegebener Objekte
- **Reserviert** Speicherbereiche f�r anstehende Belegungen
- Bietet **Speichersicherheit**, da der dem einen Objekt zugewiesener Speicher nicht von anderen Objekt verwendet werden kann
- **Defragmentiert** den Heap  
