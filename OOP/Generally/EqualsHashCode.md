- Erkl�ren Sie die Gleichheit von Objekten (erkl�ren Sie wann 2 Objekte gleich sind und erl�utern Sie den Equals/HashCode Vertrag)
----
Grunds�tzlich wird zwischen Typengleichehit, Wertgleichheit und Verweisgleichheit.
#### Verweisgleichheit ####
Beide Instanzen greifen auf den Selben Speicher zu, Equalsoperator muss nicht �berschriben werden.
<pre><code class='language-cs'>
            Person p1 = new Person("Peter Hans");
            p1.Mum = new Person("Mum of Hans");
            p1.Dad = new Person("Dad of Hans");

            Person p2 = p1; 
           
            //Refereenzgleichheit --> Typengleichheit und Wertgleichheit
            Console.WriteLine(p2 == p1); //True
</code></pre>

#### Typengelichheit ####
Bedeutet, dass die Typen zweier Instanzen gleich sind. Dies kann �ber den is Opderator �berpr�ft werden und somit beim �berschreiben der Equalsmethode angewendet werden.
<pre><code class='language-cs'>
        public override bool Equals(Object obj)
        {
            if (obj is Worker) return true;
            return false;
        }
</code></pre>

#### Wertegleichheit ###
Wertegelichheit besteht wenn die Werte zweier Instanzen gleich sind und geht grunds�tzlich mit der Typengelichheit einher.
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


Wird Equals() �berschieben so muss auch immer GetHashCode() �berschrieben werden.



#### Equals Vertrag #####

- x.Equals(x) returns true, except in cases that involve floating-point types. 
- x.Equals(y) returns the same value as y.Equals(x).
- x.Equals(y) returns true if both x and y are NaN.
- If (x.Equals(y) && y.Equals(z)) returns true, then x.Equals(z) returns true.
- Successive calls to x.Equals(y) return the same value as long as the objects referenced by x and y are not modified.
x.Equals(null) returns false.

Implementations of Equals must not throw exceptions; they should always return a value. For example, if obj is null, the Equals method should return false instead of throwing an ArgumentNullException.

#### HashCode Vertrag #####

internal consistency : Der Wert von hashCode () kann sich nur �ndern, wenn a 
Eigenschaft, die sich in equals () �ndert equals Konsistenz : Objekte, die einander gleich sind, m�ssen 
gib den gleichen Hashcode zur�ck collisions : ungleiche Objekte k�nnen den gleichen Hash-Code haben 

