### OOP - Equals() / GetHashCode() ###
----
#### Markus Mühleder
---
- Erklären Sie die Gleichheit von Objekten (erklären Sie wann 2 Objekte gleich sind und erläutern Sie den Equals/HashCode Vertrag)
----
Grundsätzlich wird zwischen Typengleichehit, Wertgleichheit und Verweisgleichheit unterschieden.
#### Verweisgleichheit ####
Beide Instanzen greifen auf den Selben Speicher zu, Equalsoperator muss nicht überschriben werden.
<pre><code class='language-cs'>
            Person p1 = new Person("Peter Hans");
            p1.Mum = new Person("Mum of Hans");
            p1.Dad = new Person("Dad of Hans");

            Person p2 = p1; 
           
            //Refereenzgleichheit --> Typengleichheit und Wertgleichheit
            Console.WriteLine(p2 == p1); //True
</code></pre>

#### Typengelichheit ####
Bedeutet, dass die Typen zweier Instanzen gleich sind. Dies kann über den is Opderator überprüft werden und somit beim überschreiben der Equalsmethode angewendet werden.
<pre><code class='language-cs'>
        public override bool Equals(Object obj)
        {
            if (obj is Worker) return true;
            return false;
        }
</code></pre>

#### Wertegleichheit ###
Wertegleichheit besteht wenn die Werte zweier Instanzen gleich sind und geht grundsätzlich mit der Typengleichheit einher.
<pre><code class='language-cs'>
        public override bool Equals(Object obj)
        {
            Worker personObj = obj as Worker;
            if (personObj == null)
                return false;
            else
                return Name.Equals(personObj.Name) && Age.Equals(personObj.Age); 
        }
</pre></code>


Wird Equals() überschieben so muss auch immer GetHashCode() überschrieben werden um die erfüllung der Verträge zu gewährleisten.



#### Equals Vertrag #####

- x.Equals(x) returns true, except in cases that involve floating-point types. 
- x.Equals(y) returns the same value as y.Equals(x).
- x.Equals(y) returns true if both x and y are NaN.
- If (x.Equals(y) && y.Equals(z)) returns true, then x.Equals(z) returns true.
- Successive calls to x.Equals(y) return the same value as long as the objects referenced by x and y are not modified.
x.Equals(null) returns false.

Implementations of Equals must not throw exceptions; they should always return a value. For example, if obj is null, the Equals method should return false instead of throwing an ArgumentNullException.

#### HashCode Vertrag #####

- Immer, wenn GetHashCode() für dasselbe Objekt mehrmals aufgerufen wird 
muss bei der Ausführung muss GetHashCode() den gleichen Wert konsistent zurückgeben, vorausgesetzt, es werden keine Informationen geändert, die für Vergleiche mit gleichen Objekten verwendet werden. Dieser Wert muss nicht konsistent von einer Ausführung einer Anwendung zu einer anderen Ausführung derselben Anwendung bleiben 
- Wenn zwei Objekte nach der Methode equals (Object) gleich sind, 
und Sie dann die Methode hashCode () für jedes der beiden Objekte aufrufen, muss derselbe Wert erzeugt werden 
- Es ist nicht erforderlich, dass wenn zwei Objekte ungleich sind 
der Hashwert ungleich ist jedoch ist ein eindeutiges ganzzahliges Ergebnis für ungleiche Objekte Leistungssteigernd für Hashtables

Dont's beim Hashcode (msdn):
- Do not serialize hash code values or store them in databases.
- Do not use the hash code as the key to retrieve an object from a keyed collection.
- Do not send hash codes across application domains or processes. In some cases, hash codes may be computed on a per-process or per-application domain basis.
- Do not use the hash code instead of a value returned by a cryptographic hashing function if you need a cryptographically strong hash. For cryptographic hashes, use a class derived from the System.Security.Cryptography.HashAlgorithm or System.Security.Cryptography.KeyedHashAlgorithm class.
- Do not test for equality of hash codes to determine whether two objects are equal. (Unequal objects can have identical hash codes.) To test for equality, call the ReferenceEquals or Equals method.

