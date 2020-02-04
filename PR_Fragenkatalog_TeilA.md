# Fragenkatalog Teil I

Dieser Fragenkatalog ist der erste Teil eines mehrteiligen Fragenkataloges zur Abschlussprüfung: Reife- und Diplomprüfung. Fragen die in diesem Teil enthalten sind müssen von jedem/er Schüler/in, unabhängig vom Ausbildungsschwerpunkt, beantwortet werden können.

## Begriffe
**Ordner:** Terms

### Erklären Sie die folgenden Begriffe im Zusammenhang (Gegenüberstellung):  
**Datei:** Comparison.md (Bozbey)

- Spezifikation \<-\> Verifikation
- Algorithmus \<-\> Programm
- Prozess \<-\> Multithraeding \<-\> Interprozesskommunikation
- Value Type \<-\> Reference Type
- Stack-Speicher \<-\> Heap-Speicher
- Call by value \<-\> Call by reference

### Erklären Sie die folgenden abstrakten Datenstrukturen:
**Datei:** DataStructures.md (Freudenthaler)

- Stack
- Queue
- Liste
- Collection

### Ordnen Sie die nachfolgenden Begriffe nach ihrer Entstehung und erläutern Sie die Bedeutung:
**Datei:** OrderTerms.md (Engleder)

- Bibliothek
- Unterprogramm
- Prozedur
- Klasse
- Funktion
- Package
- Modul

### Allgemein (Haller)
**Ordner:** Generally

- Beschreiben Sie die einzelnen Schritte beim Erstellungsprozess eines Programms (Compiler, Interpreter, Linker, Make)  
**Datei:** CreationProcess.md
- Was erreicht man mit dem Einsatz von Exceptions (Ausnahmen)?  
(Unterschied gegenüber der Fehlerbehandlung mit Rückgabewert)  
**Datei:** ExceptionHandling.md

### Ablaufsteuerung  (Trnka)
**Ordner:** FlowControl

- Beschreiben Sie ausführlich die Grundelemente zur Steuerung des Programmablaufes.  
**Datei:** BaseElements.md
- Beschreiben Sie die unterschiedlichen Schleifentypen und deren Einsatzzweck.  
**Datei:** Loops.md
- Skizzieren Sie anhand eines Beispiels die möglichen Ausführungspfade bei der Anwendung von _try_, _catch_ und _finally_ Blöcken. Zur Erläuterung der möglichen Ausführungspfade geben Sie Beispiel an.  
**Datei:** TryCatch.md

## Objektorientierung
**Ordner:** OOP

Alle Fragen in diesem Abschnitt betreffen objektorientierte Programmier-Aspekte und sind in der CSharp – Terminologie zu beantworten. Auch Beispiele, welche mit den Fragen angegeben, sind in der CSharp-Syntax anzugeben.

### Allgemein
**Ordner:** Generally

- Erklären Sie die Konzepte der Unified Modeling Language – UML in Bezug auf die objektorientierten Programmierung (Diagrammtypen mit Erläuterung über die Syntax).  
**Datei:** UmlDiagrams.md Deixler  
- Erstellen Sie ein UML/CLD für ein Beispiel Ihrer Wahl und erläutern Sie alle Möglichkeiten dieses Diagrammtyps (falls notwendig, können auch mehrere Beispiele angegeben werden).  
**Datei:** UmlClassDiagrams.md  Deixler  
- Erläutern Sie wie die Relationen zwischen Klassen aus dem UML/CLD in der OOP implementiert werden (verwenden Sie zur Erläuterung ein Beispiel).
- Erläutern Sie oberflächliches und tiefes Klonen von Objekten (auf welche Arten können Objekte geklont werden)  
**Datei:** CloneCopy.md
- Erklären Sie die Gleichheit von Objekten (erklären Sie wann 2 Objekte gleich sind und erläutern Sie den Equals/HashCode Vertrag).  
**Datei:** EqualsHashCode.md
- Erläutern Sie die Arbeits- und Funktionsweise des Garbage-Collectors  (Engleder)  
**Datei:** Garbage.md
- Erklären Sie die Bedeutung und den Vorteil eines  'Einheitliches Typsystem'  
**Datei:** TypeSystem.md
- Erläutern Sie das 'Boxing und Unboxing' (geben Sie dazu ein Beispiel an)  
**Datei:** BoxingAndUnboxing.md

### Prinzipien  (Pechak)
**Ordner:** Principle

Erklären Sie die folgenden Prinzipien, die in der OOP angewendet werden
(gegebenenfalls können Sie auf die Prozedurale Programmierung verweisen):
**Datei:** OopPrinciple.md

- Abstraktion,
- Datenkapselung (information hiding),
- Vererbung,
- Polymorphismus

### Konzepte (Pechak)
**Ordner:** Concepts

Erklären Sie die folgenden Begriffe im Zusammenhang (Gegenüberstellung):
**Datei:** OopConcepts.md

