### Model View View-Model (MVVM) Pattern
  ![alt text](MVVMPattern.png "MVVM Pattern") 

#### - Klassifikation
Das MVVM Pattern z�hlt zu den Architektur Pattern mit dazu.
Es bietet einige Verbesserungen zum MVC Pattern aber auch einige Nachteile.
Gegen�ber dem MVC Pattern l�sst sich das MVVM Pattern leichter Testen und es besteht die M�glichkeit einer Trennung zwischen Designern und Entwicklern.
#### - Zweck 
Es dient zur trennung zwischen Logik und Benutzerschnittstelle.
Somit kann man die Rollen zwischen Designer und Entwickler trennen.
Sp�tere �nderungen und Erweiterungen werden durch das Pattern erleichtert. 
Auch die wiederverwendbarkeit wird erleichtert.
#### - Entwurfsproblem und wie das Muster das Problem l�st   

  - Die Gesch�ftslogik h�ngt sehr Stark mit der View zusammen
    - Dandurch das Elemente der View via Databinding mit dem ViewModel verbunden sind kann die View sehr einfach ohne �nderungen am VM ausgetauscht werden
  - Der Controller bei MVC kann nur mit der View Instanziert werden
    - Beim MVVM Pattern kann das ViewModel ohne View instanziert werden, wodurch es nun m�glich ist das ViewModel via Unit Test zu testen
  - Die View kann nicht ohne Controller alleine Gestaltet werden
    - Die View kann dadurch das sie nicht mit dem ViewModel verbunden ist von einem Designer designt werden (Data Binding und Events werden zum Trennen der View und des ViewModels verwendet)
  - Mann kann keine 2 View zum Contoller erstellen (MVC) ohne den Controller daf�r abzu�ndern. Die View besitzt eine Referenz zum Controller
    - Durch die Trennug von View, ViewModel und Model kann ein ViewModel und Model meherere Views besitzen ohne das, das Viewmodel oder Model mit ver�ndert werden muss.
    - MVVM verschiebt die Datendarstellung der View in das ViewModel wodurch die Abh�ngigkeit von View und Model entf�llt.
    - Dessweitern beistzt das ViewModel keine abh�ngikeit zur View
#### - Anwendbarkeit     
 
  - das MVVM Pattern wird f�r Angular und WPF verwendet.
  - Es wird f�r gro�e Software Projekte verwendet, da es eine Trnnung zwischen Entwickler und Designer em�glicht
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
  - Die View ist f�r die Darstellung des Programmes verantwortlich
##### ViewModel
  - Das ViewModel implementiert Eigenschaften und Befehle. Die View kann sich an diese Eigenschaften binden. 
  - Bei Ver�nderungen Benachrichtigt das VM die View.
  - Das ViewModel ist auch daf�r verantwortlich, die Interaktionen der Ansicht mit allen erforderlichen Modellklassen zu koordinieren.
##### Model
  - Kapseln die Daten der APP.