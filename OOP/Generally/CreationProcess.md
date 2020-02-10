### Compiler, Interpreter, Linker, Make

**Datei:** CreationProcess.md

##### Allgemeines
Die Aufgabe eines Compilers oder Interpreters ist es den Source Code, welcher mit einer h�heren
Programmiersprache geschrieben wurde, in den gew�nschten Assembler und schlussendlich  in Maschinensprache umzuwandeln, um ein lauff�higes Programm � das Binary- zu erhalten. F�r jeden Prozessor gibt es einen eigenen Assembler, welcher die Maschinensprache in Form von mehr oder weniger lesbaren Befehlen darstellt. Grunds�tzlich wird zwischen Compiler, Interpreter und JIT-Compiler unterschieden. Ihre Verwendung richtet sich nach der eingesetzten Hochsprache.  

<table>
 <tr>
  <td>Compiler</�td>
  <td> Pascal, Modula, COBOL, Fortran, C, C++,� </td>
 <tr>
<tr>
  <td>Interpreter</�td>
  <td> BASIC, Smalltalk, LISP, Phyton,� </td>
 <tr>
<tr>
  <td>JIT-Compiler</�td>
  <td> Java, C#, � </td>
 <tr>
</table>  
  

##### Der Compiler
Der Compiler �bersetzt den kompletten Quelltext mit einem Mal in ausf�hrbaren Code. Das somit erzeugte Programm kann danach beliebig oft ohne erneute Compilierung gestartet werden. Bei der Ausf�hrung des Programms werden die Anweisungen direkt vom Prozessor verarbeitet. Die Reihenfolge in der die Instruktionen ausgef�hrt werden, wurde vorher durch den Compiler festgelegt. M�ssen Instruktionen nicht aufeinander warten, k�nnen diese auch parallel ausgef�hrt werden.

![compiler.png](compiler.png)

<table>
 <tr>
  <td><b>+</b></td>
  <td>Die �bersetzung in ausf�hrbaren Code ist effizient und f�hrt zu einem optimierten Code. Compilierte Programme arbeiten sehr schnell, was sich besonders bei gr��eren Programmen mit langer Laufzeit lohnt.</td>
 <tr>
<tr>
  <td><b>-</b></td>
  <td>Sobald ein neues Betriebssystem oder ein neuer Prozessor zum Einsatz kommt, muss der Quelltext neu compiliert werden. In der Praxis verf�gen jedoch sowohl Betriebssysteme als auch Prozessoren �ber einen sogenannten Kompatibilit�tsmodus, welcher auch das Ausf�hren ��lterer� Programme erlaubt. </td>
 <tr>
<tr>
  <td><b>-</b></td>
  <td> Der Aufwand bei der Software-Entwicklung steigt, da bei jeder Quelltext-�nderung neu compiliert werden muss, um das Programm zu testen. </td>
 <tr>
</table> 


##### Der Interpreter
Bei Interpreter-Sprachen wird der Programmcode w�hrend der Laufzeit interpretiert und  umgewandelt.  Sowohl Eingabe und als auch Quellcode werden gleichzeitig bearbeitet. Jede Zeile mit einer Instruktion hat eine unmittelbare Aktion des Interpreters zur Folge. Die Arbeitsschritte folgen in logischer Reihenfolge laut Vorgaben des Quellcodes.

![interpreter.png](interpreter.png) 

<table>
 <tr>
  <td><b>+</b></td>
  <td>Das Programm kann direkt gestartet werden ohne das der Programmcode vom Anwender in irgendeiner Weise ver�ndert oder umgewandelt werden muss.</td>
 </tr>
 <tr>
  <td><b>+</b></td>
  <td>Interpretierte Programme sind langsamer und ineffizienter. Dieselben Programmteile, wie Schleifen und Funktionen m�ssen erneut �bersetzt werden.</td>
 </tr>
</table> 

##### JIT-Compiler
Just in Time Compiler sind eine Kombination aus Compiler und Interpreter. Man kann sich einen JIT-Compiler als eine virtuelle Maschine in Form eines k�nstlichen Prozessors vorstellen. Der vorliegende Programmcode wird mit Hilfe eines Compilers in den sogenannten Bytecode � dem Maschinencode des k�nstlichen Prozessors- umgewandelt. Bei der Ausf�hrung des Programms l�uft der virtuelle Prozessor im Hintergrund  und wandelt den Bytecode in die eigentliche Maschinensprache um.

<table>
 <tr>
  <td><b>+</b></�td>
  <td>Der JIT-Compiler bietet die M�glichkeit den einmal geschriebenen Quelltext auf unterschiedlichen Plattformen einzusetzen, da der k�nstliche Prozessor f�r jede geeignete Hardware ausprogrammiert werden kann.</td>
 </tr>
</table> 

##### Linker
Nachdem der Compiler die Dateien in Maschinencode �bersetzt hat, f�gt der Linker diese Objektdateien zu einem kompletten Programm zusammen. Er �berpr�ft welche externen Definitionen noch fehlen und durchsucht dabei sowohl die vorliegenden Objekt-Dateien als auch die vorcompilierten Standardbibliotheken. Bei fehlenden Definitionen kommt es zu einem Linker-Fehler. Im Fall dass alle Angaben vorhanden sind, wird aus den compilierten Teilen und den ben�tigten Bibliotheken eine einzige Datei erstellt, welche das lauff�hige Programm darstellt.

##### Make
Make ist ein Build-Management Tool f�r Projekte, in denen der Quellcode in verschiedenen Dateien vorliegt. Hierbei steuert das Tool automatisiert alle Arbeitsschritte (�bersetzten, Linken, Dateien kopieren etc.) bis ein fertig, ausf�hrbares Programm vorliegt. Das resultierende Makefile erfasst alle Abh�ngigkeiten und beschreibt somit welche Quelltextdateien durch den Compiler zu welchen Objektdateien verarbeitet werden sowie welche Objektdateien durch den Linker zu Programmbibliotheken oder anderen ausf�hrbaren Programmen verbunden werden. Vor allem bei gro�en Programmpaketen m�ssen somit bei kleinen �nderungen nicht alle Teile neu compiliert werden.
