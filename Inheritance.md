### Konzept/Vererbung (Hlavacek)
**Datei:** Inheritance.md

- Erkl�ren Sie die Relation der _Vererbung_ und geben Sie Entscheidungshilfen zur Evaluierung von _Vererbungsstrukturen_ an (nennen Sie mindestens ein Beispiel f�r eine g�ltige und eine ung�ltige Vererbung).  

<span style="color:darkblue">Durch Vererbung ist esm�glich Klassen zu erweitern. Die public Member der Oberklasse werden an die erbende Klasse weitervererbt. Dabei spricht man auch von einer is-a (ist ein) beziehung.
</span>

Beispiel:

Animal (Oberklasse)  
Dog (erbende Klasse) Dog **is a** Animal  
Cat (erbende Klasse) Cat **is a** Animal  
Duck (erbende Klasse) Duck **is a** Animal, und hat zus�tzlich 2 Fl�gel

```csharp
public class Animal
{
    public DateTime BirthDate{get; set;}
    public int Legs{get; set;}
}

public class Dog : Animal
{
    public Dog()
    {
        BirthDate = DateTime.Now;
        Legs = 4;
    }
}
public class Cat : Animal
{
    public Cat()
    {
        BirthDate = DateTime.Now;
        Legs = 4;
    }
}

public class Duck : Animal
{
    public int Wings{get; set;} //Erweiterung der Oberklasse
    public Duck()
    {
        BirthDate = DateTime.Now;
        Legs = 2;
        Wings = 2;
    }
}
```

Ung�ltiges Beispiel:

Dog (Oberklasse)  
Cat (erbende Klasse) Cat **is ++not++ a** Dog  
```csharp

public class Dog 
{
    public DateTime BirthDate{get; set;}
    public int Legs{get; set;}
}
public class Cat : Dog
{
    public Cat()
    {
        BirthDate = DateTime.Now;
        Legs = 4;
    }
}
```
Es w�rde zwar funktionieren da die beiden Klassen die gleichen Member beinhalten aber es sorgt f�r verwirrung ung kann zu komplikationen bei �nderungen f�hren.

- Erkl�ren Sie welche Bedeutung die _Konstruktoren_ in der Vererbung haben und geben Sie anhand eines Beispiels an, wie die unterschiedlichen _Konstruktoren_ miteinander verkettet werden k�nnen.  

<span style="color:darkblue">Konstruktor der Oberklasse(ClassA) kann in der  ErbendenKlasse (ClassB) verwendet werden. Daf�r muss das Schl�sselwort :base() an  den Konstruktor der Erbenden Klasse(ClassB) angeh�ngt werden. Parameter k�nnen  mit dem Schl�sselwort :base() an den Konstruktor der Oberklasse weitergegeben werden. Durch das Schl�sselwort :base() wird immer zuerst der Konstruktor der Oberklasse aufgerufen (ClassA) bevor der Block des Konstruktors (ClassB) aufgerufen wird. Dadurch wird Kodeverdoppelung vermieden.
</span>

Beispiel:

```csharp
public ClassA
{
	public double result;
	public ClassA(int x,int y)
	{
		result = x + y;
	}
}

public ClassB : ClassA
{
	public ClassB(int x, int y): base(x,y)
	{
	}
}
```

- Erl�utern Sie das Konzept _Interface_  und geben Sie ein entsprechendes Szenario f�r den Einsatz an.

<span style="color:darkblue">Ein Interface beinhaltet eine Definition von Funktionalit�ten die von einer Klasse erf�llt werden m�ssen. Das hei�t ein Interface gibt eine "Bauform" einer Klasse vor. In einem Interface k�nnen beinhaltet sein:  
Properties  
Methoden  
Events  
Indexer  
Die Members im Interface k�nnen **nicht** Implementiert werden!  
Erst in der Klasse **m�ssen** die Members Implementiert werden!
</span>  

Beispiel:

```csharp
public Interface IIdentifiable
{
	int id { get; }
}

public ClassA : IIdentifiable
{
	public int id { get; set; }
}
```

<span style="color:darkblue">Durch Interfaces ist mehrfache Vererbung m�glich.
</span>  

Beispiel:

```csharp
public Interface IIdentifiable
{
	int id { get; }
}

public Interface ICopyName
{
	void CopyName(string otherName)
}

public ClassA : IIdentifiable, ICopyName
{
	public string name;
	public int id { get; set; }

	void CopyName(string otherName)
	{
		name = otherName;
	}
}
```

<span style="color:darkblue">Interfaces k�nnen Interfaces implementieren
</span>  

Beispiel:

```csharp
public Interface IIdentifiable
{
	int id { get; }
}

public Interface ICopyName
{
	void CopyName(string otherName)
}

public Interface IEntityObject : IIdentifiable, ICopyName
{
	
}
public ClassA : IEntityObject
{
	public string name;
	public int id { get; set; }

	void CopyName(string otherName)
	{
		name = otherName;
	}
}

```

