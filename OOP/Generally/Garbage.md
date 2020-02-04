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

#### Einteilung des Heap
Der Heap ist in 3 Bereiche, sogenannte "Generations" organisiert.  
**Generation 0:**  
Beinhaltet die kurzlebigsten Elemente, wie z.B. tempor�re Variablen und dieser Bereich ist f�r gew�hnlich der Kleinste aller 3 Generationen!   
Der Garbage Collector agiert in der Generation 0 am h�ufigsten.  
Sollte ein Objekt eine Garbage Collection �berstehen, so gelangt dieser "Survivor" in die n�chst h�here Generation.  
**Generation 1:**  
Dient als Puffer zwischen Generation 0 und Generation 2.  
"�berleben" diese Objekte eine Garbage Collection, so gelangen diese in die Generation 2.  
**Generation 2:**  
Ist der Bereich f�r langlebiege und gro�e Objekte.  
Eine Bereinigung durch den Garbage Collector nennt man "Full Garbage Collection" und bereinigt auch alle darunter liegenden Generationen.  

#### Was passiert w�hrend einer Garbage Collection?
1. **Marking Phase:** Alle "lebenden" Objekte werden in einer Liste zusammen gefasst.
2. **Relocating Phase:** Referenze zu den zu komprimierenden Objekte werden aktualisiert.
3. **Compacting Phase:** Der Speicher von "toten" Objekten wird freigegeben und �berlebte Objekte werden komprimiert. 