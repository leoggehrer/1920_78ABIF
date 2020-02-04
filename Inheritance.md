### Konzept/Vererbung (Hlavacek)
**Datei:** Inheritance.md

- Erklären Sie die Relation der _Vererbung_ und geben Sie Entscheidungshilfen zur Evaluierung von _Vererbungsstrukturen_ an (nennen Sie mindestens ein Beispiel für eine gültige und eine ungültige Vererbung).  

<span style="color:darkblue">Durch Vererbung ist es möglich Klassen zu erweitern. Die public Member der Oberklasse werden an die erbende Klasse weitervererbt. Dabei spricht man auch von einer is-a (ist ein) beziehung.
</span>

Beispiel:

Animal (Oberklasse)  
Dog (erbende Klasse) Dog **is a** Animal  
Cat (erbende Klasse) Cat **is a** Animal  
Duck (erbende Klasse) Duck **is a** Animal, und hat zusätzlich 2 Flügel

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

Ungültiges Beispiel:

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
Es würde zwar funktionieren da die beiden Klassen die gleichen Member beinhalten aber es sorgt für verwirrung ung kann zu komplikationen bei Änderungen führen.

- Erklären Sie welche Bedeutung die _Konstruktoren_ in der Vererbung haben und geben Sie anhand eines Beispiels an, wie die unterschiedlichen _Konstruktoren_ miteinander verkettet werden können.  

<span style="color:darkblue">Konstruktor der Oberklasse(ClassA) kann in der  ErbendenKlasse (ClassB) verwendet werden. Dafür muss das Schlüsselwort :base() an  den Konstruktor der Erbenden Klasse(ClassB) angehängt werden. Parameter können  mit dem Schlüsselwort :base() an den Konstruktor der Oberklasse weitergegeben werden. Durch das Schlüsselwort :base() wird immer zuerst der Konstruktor der Oberklasse aufgerufen (ClassA) bevor der Block des Konstruktors (ClassB) aufgerufen wird. Dadurch wird Kodeverdoppelung vermieden.
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

- Erläutern Sie das Konzept _Interface_  und geben Sie ein entsprechendes Szenario für den Einsatz an.

<span style="color:darkblue">Ein Interface beinhaltet eine Definition von Funktionalitäten die von einer Klasse erfüllt werden müssen. Das heißt ein Interface gibt eine "Bauform" einer Klasse vor. In einem Interface können beinhaltet sein:  
Properties  
Methoden  
Events  
Indexer  
Die Members im Interface können **nicht** Implementiert werden!  
Erst in der Klasse **müssen** die Members Implementiert werden!
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

<span style="color:darkblue">Durch Interfaces ist mehrfache Vererbung möglich.
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

<span style="color:darkblue">Interfaces können Interfaces implementieren
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

- Erklären Sie das Konzept 'Polymorphie' und geben Sie ein konkretes Beispiel, welches den Einsatz dieses Konzeptes demonstriert, an.

<span style="color:darkblue"> Polymorphie bedeutet Vielgestaltigkeit oder im englischen multiple forms. Überschriebene Methoden (virtual & override) sind dynamisch gebunden, deshalb erfüllen sie das Konzept der Polimorphie da sie in der jeweiligen Klasse eine andere Aufgabe erfüllen (andere Form annehmen) dieses Konzept wird auch Run-Time-Polymorphism gennant.
Compile-Time-Polimorphism kann durch Methodenüberladung geschaffen werden, da die Methode den gleichen Namen hat, jedoch andere Parameter übernimmt. Durch die Überladung und der Parameterübergabe weiß der Compiler welche Methode verwendet werden soll.
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

- Erklären Sie das „_Überschreiben von Instanzmethoden_&quot; und das dynamische Binden von Methoden (verwenden Sie zur Erläuterung ein konkretes Beispiel).

