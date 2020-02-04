### Singleton (Seidl)

Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
  Das Singleton gehört zu den Erzeugenden Mustern
- Zweck
  Es soll sichergestellt werden, das während der gesamten Laufzeit nur ein einziges Objekt von einer bestimmten Klasse erstellt wird.
  
- Entwurfsproblem und wie das Muster das Problem löst
  In der Praxis hat man oft bestimmte Resourcen welche nur einmal geöffnet werden sollten und nicht öfters 
  bzw. wenn nicht benötigt überhaupt nicht.
  Das Singleton löst dieses Problem in dem es seinen Konstruktor als private deklariert und nach außen nur eine Funktion zum anfordern 
  des aktuellen Objects bereitstellt.
  
- Anwendbarkeit
  - Hardware Resourcen
  - von mehreren Klassen verwendete Klasse(Proxy, Verteiler,...)
  - Datenbankverbindungen
  - Netzwerk verbindungen
  - ...
- Struktur des Musters
  ```
  class MySingleton{
    private MySingleton instance;
  
    private MySingleton(){
      //do something
    }
    public static MySingleton GetInstance(){
        if(instance == NULL){
          instance = new MySingleton();
        }
        return instance;
    }
  }
  ```
