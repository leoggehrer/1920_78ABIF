### Compiler, Interpreter, Linker, Make

**Datei:** CreationProcess.md

##### Allgemeines
Die Aufgabe eines Compilers oder Interpreters ist es den Source Code, welcher mit einer höheren
Programmiersprache geschrieben wurde, in den gewünschten Assembler und schlussendlich  in Maschinensprache umzuwandeln, um ein lauffähiges Programm – das Binary- zu erhalten. Für jeden Prozessor gibt es einen eigenen Assembler, welcher die Maschinensprache in Form von mehr oder weniger lesbaren Befehlen darstellt. Grundsätzlich wird zwischen Compiler, Interpreter und JIT-Compiler unterschieden. Ihre Verwendung richtet sich nach der eingesetzten Hochsprache.  

<table>
 <tr>
  <td>Compiler</´td>
  <td> Pascal, Modula, COBOL, Fortran, C, C++,… </td>
 <tr>
<tr>
  <td>Interpreter</´td>
  <td> BASIC, Smalltalk, LISP, Phyton,… </td>
 <tr>
<tr>
  <td>JIT-Compiler</´td>
  <td> Java, C#, … </td>
 <tr>
</table>  
  

##### Der Compiler
Der Compiler übersetzt den kompletten Quelltext mit einem Mal in ausführbaren Code. Das somit erzeugte Programm kann danach beliebig oft ohne erneute Compilierung gestartet werden. Bei der Ausführung des Programms werden die Anweisungen direkt vom Prozessor verarbeitet. Die Reihenfolge in der die Instruktionen ausgeführt werden, wurde vorher durch den Compiler festgelegt. Müssen Instruktionen nicht aufeinander warten, können diese auch parallel ausgeführt werden.

![compiler.png](compiler.png)

<table>
 <tr>
  <td><b>+</b></td>
  <td>Die Übersetzung in ausführbaren Code ist effizient und führt zu einem optimierten Code. Compilierte Programme arbeiten sehr schnell, was sich besonders bei größeren Programmen mit langer Laufzeit lohnt.</td>
 <tr>
<tr>
  <td><b>-</b></td>
  <td>Sobald ein neues Betriebssystem oder ein neuer Prozessor zum Einsatz kommt, muss der Quelltext neu compiliert werden. In der Praxis verfügen jedoch sowohl Betriebssysteme als auch Prozessoren über einen sogenannten Kompatibilitätsmodus, welcher auch das Ausführen „älterer“ Programme erlaubt. </td>
 <tr>
<tr>
  <td><b>-</b></td>
  <td> Der Aufwand bei der Software-Entwicklung steigt, da bei jeder Quelltext-Änderung neu compiliert werden muss, um das Programm zu testen. </td>
 <tr>
</table> 


##### Der Interpreter
Bei Interpreter-Sprachen wird der Programmcode während der Laufzeit interpretiert und  umgewandelt.  Sowohl Eingabe und als auch Quellcode werden gleichzeitig bearbeitet. Jede Zeile mit einer Instruktion hat eine unmittelbare Aktion des Interpreters zur Folge. Die Arbeitsschritte folgen in logischer Reihenfolge laut Vorgaben des Quellcodes.

![interpreter.png](interpreter.png) 

<table>
 <tr>
  <td><b>+</b></td>
  <td>Das Programm kann direkt gestartet werden ohne das der Programmcode vom Anwender in irgendeiner Weise verändert oder umgewandelt werden muss.</td>
 </tr>
 <tr>
  <td><b>+</b></td>
  <td>Interpretierte Programme sind langsamer und ineffizienter. Dieselben Programmteile, wie Schleifen und Funktionen müssen erneut übersetzt werden.</td>
 </tr>
</table> 

##### JIT-Compiler
Just in Time Compiler sind eine Kombination aus Compiler und Interpreter. Man kann sich einen JIT-Compiler als eine virtuelle Maschine in Form eines künstlichen Prozessors vorstellen. Der vorliegende Programmcode wird mit Hilfe eines Compilers in den sogenannten Bytecode – dem Maschinencode des künstlichen Prozessors- umgewandelt. Bei der Ausführung des Programms läuft der virtuelle Prozessor im Hintergrund  und wandelt den Bytecode in die eigentliche Maschinensprache um.

<table>
 <tr>
  <td><b>+</b></´td>
  <td>Der JIT-Compiler bietet die Möglichkeit den einmal geschriebenen Quelltext auf unterschiedlichen Plattformen einzusetzen, da der künstliche Prozessor für jede geeignete Hardware ausprogrammiert werden kann.</td>
 </tr>
</table> 

##### Linker
Nachdem der Compiler die Dateien in Maschinencode übersetzt hat, fügt der Linker diese Objektdateien zu einem kompletten Programm zusammen. Er überprüft welche externen Definitionen noch fehlen und durchsucht dabei sowohl die vorliegenden Objekt-Dateien als auch die vorcompilierten Standardbibliotheken. Bei fehlenden Definitionen kommt es zu einem Linker-Fehler. Im Fall dass alle Angaben vorhanden sind, wird aus den compilierten Teilen und den benötigten Bibliotheken eine einzige Datei erstellt, welche das lauffähige Programm darstellt.

##### Make
Make ist ein Build-Management Tool für Projekte, in denen der Quellcode in verschiedenen Dateien vorliegt. Hierbei steuert das Tool automatisiert alle Arbeitsschritte (Übersetzten, Linken, Dateien kopieren etc.) bis ein fertig, ausführbares Programm vorliegt. Das resultierende Makefile erfasst alle Abhängigkeiten und beschreibt somit welche Quelltextdateien durch den Compiler zu welchen Objektdateien verarbeitet werden sowie welche Objektdateien durch den Linker zu Programmbibliotheken oder anderen ausführbaren Programmen verbunden werden. Vor allem bei großen Programmpaketen müssen somit bei kleinen Änderungen nicht alle Teile neu compiliert werden.
