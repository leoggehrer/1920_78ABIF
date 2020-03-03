### Observer Pattern (Hlavacek)
**Datei** Observer.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation  
<span style="color:darkblue">
Observer Pattern zählt zu den Design Pattern.
</span>
- Zweck  
<span style="color:darkblue">
Klassen voneinander zu entkoppeln. Sie erhalten nur die Informationen die für die weitere Verarbeitung notwendig sind.
</span>

- Entwurfsproblem und wie das Muster das Problem löst  
<span style="color:darkblue"> Das Problem dabei ist das eine Klasse viel zu viel über die anderen Klasse weis um die änderungen mitzubekommen.  
Lösung:  
Ein Observable wird von *n* Observer beobachtet. Sobald ein Ereignis, Event oder Wert eintrifft/ändert verständigt der Observable alle Observer die am Observable registriert sind mit den dazugehörigen Informationen. Die Klassen wissen sonst nichts voneinander.
</span>
- Anwendbarkeit  
<span style="color:darkblue">
MVC Pattern - wenn sich Werte ändern müssen diese in der GUI aktualisiert werden.  
Sensor Messwerte - nur wenn sich der Wert ändert wird dieser weitergegeben.  
Simulationen - Eine FastClock wird verwendet um die Simualtion zu beschleunigen, und deshalb müssen Werte z.B.: 1000 mal in der Sekunde aktualisiert werden.
</span>
- Struktur des Musters  

![ObserverPattern](/Desktop/Observerpattern.PNG)  
<span style="color:darkblue">
Ein NumberGenerator (Observable) verständigt die Bar- und TextView (Observers) .
</span>