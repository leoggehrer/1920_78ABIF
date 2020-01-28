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
Am Anfang wurde s�mtlicher Code in einem File "Spaghetti-Code" geschrieben.  In Skript-Sprachen wie CMD, PowerShell findet man oft heute noch diesen Ansatz vor!  

#### Unterprogramme
Unterprogramme oder Methoden sind Codebl�cke mit Anweisungen. 
Ein Programm ruft ein Unterprogramme auf und alle Anweisungen innerhalb dieser Metoden werden ausgef�hrt!   Diesen Ansatz nennt man prozedurale Programmierung und ebnete den Weg weg von Assemblersprachen hin zu h�heren Sprachen.
Dabei k�nnen Unterprogramme sowohl Werte zur�ckgeben, oder Werte als Parameter vom Aufrufer erhalten.
Weiter k�nnen Methoden mit unterschiedlichen Zugriffsmodifikatoren (**private/public**) versehen werden. 
Siehe Prozedur / Funktion

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
Unterprogramme zusammen mit den Daten werden in logischen Einheiten zusammengefasst!  Diese Teilbl�cke k�nnen einzeln geplant, programmiert und getestet werden.

#### Klassen
Klassen beschreiben **Eigenschaften und F�higkeiten** von Objekten.
Klassen werden in C# mit **class** deklariert und k�nnen mit unterschiedlichen Zugriffsmodifikatoren (**private/public**) versehen werden. 
Diese k�nnen Fields, Properties und Methoden als sogenannte Members beinhalten.
Klassen k�nnen von anderen Klassen oder Interfaces deren Members erben.
Instanziert werden Klassen mit dem Schl�sselwort new(). Dabei wird der Konstruktor aufgerufen, welchen auch Parameter zur Instanzierung �bergeben werden k�nnen.  

````
    public class Car
    {
        private int fuelTank;
        public string Brand { get; set; }
        public Car(int maxFuelLevel)
        {
            this.fuelTank = maxFuelLevel;
        }
        public void StartEngine()
        {

        }
    }
````
Abbildung Klassendiagramm  
![alt text](CarClassDiagram.png "Klassendiagramm Car")

#### Bibliothek
Bibliotheken sind Sammlungen von Klassen und Unterprogrammen, die von Programmen angefordert werden k�nnen.
Im Unterschied zu Programmen stellen Bibliotheken keine eigenen lauff�higen Einheiten dar!
Nach der Kompilierung werden Bibliotheken in DLL-Dateien (Assembly) �bersetzt!

#### Package
Ein Package kann neben dem eigentlichen ausf�hrbaren Programm auch andere Programme und Dateien enthalten. Vergleichbar mit Namespace   
