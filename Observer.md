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
<span style="color:darkblue"> Das Problem dabei ist das immer alle Observer verständigt werden, auch wenn sie nicht mehr an den Benachrichtigungen interessiert sind.  
Lösung:  
Ein Observable wird von *n* Observer beobachtet. Sobald ein Ereignis, Event oder Wert eintrifft/ändert verständigt der Observable alle Observer die am Observable registriert sind mit den dazugehörigen Informationen. Sobald ein Observer nicht mehr an den Benachrichtigungen interessiert ist, kann sich dieser beim Observable wieder abmelden. Somit wird dieser nicht mehr verständigt.
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