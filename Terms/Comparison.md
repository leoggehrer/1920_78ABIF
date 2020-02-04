# Gegen�berstellung
## Tolga Bozbey
## Erkl�ren Sie die folgenden Begriffe im Zusammenhang (Gegen�berstellung):
---
- Spezifikation \<-\> Verifikation
- Algorithmus \<-\> Programm
- Prozess \<-\> Multithraeding \<-\> Interprozesskommunikation
- Value Type \<-\> Reference Type
- Stack-Speicher \<-\> Heap-Speicher
- Call by value \<-\> Call by reference
#### 1. Spezifikation \<-\> Verifikation
---
Das Ziel der Speizifikation ist es, das Problem der Software zu erfassen und zu beschreiben, 
wogegen das Ziel der Verfikation es ist, klarzustellen ob alle Anforderungen jeder seiner Phase vollst�ndig erf�llt wurde und 
falls die Phase nicht abgeschlossen wurde, muss es in der n�chsten Phase abgeschlossen werden.

#### 2. Algorithmus \<-\> Programm
---
Ein Algorithmus ist ein systematischer logischer Ansatz zum L�sen eines spezifischen Problems.<br><br>

*Typische Schritte bei der Entwicklung von Algorithmen*

    Problem Definition
    Entwicklung eines Modells
    Spezifikation des Algorithmus
    Einen Algorithmus entwerfen
    �berpr�fung der Richtigkeit des Algorithmus
    Analyse des Algorithmus
    Implementierung des Algorithmus
    Programm testen
    Vorbereitung der Dokumentation

*Algorithums einer linearen Suche* 

    1. Beginne die Suche beim ersten Element des Arrays und vergleiche jedes Element des Arrays mit x.
    2. Falls ein Element des Arrays mit x gleich ist, gebe dessen Indexwert zur�ck.
    3. Falls keines der Elemente des Arrays mit x gleich ist, gebe -1 zur�ck.

<br>Ein Program ist der genaue Code, der f�r das Problem geschrieben wurde und alle Regeln der Programmiersprache befolgt.
Also eine Anleitung von einer Reihe an Anweisungen, welches der Computer Schritt-f�r-Schritt abarbeitet.<br><br>
*Program einer lineraren Suche*
``` c#
int search(int arr[], int n, int x)
{   
	for (int i = 0; i < length; i++)
	{
		if(arr[i] == x)
		{
			return i;
		}
		else
		{
			return -1;
		}
	}
}
```
#### 3. Prozess \<-\> Multithreading \<-\> Interprozesskommunikation
---
*Prozess*<br>
Ein Prozess kann aus mehreren Threads bestehen, welche dann einzeln oder parallel erledigt werden k�nnen. 
Ein Prozessorkern kann nur ein Thread zur einer Zeit behandeln. 
Aber durch die Einf�hrung von Multitasking, kann der Kern die mehrere Threads parallel abarbeiten.


*Multithreading*<br>
Multithreading ist das Gegenteil von Single-Threading. Sowohl Multithreading, also auch Multitasking k�nnen von nur einem Prozessorkern ausgef�hrt werden.
Eine echt-parallele Ausf�hrung l�sst sich durch ein Prozessor mit mehreren Prozessorkernen l�sen.
<br><br>Vorteile vom Multithreading gegen�ber Single-Threading
- Reaktionsf�higkeit
- Schnellere Ausf�hrung
- Geringerer Ressourcenverbrauch
- Bessere Systemauslastung
- Parallelisierung


<br>Nachteile vom Multithreading gegen�ber Single-Threading
- Synchronization
- Thread crahses a process


*Interprozesskommunikation*<br>
Interprozesskommunikation benzutzt folgende Arten der Kommunikationen:
- Speicherbasierte Kommunikation (Shared Memory)
- Kommunikation �ber Dateien (Austausch von Dateien)
- Nachrichtenbasierte Kommunikation (Message Quueue, namenlose Pipes, bekannte Pipes, Sockets)
- Race Conditions