- Klasse \<-\> Objekt
- Basisreferenz \<-\> Selbstreferenz
- Konstruktors \<-\> Destruktors
- Defaultkonstruktor \<-\> Standardkonstruktor
- Überladen von Methoden \<-\> Überladen von Operatoren

Erläutern Sie die Standard-Methoden

- Welche kennen Sie (nennen Sie mind. 3)?
- Geben Sie deren Zweck an

Erläutern Sie das Überladen von Methoden

- Geben Sie den Zweck an (geben Sie ein Beispiel an)

Erklären und erläutern Sie die Arten von

- Klassenmembers und Objektmembers.

Welche Entscheidungshilfen wenden Sie zur Identifizierung von

- Klassenmethoden und
- Exemplarmethoden (Objektmembers) an?

Erklären Sie den Unterschied zwischen einer

- 'Rein virtuelle Methoden' und einer
- 'virtuelle Methoden'

### Konzept/Vererbung (Hlavacek)
**Datei:** Inheritance.md

- Erklären Sie die Relation der _Vererbung_ und geben Sie Entscheidungshilfen zur Evaluierung von _Vererbungsstrukturen_ an (nennen Sie mindestens ein Beispiel für eine gültige und eine ungültige Vererbung).

- Erklären Sie welche Bedeutung die _Konstruktoren_ in der Vererbung haben und geben Sie anhand eines Beispiels an, wie die unterschiedlichen _Konstruktoren_ miteinander verkettet werden können.

- Erläutern Sie das Konzept _Interface_  und geben Sie ein entsprechendes Szenario für den Einsatz an.

- Erklären Sie das Konzept 'Polymorphie' und geben Sie ein konkretes Beispiel, welches den Einsatz dieses Konzeptes demonstriert, an.

- Erklären Sie das „_Überschreiben von Instanzmethoden_&quot; und das dynamische Binden von Methoden (verwenden Sie zur Erläuterung ein konkretes Beispiel).

- Erläutern Sie das Konzept _Abstrakte Klassen_ und geben Sie ein entsprechendes Szenario für den Einsatz an.

- Erläutern Sie das Konzept _Mehrfachvererbung_ und geben Sie ein entsprechendes Szenario für den Einsatz an.

- Stellen Sie die beiden Konzepte _Vererbung_ und _Komposition_ gegenüber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.

- Stellen Sie die beiden Konzepte _Abstrakte Klassen_  und _Interfaces_  gegenüber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.

### Technik/Serialisierung (Peterseil)
**Datei:** Serializable.md

- Erklären Sie die Technik 'Serialisierung von Objekten' und 'Deserialisierung von Objekten'.

- Serialisierung und Deserialisierung ist eine wichtige Basistechnik für weitere höhere (Architektur-)Konzepte. Nennen Sie eine weitere Technik, welche Serialisierung und Deserialisierung als Basis verwendet.

### Technik/Generische Typen (Seidl)
**Datei:** Generics.md

- Erklären Sie die Technik 'Generizität' und erläutern Sie die Verwendung dieser Technik (konstruieren Sie ein einfaches Beispiel).

- Generizität ist eine sehr junge Programmiertechnik. Wie konnte man vor Einführung dieser Technik bestimmte Merkmale dieser Technik dennoch nachbilden (erläutern Sie dies anhand der abstrakten Datenstruktur 'Stack').

- Was sind Einschränkungen und welche Bedeutung haben diese im Bezug auf Generische Typen (skizzieren Sie ein Beispiel)?

### Technik/Reflection (Eichinger)
**Datei:** Reflection.md

Erläutern Sie die Möglichkeiten Klassen und Objekte zur Laufzeit zu analysieren. Skizzieren Sie einen Anwendungsfall aus der Praxis.

### Technik/Eventhandling (Eichinger)
**Datei:** Events.md

Erläutern Sie das Prinzip und die Idee vom Eventhandling. Geben Sie dazu ein konkretes Beispiel an. Vergleichen Sie diese Technik mit früheren Prinzipien (Polling, Interrupt).

## Design Pattern
**Ordner** Patterns

### Singleton (Seidl)
**Datei** Singleton.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck
- Entwurfsproblem und wie das Muster das Problem löst
- Anwendbarkeit
- Struktur des Musters

### Iterator (Haller)
**Datei** Iterator.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck
- Entwurfsproblem und wie das Muster das Problem löst
- Anwendbarkeit
- Struktur des Musters

### Observer Pattern (Hlavacek)
**Datei** Observer.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck
- Entwurfsproblem und wie das Muster das Problem löst
- Anwendbarkeit
- Struktur des Musters

### Model View Control (MVC) Pattern (Walchetseder)
**Datei** Mvc.md  

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck
- Entwurfsproblem und wie das Muster das Problem löst
- Anwendbarkeit
- Struktur des Musters

### Model View View-Model (MVVM) Pattern (Freudenthaler)
**Datei** MvvM.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck
- Entwurfsproblem und wie das Muster das Problem löst
- Anwendbarkeit
- Struktur des Musters
