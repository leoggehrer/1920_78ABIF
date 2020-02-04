# Terms
Autor: Markus Freudenthaler
### Erkl�ren Sie die folgenden abstrakten Datenstrukturen:
Der Begriff Datenstrukture wird oft gleichbedeutend mit Datentyp gebraucht.
Von Datenstrukturen spricht man, wenn aus einfachen Datentypen zusammengesetzte Datentypen aufgebaut werden.
Soll hei�en eine Datenstruktur dient zur Speicherung und Organisation von Daten. Durch Operatoren wird festgelegt wie auf die Daten der Datenstruktur zugegriffen werden kann.
Da der Zugriff nur �ber die festgelegten Operationen erfolgt, sind die Daten nach au�en gekapselt. 

#### - Stack:
  ![alt text](StackImplement.jpg "Stack Implement") 

  - Ein Stack funktioniert in C# nach den last in first out (LIFO) Prinzip.
  - Im deutschen hei�t Stack Stapel oder Kellerspeicher.
  - Die meisten Microprozessoren unterst�tzen einen Stack direkt in der Hardware.
  - Der Microprozessor hat f�r den Stack einen speziellen Speicher: der Stackpointer. Er zeigt auf den aktuellen Stapeleintrag.
  - Praktisches Beispiel: Passagiere die eine Flugzeug besteigen und es dann in umgekehrter Reihenfolge verlassen.
  - Deklaration eines Stacks: Stack st = new Stack()
  - Hinzuf�gen eines Elements zu dem Stack: Stack.push(element)
  - Element vom Stack herunternehmen: Stack.pop()
  - Anzahl von Elementen auf einem Stack: Stack.Count
  - �berpr�fen ob sich ein Element auf dem Stack befindet: Stack.Contains(element)
  - L�schen eines gesammten Stacks mit Stack.Clear()
 ##### Beispiel:
  ![alt text](Stack.png "Stack") 
    1: Stack wird definiert  
    2: Elemente werden auf Stack zugewiesen     
    3: Ausgabe s�mmtlicher Elemente auf dem Stack   
    4: Anazhl der Elemente auf dem Stack    
    5: Element am Stack enthalten
 ##### Ausgabe:
  ![alt text](OutputStack.png "Stack Output") 

  
#### - Queue:    
  ![alt text](QueueImplement.png "Queue Implement") 

 - Implementiert eine spezielle Collection, welche nach den first in first out Prinzip arbeitet.
 - Praktisches Beispiel hierf�hr ist zb.: die Person die sich zuerst anstellt betritt zuerst den Bus.
 - Deklaration einer Queue: Queue qt = new Queue()
 - Hinzuf�gen eines Elements zu der Queue: Queue.enqueue(element)
 - Element von der Queue herunternehemen: Queue.dequeue()
 - Anazhl von Elementen auf einer Queue: Queue.Count
 - �berpr�fen ob sich ein Element auf der Queue befindet: Queue.Contains(element)
 - L�schen der gesammten Queue: Queue.Clear()
##### Beispiel:
  ![alt text](Queue.png "Queue") 
    1: Queue wird definiert  
    2: Elemente werden auf die Queue zugewiesen     
    3: Ausgabe s�mmtlicher Elemente die sich auf der Queue befinden 
    4: Anazhl der Elemente auf der Queue    
    5: Element auf der Queue enthalten
##### Ausgabe
  ![alt text](QueueOutput.png "Queue Output") 


#### - Liste
  ![alt text](ListImplementation.jpg "List Implement") 
  
 - Die Liste ist ein Objekt welches mehrere Variablen in einer definierten Reihenfolge h�lt.
 - Deklaration einer Liste: List<int> li = new List<int>();
 - Hinzuf�gen eines Elements zu der Liste: List.Add(element)
 - Element von der Liste entfernen: List.Remove(element)
 - Anazhl der Elemente in einer Liste: List.Count
 - �berpr�fen ob sich ein Element in der Liste befindet: List.Contains(element)
 - L�schen der gesammten Liste: List.Clear()
##### Beispiel:
  ![alt text](List.png "List") 
    1: List wird definiert  
    2: Elemente werden in die Liste hinzugef�gt     
    3: Ausgabe s�mmtlicher Elemente die sich in der Liste befinden 
    4: Anazhl der Elemente in der Liste    
    5: Element in der Liste enthalten
##### Ausgabe:
  ![alt text](ListOutput.png "List Output") 

#### - Collection
  ![alt text](CollectionOverview.png "Collection Overview") 
 - Collections sind sehr �hnlich zu Arrays allerdings erm�glichen Collections eine flexiblere Arbeitsweise
 - Bei einem Array muss man die g��e eines Arrays definieren. Bei einer Collection nicht
 - In C# gibt es mehrere Arten von Collections
     - Stack
     - List
     - Queue
 - Deklaration einer Collection: Collection<int> co = new Collection<int>();
 - Hinzuf�gen eines Elements zu einer Collection: Collection.Add(element)
 - Element von einer Collection entfernen: Collection.Remove(element)
 - Anazhl der Elemente in einer Collection: Collection.Count
 - �berpr�fen ob siche ein Element in einer Collection befindet: Collection.Conatins(element)
 - L�schen der gesammten Collection: Collection.Clear()
##### Beispiel:
  ![alt text](Collection.png "Collection") 
    1: Collection wird definiert  
    2: Elemente werden in die Collection hinzugef�gt     
    3: Ausgabe s�mmtlicher Elemente die sich in der Collection befinden 
    4: Anazhl der Elemente in der Collection    
    5: Element in der Collection enthalten
##### Ausgabe:
  ![alt text](CollectionOutput.PNG "Collection Output") 


