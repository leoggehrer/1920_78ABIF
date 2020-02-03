# Eventhandling  
##### by Maximilian Eichinger  
Beim Programmieren kommt es sehr oft vor das ein bestimmter Quellcode bei einem bestimmten Ereignis (Event) ausgef�hrt werden muss oder auch dass ein bestimmter Status erreicht wird.  
In vielen F�llen liegt es hierbei an �fremden� Objekten, dass etwas passiert ist, dann soll jedoch entsprechend darauf reagiert werden.  
Eine Nachricht muss von diesem �fremden� Objekt empfangen werden, wenn das entsprechende Ereignis (Event) eintritt.  
Es gibt seitens Visual Studio schon vorgefertige Events z.B.: click-Event  bei anclicken eines Buttons.  
Man kann aber auch eigene Events definieren bzw. festlegen.  
Beispiel:  
```
// Event festlegen/ definieren
button1.Click += new EventHandler(Button1_Click);

// Methode die aufgerufen wird, wenn das Buttonclickevent ausgel�st wurde
private void Button1_Click(object sender, EventArgs e)  
{ 
    //TODO
}
```  
### Fr�here Prinzipien:  
#### Polling, Interrupt  
##### Polling
Unter Polling versteht man in der Informatik eine zyklische Abfrage.  
Der Nachteil hier ist, dass mehr Rechenleistung ben�tigt wird und bei der Abfrage eine Verz�gerung auftritt da der Ablauf in einer Schleife stattfindet.  
Kurz gesagt beim Polling wird st�ndig nachgefragt ob sich ein bestimmter Status ge�ndert hat oder nicht.  
Beispiel:  
 
[Beispiel Polling](https://pic-projekte.de/blog/pic18-tutorial-interrupt-konfig-und-icsp/)

##### Interrupt  
Unter einem Interrupt versteht man eine vor�bergehende Unterbrechung einer laufenden Aufgabe des Prozessors.  
Die Nutzung von Interrupts ist eine sehr effektive Art um auf nicht regelm��g auftretende Ereignisse (Events) zu reagieren.  
So eine Anwendung findet man zum Beispiel in der Mikrocontroller Programmierung.  
Beispiel:  
 
[Beispiel Interrupt](https://pic-projekte.de/blog/pic18-tutorial-interrupt-konfig-und-icsp/)



