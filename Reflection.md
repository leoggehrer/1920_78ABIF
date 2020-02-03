# Reflection  
##### by Maximilian Eichinger  
Zur Laufzeit eines Programms kann es notwendig sein, dass sich das Programm selbst analysieren und ggf. ver�ndern kann.  
In C# kann dies mit der Funktionalit�t von Reflections erreicht werden.  
Die Reflection �reflektiert� zur Laufzeit aufrufbare Assemblys, Module und Typen und bietet so dynamischen Zugriff auf Objekte, Methoden und Metadaten, welche erst zur Laufzeit bekannt werden.  
Eine Programmiersprache, welche diese M�glichkeit zur �Reflektion� der eigenen Programminhalte hat, kann ihre eigene Struktur selbst zur Laufzeit analysieren und auf sie Einfluss nehmen.  
Kurz gesagt, die Reflection macht es m�glich eine Instanz einer Klasse zu erstellen und darauf Methoden aufzurufen, die zur Compile-Zeit noch nicht bekannt sind. Au�erdem ist es so m�glich den Inhalt einer DLL (z.B.: Klassen, Methoden) aufzulisten ohne den Quellcode zu kennen.  
Mit <b>typeof(...)</b> kommt man zum Beispiel an die Informationen eines bekannten Typs.  
##### Beispiel 1: 
```
// GetType verwenden um entsprechende Typ Informationen zu erhalten:   
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type); 
```  
Ergebnis: "System.Int32"  
##### Beispiel 2:  
```
// Reflection verwenden um entsprechende Informationen �ber ein Assembly zu erhalten:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);
```  
Beispielergebnis: "System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e" 
