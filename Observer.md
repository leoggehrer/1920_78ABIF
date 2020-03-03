### Observer Pattern (Hlavacek)
**Datei** Observer.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation  
<span style="color:darkblue">
Observer Pattern z�hlt zu den Design Pattern.
</span>
- Zweck  
<span style="color:darkblue">
Klassen voneinander zu entkoppeln. Sie erhalten nur die Informationen die f�r die weitere Verarbeitung notwendig sind.
</span>

- Entwurfsproblem und wie das Muster das Problem l�st  
<span style="color:darkblue"> Das Problem dabei ist das eine Klasse viel zu viel �ber die anderen Klasse weis um die �nderungen mitzubekommen.  
L�sung:  
Ein Observable wird von *n* Observer beobachtet. Sobald ein Ereignis, Event oder Wert eintrifft/�ndert verst�ndigt der Observable alle Observer die am Observable registriert sind mit den dazugeh�rigen Informationen. Die Klassen wissen sonst nichts voneinander.
</span>
- Anwendbarkeit  
<span style="color:darkblue">
MVC Pattern - wenn sich Werte �ndern m�ssen diese in der GUI aktualisiert werden.  
Sensor Messwerte - nur wenn sich der Wert �ndert wird dieser weitergegeben.  
Simulationen - Eine FastClock wird verwendet um die Simualtion zu beschleunigen, und deshalb m�ssen Werte z.B.: 1000 mal in der Sekunde aktualisiert werden.
</span>
- Struktur des Musters  

![ObserverPattern](/Desktop/Observerpattern.PNG)  
<span style="color:darkblue">
Ein NumberGenerator (Observable) verst�ndigt die Bar- und TextView (Observers) .
</span>