#### 4. Value Type \<-\> Reference Type
---

Ein Datentyp ist ein Werttyp, wenn er einen Datenwert in seinem eigenen Speicherbereich enth�lt. Das bedeutet, dass Variablen dieser Datentypen ihre Werte direkt enthalten,
w�hrendessen Ein Referenztyp speichert seinen Wert nicht direkt. 
Stattdessen speichert er die Adresse, welches einen Zeiger auf eine andere Speicherstelle, die die Daten enth�lt. 

*Value Type*<br>
Eine Liste der Value Types<br>
- bool
- byte
- char
- decimal
- double
- enum
- float
- int
- long
- sbyte
- short
- struct
- uint
- ulong
- ushort

*Reference Type*<br>
Eine Liste der Value Types<br>
- string
- arrys
- classes
- delegates

#### 5. Stack-Speicher \<-\> Heap-Speicher
---
*Stack-Speicher*<br>
```c#
p1 (0x123456)
p2 ...
```
*Heap-Speicher*<br>

```c#
class Person
{
    public string Name;
    public string Age;

    public Person Person;
}
```

Locale Variablen kommen auf den Stack, 
w�hrend Instanzen von Klassen auf den Heap kommen in .Net.
Und wenn keine Referenzen mehr auf den Heap-Speicher zeigen,
r�umt hier der Garbage-Collector auf. 


#### 6. Call by value \<-\> Call by reference
---
*Call by value -> Wert*<br>

```c#
"Call by value" kopiert den Wert und es wird nur die Kopie ge�ndert - Folge mehr Speicherplatz notwendig wird, 
aber der Vorteil dabei ist, dass Variablen au�erhalb einer Methode nicht ge�ndert werden kann.  
```

*Call by reference -> Verweis*<br>

```c#
"Call by reference" es auf den Orginalwert referenziert wird und dieser ver�ndert wird - Folge es wird Fehelr anf�lliger, 
aber der Vorteil ist, dass die Variablen auch au�erhalb einer Mehthode ge�ndert werden k�nnen.
```


### Quellen:
| Thema | Quelle|
| --- | --- |
| 1 | https://de.wikipedia.org/wiki/Software_Requirements_Specification |
| 1 | https://en.wikipedia.org/wiki/Software_verification |
| 1 | https://en.wikipedia.org/wiki/Software_verification_and_validation |
| 1 | https://www.easterbrook.ca/steve/2010/11/the-difference-between-verification-and-validation/ |
| 2 | https://www.geeksforgeeks.org/difference-between-algorithm-pseudocode-and-program/ |
| 2 | https://en.wikipedia.org/wiki/Algorithm |
| 2 | https://michaelkipp.de/processing/10%20algorithmen.html |
| 2 | https://www.alexanderthamm.com/de/artikel/erklaert-was-genau-sind-eigentlich-algorithmen/ |
| 3 | https://en.wikipedia.org/wiki/Process_(computing) |
| 3 | https://de.wikipedia.org/wiki/Multithreading |
| 3 | https://en.wikipedia.org/wiki/Thread_(computing)#Multithreading |
| 3 | https://de.wikipedia.org/wiki/Interprozesskommunikation |
| 4 | https://en.wikipedia.org/wiki/Value_type_and_reference_type |
| 4 | https://en.wikipedia.org/wiki/Primitive_data_type |
| 4 | https://en.wikipedia.org/wiki/Composite_data_type |
| 4 | https://www.tutorialsteacher.com/csharp/csharp-value-type-and-reference-type |
| 4 | https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/reference-types |
| 5 | https://en.wikipedia.org/wiki/Stack_(abstract_data_type) |
| 5 | https://en.wikipedia.org/wiki/Heap_(data_structure) |
| 6 | https://en.wikipedia.org/wiki/Evaluation_strategy#Call_by_value |
| 6 | https://en.wikipedia.org/wiki/Evaluation_strategy#Call_by_reference |
| 6 | https://www.guru99.com/call-by-value-vs-call-by-reference.html |
| | https://www.youtube.com |