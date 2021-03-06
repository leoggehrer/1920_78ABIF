# Technik/Serialisierung
## Autor: Peterseil Christoph
### Erklären Sie die Technik 'Serialisierung von Objekten' und 'Deserialisierung von Objekten'.

Bei der Serialisierung wird ein Objekt in einen Stream konvertiert, um das Objekt zu speichern oder in den Speicher, einer Datenbank oder einer Datei zu übertragen.  

Der Hauptzweck ist ein Objekts zu speichern, um es bei Bedarf neu erstellen (wiederherstellen) zu können. Der umgekehrte Vorgang der Serealisierung wird Deserialisierung genannt.  

Im .Net Framework gibt es verschieden vorgefertigte Serializer z.B. XML, JSON oder Binary, man kann aber auch selber einen Serializer schreiben.  

Als Beispiel der Seralisierung und Deserealisierung einer Liste von Serealisierbaren Objekten in eine Datei.
 
```csharp
[Serializable]
class Test
{
    public string Name {get; set;}
    ...
}

//Serealisierung
public void Serialize()
{
    ...
    IFormatter formatter = new BinaryFormatter();
    Stream stream = new FileStream(filepath, FileMode.Create, FileAccess.Write);

    formatter.Serialize(stream, tests);
    stream.Close();
    ...
}

//Deserealisierung
public void Deserialize()
{
    ...
    IFormatter formatter = new BinaryFormatter();
    Stream stream = new FileStream(filepath, FileMode.Open, FileAccess.Read);
    var tests = (List<Test>)formatter.Deserialize(stream);
    ...
}
```
<br/>

### Serialisierung und Deserialisierung ist eine wichtige Basistechnik für weitere höhere (Architektur-)Konzepte. Nennen Sie eine weitere Technik, welche Serialisierung und Deserialisierung als Basis verwendet.

#### z.B.: .NET Remoting

".Net Remoting" ist ein Technologie die Serealisierung als Basis hat, Serealisierung wird eingesetzt bei der Übertragung des Fernaufrufs.
Zur Übertragung des Fernaufrufs wird ein **Formatter** eingesetzt.
Ein **Formatter** ist in diesem Fall ein Mechanismus, der ein Objekt in einen Byte-Strom umwandelt bzw. zurückwandelt. Das ist Serealisierung, bzw. Deserealisierung!