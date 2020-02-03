# Konzepte
## by Martin Pechak
##Erkl�ren Sie die folgenden Begriffe im Zusammenhang (Gegen�berstellung):
**Datei:** OopConcepts.md

- Klasse \<-\> Objekt
- Basisreferenz \<-\> Selbstreferenz
- Konstruktors \<-\> Destruktors
- Defaultkonstruktor \<-\> Standardkonstruktor
- �berladen von Methoden \<-\> �berladen von Operatoren

Erl�utern Sie die Standard-Methoden

- Welche kennen Sie (nennen Sie mind. 3)?
- Geben Sie deren Zweck an

Erl�utern Sie das �berladen von Methoden

- Geben Sie den Zweck an (geben Sie ein Beispiel an)

Erkl�ren und erl�utern Sie die Arten von

- Klassenmembers und Objektmembers.

Welche Entscheidungshilfen wenden Sie zur Identifizierung von

- Klassenmethoden und
- Exemplarmethoden (Objektmembers) an?

Erkl�ren Sie den Unterschied zwischen einer

- 'Rein virtuelle Methoden' und einer
- 'virtuelle Methoden' 

## Antwort
##Erkl�ren Sie die folgenden Begriffe im Zusammenhang (Gegen�berstellung):

- Klasse \<-\> Objekt
Als Klasse kann man sich eine Art Schablone vorstellen, die einige Informationen enth�lt.
Ein Objekt ist eine Abbildung dieser Schablone
```
// Beispiel einer Klasse:
public class Person
{
    public string Firstname { get; set; }
    public string Lastname { get; set; }
    public string Email { get; set; }
    public string Country { get; set; }
}
// Beispiel eines Objektes:
public void Main()
{
    ...

    Person MyFirstPerson = new Person();

    ...
}
// MyFirstPerson ist ein Objekt, welches die Eigenschaften und die Methoden aus der Klasse Person enth�lt
```
- Basisreferenz \<-\> Selbstreferenz

- Konstruktors \<-\> Destruktors
Konstruktoren werden automaitisch aufgerufen, wenn eine Objekt instanziert wird. Sie m�ssen den selben Namen aufweisen wie die Klasse, zu der sie geh�ren. Konstruktoren k�nnen keinen R�ckgabewert haben. Es sit m�glich, Konstruktoren zu �berladen. Somit ist es z.B. M�glich, einen "leeren" Konstruktor sowie eien, der Werte zu begin setzt, zu haben.
Dekonstruktoren werden von der CLR auffgerufen, wenn diese entdeckt, dass ein Objekt nicht l�nger ben�tigt wird. Sie haben ebenfalls den selben Namen wie die Klasse, habe jedoch am Anfang eine Tilde (~). Es ist m�glich, exakt zu bestimmen, wann ein Deconstructor aufgerufen wird.
```
public class Person
{

    public string Firstname { get; set; }
    public string Lastname { get; set; }
    public string Email { get; set; }
    public string Country { get; set; }

    // constructor
    public Person() {}

    // second constructor
    public Person(firstname, lastname, email, country)
    {
        Firstname = firstname;
        Lastname = lastname;
        Email = email;
        Country = country;
    }

    // deconstructor
    ~Person
    {
        // Finalizer implementation
    }
}
// usage of the constructors
public void Main()
{
    Person firstPerson = new Person();

    Person secondPerson = new Person("Max", "Mustermann", "max.mustermann@yahoo.de", "Germany");
}


```
- Defaultkonstruktor \<-\> Standardkonstruktor
- �berladen von Methoden \<-\> �berladen von Operatoren

Erl�utern Sie die Standard-Methoden

- Welche kennen Sie (nennen Sie mind. 3)?
- Geben Sie deren Zweck an

Erl�utern Sie das �berladen von Methoden

- Geben Sie den Zweck an (geben Sie ein Beispiel an)

Erkl�ren und erl�utern Sie die Arten von

- Klassenmembers und Objektmembers.

Welche Entscheidungshilfen wenden Sie zur Identifizierung von

- Klassenmethoden und
- Exemplarmethoden (Objektmembers) an?

Erkl�ren Sie den Unterschied zwischen einer

- 'Rein virtuelle Methoden' und einer
- 'virtuelle Methoden' 