<span style="color:darkblue">Um eine Methode überschreiben zu können muss diese mit **abstract** oder **virtual** gekennzeichnet sein. Methoden die mit **virtual** gekennzeichnet sind, **können** überschrieben werden, **abstract** Methoden **müssen** überschrieben werden.  
Mit dem Schlüsselwort ++*override*++ muss die Methode gekennzeichnent werden die die virtual bzw. abstract Methode überschreibt. Mit dem Schlüsselwort base wird die Methode der Oberklasse aufgerufen und danach erst die Methode der aktuellen Klasse. Dadurch wird **dynamisches Binden** ermöglicht, da die override Methode und die virtual Methode dynamisch miteinander gebunden werden.
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

<span style="color:darkblue"> Dadurch ist es möglich return Parameter aneinander zu reihen und mit Informationen zu erweitern, ohne Code verdoppelung zu verursachen. 
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

- Erläutern Sie das Konzept _Abstrakte Klassen_ und geben Sie ein entsprechendes Szenario für den Einsatz an.

<span style="color:darkblue"> Abstrakt Klassen müssen mit dem Schlüsselwort abstract gekennzeichnent sein. In einer abstrakten Klasse gibt es ähnlich wie beim Interface, **keine** implementierten Methoden. Die Methoden müssen ebenso mit abstract gekennzeichnet sein. Eine abstrakte Klasse **kann nicht instanziert werden**. Die Implementation der abstrakten Methoden erfolgen mit dem ++*override*++ Schlüsselwort. Abstrakte Methoden **müssen** überschrieben werden. Abstrakte Klasse beinhalten abstrakte Member, können aber auch nicht-abstrakte Member beinhalten.
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
        
        //Abstract muss überschrieben werden
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
        
        //Überschrieben Methode
        public override void print()
        {
            Console.WriteLine($"Martin arbeitet als {job}");
        }
    }

    // Output: 
    // Martin arbeitet als programmer
    // Alter: 27
```

- Erläutern Sie das Konzept _Mehrfachvererbung_ und geben Sie ein entsprechendes Szenario für den Einsatz an.

<span style="color:darkblue"> Mehrfachvererbung ist nur mit Interfaces möglich. Klassen können in C# nicht von mehreren Klassen erben. 
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

- Stellen Sie die beiden Konzepte _Vererbung_ und _Komposition_ gegenüber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.

<span style="color:darkblue">Vererbung (is-a) beziehung, Komposition (has-a) beziehung. Durch Vererbung werden is-a beziehungen geknöpft. Das heisst die Erbende Klasse ist eine erweiterung der Oberklasse. Deshalb kann die Oberklasse ohne die erbende Klasse existieren. Bei einer Komposition ist eine has-a Beziehung vorhanden, das heisst, dass die zwei Klassen voneinander enkoppelt sind, und somit unabhängig agieren können.
</span>  

- Stellen Sie die beiden Konzepte _Abstrakte Klassen_  und _Interfaces_  gegenüber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.

<span style="color:darkblue"> Interfaces müssen von der Erbenden Klasse zur gänze erfüllt werden, alle Member müssen in der Klasse implementiert werden. Bei Abstrakten Klassen hingegen müssen nur die Member die mit dem Schlüsselwort abstract gekennzeichnet sind überschrieben werden. In Abstrakten Klassen können auch implementierte Member vorkommen (nicht mit abstract gekennzeichnet) und können direkt in der erbenden Klasse verwendet werden.
</span>  

<span style="color:darkblue">Interfaces geben eine klare Struktur (Bauform) vor die erfüllt werden muss. Wenn in einer Klasse ein Member hinzugefügt wird muss dieser auch im Interface hinzugefügt werden und umgekehrt. Abstrakte Klassen können Member beinhalten die nicht überschrieben werden müssen und direkt verwendet werden können.  
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
        
        //Abstract muss überschrieben werden
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
        
        //Überschrieben Methode
        public override void print()
        {
            Console.WriteLine($"Martin arbeitet als {job}");
        }
    }

    // Output: 
    // Martin arbeitet als programmer
    // Alter: 27
```