- Erkl�ren Sie das Konzept 'Polymorphie' und geben Sie ein konkretes Beispiel, welches den Einsatz dieses Konzeptes demonstriert, an.

<span style="color:darkblue"> Polymorphie bedeutet Vielgestaltigkeit oder im englischen multiple forms. �berschriebene Methoden (virtual & override) sind dynamisch gebunden, deshalb erf�llen sie das Konzept der Polimorphie da sie in der jeweiligen Klasse eine andere Aufgabe erf�llen (andere Form annehmen) dieses Konzept wird auch Run-Time-Polymorphism gennant.
Compile-Time-Polimorphism kann durch Methoden�berladung geschaffen werden, da die Methode den gleichen Namen hat, jedoch andere Parameter �bernimmt. Durch die �berladung und der Parameter�bergabe wei� der Compiler welche Methode verwendet werden soll.
</span>  

Beispiel:  

Compile-Time-Polimorphism
```csharp

    class Program
    {
        static void Main(string[] args)
        {
            A a = new A();
            a.PrintInfo();          //Output: C#
            a.PrintInfo("is cool!"); //Output: C# is cool!
            Console.ReadKey();
        }
    }

    public class A
    {
        public void PrintInfo()
        {
            Console.WriteLine("C#");
        }

        public void PrintInfo(string message)
        {
            Console.WriteLine($"C# {message}");
        }
    }

    // Output: C#
    //         C# is cool!
```

Run-Time-Polymorphism


```csharp

    class Program
    {
        static void Main(string[] args)
        {
            A a = new A();
            a.PrintInfo(); //Output: C#
            B b = new B();
            b.PrintInfo(); //Output: C# is cool!
            Console.ReadKey();
        }
    }

    public class A
    {
        public virtual void PrintInfo()
        {
            Console.WriteLine("C#");
        }

    }

    public class B : A
    {
        public override void PrintInfo()
        {
            Console.WriteLine("C# is cool!");
        }
    }
```

- Erkl�ren Sie das �_�berschreiben von Instanzmethoden_&quot; und das dynamische Binden von Methoden (verwenden Sie zur Erl�uterung ein konkretes Beispiel).

<span style="color:darkblue">Um eine Methode �berschreiben zu k�nnen muss diese mit **abstract** oder **virtual** gekennzeichnet sein. Methoden die mit **virtual** gekennzeichnet sind, **k�nnen** �berschrieben werden, **abstract** Methoden **m�ssen** �berschrieben werden.  
Mit dem Schl�sselwort ++*override*++ muss die Methode gekennzeichnent werden die die virtual bzw. abstract Methode �berschreibt. Mit dem Schl�sselwort base wird die Methode der Oberklasse aufgerufen und danach erst die Methode der aktuellen Klasse. Dadurch wird **dynamisches Binden** erm�glicht, da die override Methode und die virtual Methode dynamisch miteinander gebunden werden.
</span>  

Beispiel:

```csharp

    class Program
    {
        static void Main(string[] args)
        {
            B b = new B();
            b.PrintInfo();
            Console.ReadKey();
        }
    }

    public class A
    {
        private string name = "Martin";

        public virtual void PrintInfo()
        {
            Console.WriteLine(name);
        }

    }

    public class B : A
    {
        private string job = "programmer";

        public override void PrintInfo()
        {
            base.PrintInfo();
            Console.WriteLine(job);
        }
    }

   	//Output:
        // Martin
        // programmer
	
```

<span style="color:darkblue"> Dadurch ist es m�glich return Parameter aneinander zu reihen und mit Informationen zu erweitern, ohne Code verdoppelung zu verursachen. 
</span>  

Beispiel:

```csharp

    class Program
    {
        static void Main(string[] args)
        {
            B person = new B();
            Console.WriteLine(person.PrintInfo());
            Console.ReadKey();
        }
    }

    public class A
    {
        private string name = "Martin";

        public virtual string PrintInfo()
        {
            return name;
        }

    }

    public class B : A
    {
        private string job = "programmer";

        public override string PrintInfo()
        {
             return base.PrintInfo() + " " + job;
        }
    }

   	//Output:
        // Martin programmer

	
```

<span style="color:darkblue"> Ein klassisches Beispiel ist die ToString() Methode, da man alle Informationen die man Ausgeben will, aneinander reihen kann.
</span>  

Beispiel:

```csharp
    class Program
    {
        static void Main(string[] args)
        {
            B person = new B();
            Console.WriteLine(person.ToString());
            Console.ReadKey();
        }
    }

    public class A
    {
        private string name = "Martin";

        public override string ToString()
        {
            return name;
        }

    }

    public class B : A
    {
        private string job = "programmer";

        public override string ToString()
        {
            return base.ToString() + " arbeitet als " + job;
        }
    }
   	//Output:
        // Martin arbeitet als programmer

	
```

