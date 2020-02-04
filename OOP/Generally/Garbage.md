## Objektorientierung  
### Garbage Collector
**Verantwortlicher:** Engleder Michael  
- Erläutern Sie die Arbeits- und Funktionsweise des Garbage-Collectors  
--------------
Der Garbage Collector dient zur Laufzeit einer Applikation als automatischer **Speicher-Verwaltung** für dessen zugewiesenen Heap.  
Sobald von der C# Applikation eine Klasse instanziert wurde, muss auf dem speicherbegrenzten Heap der dafür notwendige Speicherbereich allokiert werden.   
Wird diese Klasse im späteren Ablauf nicht mehr benötigt, so muss dieser Speicherbereich zur anderweitigen Verwendung wieder freigegeben werden.   
Die Freigabe erfolgt durch **Entfernung aller Referenzen** zu dem instanzierten Objekt!    
Folgende Vorteile bietet der Garbage Collector:  
- C# Anwendungen benötigen **keine manuelle Speicherfreigabe**
- **Effiziente Zuordnung** von Objekten am Heap zur Laufzeit
- **Löscht** Speicherbereiche freigegebener Objekte
- **Reserviert** Speicherbereiche für anstehende Belegungen
- Bietet **Speichersicherheit**, da der dem einen Objekt zugewiesener Speicher nicht von anderen Objekt verwendet werden kann
- **Defragmentiert** den Heap 

#### Einteilung des Heap
Der Heap ist in 3 Bereiche, sogenannte "Generations" organisiert.  
**Generation 0:**  
Beinhaltet die kurzlebigsten Elemente, wie z.B. temporäre Variablen und dieser Bereich ist für gewöhnlich der Kleinste aller 3 Generationen!   
Der Garbage Collector agiert in der Generation 0 am häufigsten.  
Sollte ein Objekt eine Garbage Collection überstehen, so gelangt dieser "Survivor" in die nächst höhere Generation.  
**Generation 1:**  
Dient als Puffer zwischen Generation 0 und Generation 2.  
"Überleben" diese Objekte eine Garbage Collection, so gelangen diese in die Generation 2.  
**Generation 2:**  
Ist der Bereich für langlebiege und große Objekte.  
Eine Bereinigung durch den Garbage Collector nennt man "Full Garbage Collection" und bereinigt auch alle darunter liegenden Generationen.  

#### Was passiert während einer Garbage Collection?
1. **Marking Phase:** Alle "lebenden" Objekte werden in einer Liste zusammen gefasst.
2. **Relocating Phase:** Referenze zu den zu komprimierenden Objekte werden aktualisiert.
3. **Compacting Phase:** Der Speicher von "toten" Objekten wird freigegeben und überlebte Objekte werden komprimiert. 