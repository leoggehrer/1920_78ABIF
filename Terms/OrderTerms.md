## Terms
### Ordnen Sie die nachfolgenden Begriffe nach ihrer Entstehung und erl�utern Sie die Bedeutung:
**Verantwortlicher:** Engleder Michael

- Bibliothek
- Unterprogramm
- Prozedur
- Klasse
- Funktion
- Package
- Modul

-------------------------------------
#### Anf�nge der Programmierung
Am Anfang wurde s�mtlicher **Code in einem File** (Anmerkung: "Spaghetti-Code") geschrieben.  
In Skript-Sprachen wie CMD, PowerShell findet man oft heute noch diesen Ansatz vor!   

#### Unterprogramme
Unterprogramme oder in C# Methoden sind **Codebl�cke mit Anweisungen**.  
Ein Programm ruft ein Unterprogramme auf und alle Anweisungen innerhalb dieses Codeblocks werden ausgef�hrt!   
Diesen Ansatz nennt man **prozedurale Programmierung** und ebnete den Weg weg von Assemblersprachen hin zu h�heren Sprachen.
Dabei k�nnen Unterprogramme sowohl Werte zur�ckgeben, oder Werte als Parameter vom Aufrufer erhalten.
Weiter k�nnen Methoden mit unterschiedlichen Zugriffsmodifikatoren (**private/public**) versehen werden.  
Siehe **Prozedur / Funktion**

#### Prozedur
Prozeduren sind Unterprogramme und werden von einem Programm aufgerufen, geben aber **keinen Wert (void)** zur�ck  
````
    class Program
    {
        static void Main(string[] args)
        {
            WriteHelloWorld
        }
        public static void WriteHelloWorld()
        {
            Console.WriteLine("Hello World!");
        }
    }
````

#### Funktion
Funktionen sind Unterprogramme, werden von einem Programm aufgerufen und geben **einen Wert** zur�ck.  
````
    class Program
    {
        static void Main(string[] args)
        {
            int sum = Sum(1, 2);
        }

        private static int Sum(int num1, int num2)
        {
            return num1 + num2;
        }
    }
````
#### Modul
Unterprogramme werden in **einer logischen Einheiten** (z.B in einer Datei) zusammengefasst!  
Die Unterprogramme eines Moduls k�nnen dann von einem Program aufgerufen werden.  
Module k�nnen einzeln geplant, programmiert und getestet werden.  
Hier verfolgt man die **modulare Programmierweise** mit **austauschbaren Komponenten** und **Datenkapselung**.
Zus�tzlich wird durch die Aufteilung auch die Lesbarkeit des Codes verbessert.  

#### Klassen
Klassen beschreiben **Eigenschaften und F�higkeiten** von Objekten. (= objektorientierte Programmierung)   
Klassen werden in C# mit **class** deklariert und k�nnen mit unterschiedlichen Zugriffsmodifikatoren (**private/public**) versehen werden.   
Diese k�nnen Fields, Properties und Methoden als sogenannte **Members** beinhalten.  
Klassen k�nnen von anderen Klassen oder Interfaces deren Members erben. (**Vererbung**)  
Instanziert werden Klassen in C# mit dem Schl�sselwort new(). Dabei wird der Konstruktor aufgerufen, welchen auch Parameter zur Instanzierung �bergeben werden k�nnen.  

````
    public class Car: ICar
    {
        private int fuelTank;
        public string Brand { get; set; }
        public Car(int maxFuelLevel)
        {
            this.fuelTank = maxFuelLevel;
        }
        public void StartEngine()
        {
            // do someting
        }
    }
````
Abbildung Klassendiagramm  
![alt text](CarClassDiagram.png "Klassendiagramm Car")

#### Bibliothek
Bibliotheken sind **Sammlungen von Modulen und Klassen** und deren Unterprogramme.  
Diese k�nnen von einem Programmen angefordert werden.  
Im Unterschied zu Programmen stellen Bibliotheken **keine eigenen lauff�higen Einheiten** dar!  
**Datenkapselung** und Zugriffsmodifikatoren f�r den Aufruf spielen hier eine gro�e Rolle.  
Nach der Kompilierung werden Bibliotheken unter .net in DLL-Dateien (Assembly) �bersetzt!  
Bibliotheken k�nnen typischerweise in mehreren Software-Projekten eingesetzt werden...  
Abbildung Klassendiagramm  
![alt text](Bibliothek.png "Bibliothek C#")  

#### Package
Ein Package kann neben dem eigentlichen ausf�hrbaren Programm auch andere Programme und Dateien enthalten.  
Packages k�nnen z.B. einfache **Archive** (z.B. TAR-Packages unter Linux) darstellen und diese werden dann von einem Package-Manager angefordert. 

````
sudo apt-get update
# Aktualisiert die Package Datenbank unter der jeweiligen Linux Distribution
```` 
Abbildung PackageManager Linux  
![alt text](sudoUpdatePackage.png "Package Manager in Shell")