- Erl�utern Sie das Konzept _Abstrakte Klassen_ und geben Sie ein entsprechendes Szenario f�r den Einsatz an.

<span style="color:darkblue"> Abstrakt Klassen m�ssen mit dem Schl�sselwort abstract gekennzeichnent sein. In einer abstrakten Klasse gibt es �hnlich wie beim Interface, **keine** implementierten Methoden. Die Methoden m�ssen ebenso mit abstract gekennzeichnet sein. Eine abstrakte Klasse **kann nicht instanziert werden**. Die Implementation der abstrakten Methoden erfolgen mit dem ++*override*++ Schl�sselwort. Abstrakte Methoden **m�ssen** �berschrieben werden. Abstrakte Klasse beinhalten abstrakte Member, k�nnen aber auch nicht-abstrakte Member beinhalten.
</span>  

Beispiel :

```csharp
        class Program
    {
        static void Main(string[] args)
        {
            B person = new B();
            person.print();
            person.PrintAge();
            Console.ReadKey();
        }
    }

    abstract public class A
    {
        private int age = 27;
        
        //Abstract muss �berschrieben werden
        public abstract void print();

        //wird weitervererbt und kann verwendet werden
        public void PrintAge()
        {
            Console.WriteLine("Alter: " + age);
        }
    }

    public class B : A
    {
        private string job = "programmer";
        
        //�berschrieben Methode
        public override void print()
        {
            Console.WriteLine($"Martin arbeitet als {job}");
        }
    }

    // Output: 
    // Martin arbeitet als programmer
    // Alter: 27
```

- Erl�utern Sie das Konzept _Mehrfachvererbung_ und geben Sie ein entsprechendes Szenario f�r den Einsatz an.

<span style="color:darkblue"> Mehrfachvererbung ist nur mit Interfaces m�glich. Klassen k�nnen in C# nicht von mehreren Klassen erben. 
</span> 

Beispiel:

```csharp
public Interface IIdentifiable
{
	int id { get; }
}

public Interface ICopyName
{
	void CopyName(string otherName)
}

public ClassA : IIdentifiable, ICopyName
{
	public string name;
	public int id { get; set; }

	void CopyName(string otherName)
	{
		name = otherName;
	}
}
```

- Stellen Sie die beiden Konzepte _Vererbung_ und _Komposition_ gegen�ber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.

<span style="color:darkblue">Vererbung (is-a) beziehung, Komposition (has-a) beziehung. Durch Vererbung werden is-a beziehungen gekn�pft. Das heisst die Erbende Klasse ist eine erweiterung der Oberklasse. Deshalb kann die Oberklasse ohne die erbende Klasse existieren. Bei einer Komposition ist eine has-a Beziehung vorhanden, das heisst, dass die zwei Klassen voneinander enkoppelt sind, und somit unabh�ngig agieren k�nnen.
</span>  

- Stellen Sie die beiden Konzepte _Abstrakte Klassen_  und _Interfaces_  gegen�ber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.

<span style="color:darkblue"> Interfaces m�ssen von der Erbenden Klasse zur g�nze erf�llt werden, alle Member m�ssen in der Klasse implementiert werden. Bei Abstrakten Klassen hingegen m�ssen nur die Member die mit dem Schl�sselwort abstract gekennzeichnet sind �berschrieben werden. In Abstrakten Klassen k�nnen auch implementierte Member vorkommen (nicht mit abstract gekennzeichnet) und k�nnen direkt in der erbenden Klasse verwendet werden.
</span>  

<span style="color:darkblue">Interfaces geben eine klare Struktur (Bauform) vor die erf�llt werden muss. Wenn in einer Klasse ein Member hinzugef�gt wird muss dieser auch im Interface hinzugef�gt werden und umgekehrt. Abstrakte Klassen k�nnen Member beinhalten die nicht �berschrieben werden m�ssen und direkt verwendet werden k�nnen.  
</span>  

<span style="color:darkblue">
</span>

Beispiel:

```csharp
        class Program
    {
        static void Main(string[] args)
        {
            B person = new B();
            person.print();

            // Implementierte Methode in der abstracten Klasse
            person.PrintAge();
            Console.ReadKey();
        }
    }

    abstract public class A
    {
        private int age = 27;
        
        //Abstract muss �berschrieben werden
        public abstract void print();

        //wird weitervererbt und kann verwendet werden
        public void PrintAge()
        {
            Console.WriteLine("Alter: " + age);
        }
    }

    public class B : A
    {
        private string job = "programmer";
        
        //�berschrieben Methode
        public override void print()
        {
            Console.WriteLine($"Martin arbeitet als {job}");
        }
    }

    // Output: 
    // Martin arbeitet als programmer
    // Alter: 27
```


### Observer Pattern (Hlavacek)
**Datei** Observer.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck
- Entwurfsproblem und wie das Muster das Problem l�st
- Anwendbarkeit
- Struktur des Musters