### Observer Pattern (Hlavacek)
**Datei** Observer.md

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck  
<span style="color:darkblue">
Klassen voneinander zu entkoppeln. Sie erhalten nur die Informationen die f�r die weitere Verarbeitung notwendig sind.
</span>

- Entwurfsproblem und wie das Muster das Problem l�st  
<span style="color:darkblue"> Das Problem dabei ist das eine Klasse die gesamte Schnittstelle der anderen Klasse kennt um die �nderungen mitzubekommen.  
L�sung:  
Ein Observable wird von *n* Observer beobachtet. Sobald ein Ereignis, Event oder Wert eintrifft/�ndert verst�ndigt der Observable alle Observer die am Observable registriert sind mit den dazugeh�rigen Informationen. Dabei ist nur die Observer Schnittstelle bekannt. Und die Klassen wissen sonst nichts voneinander.
</span>
- Anwendbarkeit  
<span style="color:darkblue">
MVC Pattern - wenn sich Werte �ndern m�ssen diese in der GUI aktualisiert werden.  
Simulationen - Eine FastClock wird verwendet um die Simualtion zu beschleunigen, und deshalb m�ssen Werte z.B.: 1000 mal in der Sekunde aktualisiert werden.
</span>
- Struktur des Musters  
<span style="color:darkblue">
**Ein Anbieter (Observable)** muss die Schnittstelle IObservable und eine IObservable.Subscribe() Methode implementieren die der Observer (Beobachter) aufrufen kann um Informationen zu erhalten. Eine IDisposeable-Implementierung ist notwendig um Observer wieder abzumelden.  
**Der Beobachter (Observer)** muss die Schnittstelle IObserver und die drei Methoden: IObserver.OnNext(), IObserver.OnError() und IObserver.OnComplete() implementieren.
Die Verweise von den Observer die sich beim Observable angemeldet haben, werden in einem Container (List) gespeichert um Informationen zu erhalten.
</span>