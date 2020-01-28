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
#### Unterprogramme
Unterprogramme oder Methoden sind Codebl�cke mit Anweisungen. 
Ein Programm ruft eine Methode auf und alle Anweisungen innerhalb dieser Metoden werden ausgef�hrt!   
Dabei k�nnen Unterprogramme sowohl Werte zur�ckgeben, oder Werte als Parameter vom Aufrufer erhalten.
Weiter k�nnen Methoden mit unterschiedlichen Zugriffsmodifikatoren (**private/public**) versehen werden. 
Siehe Prozedur / Funktion

#### Prozedur
Prozeduren werden von einem Programm aufgerufen, geben aber **keinen Wert (void)** zur�ck  
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
Funktionen werden von einem Programm aufgerufen und geben **einen Wert** zur�ck 
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
Bibliotheken sind Sammlungen von Unterprogrammen, die von Programmen angefordert werden k�nnen.
Im Unterschied zu Programmen stellen Bibliotheken keine eigenen lauff�higen Einheiten dar!
Nach der Kompilierung werden Bibliotheken in DLL-Dateien �bersetzt!

#### Package
Bibliotheken sind Sammlungen von Unterprogrammen, die von Programmen angefordert werden k�nnen.
Im Unterschied zu Programmen stellen Bibliotheken keine eigenen lauff�higen Einheiten dar!
Nach der Kompilierung werden Bibliotheken in DLL-Dateien �bersetzt!
