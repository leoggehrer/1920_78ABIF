### Model View Control (MVC) Pattern (Walchetseder)
**Datei** Mvc.md  


Beschreiben Sie das Muster nach den folgenden Punkten:

- Klassifikation
- Zweck  
  Trennung zwischen *Datenverarbeitung, Repr�sentation und Eingaben*.  

- **Entwurfsproblem und wie das Muster das Problem l�st**  
  Jede interaktive Anwendung besteht aus Eingaben, Daten und der Darstellung der Daten auf dem Bildschirm. Problematisch w�re es vor allem bei gr��eren Anwendungen diese drei Elemente in einer Klasse (Formular) zusammenzufassen.  
   MVC ist deswegen in drei Komponenten geteilt  
  1) Model  
  2) View  
  3) Controller  
  sind verantwortlich f�r die Steuerung der Anwendung durch den Benutzer. Sie �berwachen alle Eingabeger�te, werten die Eingabedaten aus und leiten sie weiter. �nderungen der Modelldaten werden also vom Controller eingeleitet.  
View und Controller bilden zusammen die Benutzungsoberfl�che. 
- Anwendbarkeit
- Struktur des Musters  
  