### Konzept/Vererbung (Hlavacek)
**Datei:** Inheritance.md

- Erkl�ren Sie die Relation der _Vererbung_ und geben Sie Entscheidungshilfen zur Evaluierung von _Vererbungsstrukturen_ an (nennen Sie mindestens ein Beispiel f�r eine g�ltige und eine ung�ltige Vererbung).  

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

<span style="color:darkblue">Durch Interfaces ist mehrfachvererbung m�glich.
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

- Erkl�ren Sie das �_�berschreiben von Instanzmethoden_&quot; und das dynamische Binden von Methoden (verwenden Sie zur Erl�uterung ein konkretes Beispiel).

- Erl�utern Sie das Konzept _Abstrakte Klassen_ und geben Sie ein entsprechendes Szenario f�r den Einsatz an.

- Erl�utern Sie das Konzept _Mehrfachvererbung_ und geben Sie ein entsprechendes Szenario f�r den Einsatz an.

- Stellen Sie die beiden Konzepte _Vererbung_ und _Komposition_ gegen�ber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.

- Stellen Sie die beiden Konzepte _Abstrakte Klassen_  und _Interfaces_  gegen�ber und geben Sie Entscheidungshilfen zur richtigen Konzeptauswahl an.


### Observer Pattern (Hlavacek)
**Datei** Observer.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck
- Entwurfsproblem und wie das Muster das Problem l�st
- Anwendbarkeit
- Struktur des Musters