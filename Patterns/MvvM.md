# Patterns
Autor: Markus Freudenthaler
### Model View View-Model (MVVM) Pattern
  ![alt text](MVVMPattern.png "MVVM Pattern") 

#### - Klassifikation
Das MVVM Pattern zählt zu den Architektur Pattern mit dazu.
Es bietet einige Verbesserungen zum MVC Pattern aber auch einige Nachteile.
Gegenüber dem MVC Pattern lässt sich das MVVM Pattern leichter Testen und es besteht die Möglichkeit einer Trennung zwischen Designern und Entwicklern.
#### - Zweck 
Es dient zur trennung zwischen Logik und Benutzerschnittstelle.
Somit kann man die Rollen zwischen Designer und Entwickler trennen.
Spätere Änderungen und Erweiterungen werden durch das Pattern erleichtert. 
Auch die wiederverwendbarkeit wird erleichtert.
#### - Entwurfsproblem und wie das Muster das Problem löst   

  - Die Geschäftslogik hängt sehr Stark mit der View zusammen
    - Dandurch das Elemente der View via Databinding mit dem ViewModel verbunden sind kann die View sehr einfach ohne änderungen am VM ausgetauscht werden
  - Der Controller bei MVC kann nur mit der View Instanziert werden
    - Beim MVVM Pattern kann das ViewModel ohne View instanziert werden, wodurch es nun möglich ist das ViewModel via Unit Test zu testen
  - Die View kann nicht ohne Controller alleine Gestaltet werden
    - Die View kann dadurch das sie nicht mit dem ViewModel verbunden ist von einem Designer designt werden (Data Binding und Events werden zum Trennen der View und des ViewModels verwendet)
  - Mann kann keine 2 View zum Contoller erstellen (MVC) ohne den Controller dafür abzuändern. Die View besitzt eine Referenz zum Controller
    - Durch die Trennug von View, ViewModel und Model kann ein ViewModel und Model meherere Views besitzen ohne das, das Viewmodel oder Model mit verändert werden muss.
    - MVVM verschiebt die Datendarstellung der View in das ViewModel wodurch die Abhängigkeit von View und Model entfällt.
    - Dessweitern beistzt das ViewModel keine abhängikeit zur View
#### - Anwendbarkeit     
 
  - das MVVM Pattern wird für Angular und WPF verwendet.
  - Es wird für große Software Projekte verwendet, da es eine Trnnung zwischen Entwickler und Designer emöglicht
#### - Struktur des Musters
  ![alt text](mvvmMuster.png "MVVM Muster") 
  - Es gibt 3 Kernkompunenten im MVVM Modell
    - View (Ansicht)
    - ViewModel (Ansichts model)
    - Model (Model)
  - Jedes dieser 3 Kompunenten hat einen bestimmten Zweck
  - Die View kennt das ViewModel und das ViewModel kennt das Model. Die View kennt aber das Model nicht und das ViewModel kennt die View nicht.
    - Dieser Umstand brinngt den Vorteil das die View ohne Model entwickelt werden kann.
##### View
  - Die View ist für die Darstellung des Programmes verantwortlich
##### ViewModel
  - Das ViewModel implementiert Eigenschaften und Befehle. Die View kann sich an diese Eigenschaften binden. 
  - Bei Veränderungen Benachrichtigt das VM die View.
  - Das ViewModel ist auch dafür verantwortlich, die Interaktionen der Ansicht mit allen erforderlichen Modellklassen zu koordinieren.
##### Model
  - Kapseln die Daten der APP.