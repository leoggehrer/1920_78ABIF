# Schleifen und deren Einsatzzweck

Es gibt viele Situationen, in denen eine Anweisung nicht nur einmal, 
sondern mehrfach ausgef�hrt werden soll. 
Dazu k�nnte man grunds�tzlich die Anweisung im Programmcode einfach mehrmals hintereinander
notieren, so oft wie es das Programm erfordern w�rde:

![anweisungsfolge](https://homepages.fhv.at/fw/fhvwbt/img/07_001_anweisungsfolge2.gif)

Ist jedoch sehr aufw�ndig und fehleranf�llig.
Deshalb gibt es verschiedene Schleifen um diese Arbeit zu erleichtern.

- **Bedingungsgesteuerte Schleifen:**

Eine bedingungsgesteuerte Schleife erm�glicht es, 
eine Anweisung ausf�hren zu lassen, 
solange eine klar definierte und logisch �berpr�fbare (true/false) Bedingung erf�llt ist.

![bedingsgesteuerte Schleife](https://homepages.fhv.at/fw/fhvwbt/img/07_003_schleife2.gif)

- Abweisende Schleife / While-Schleife (kopfgesteuert):

Bei der abweisenden Schleife erfolgt die Bedingungspr�fung am Beginn der Schleife.
Falls das Resultat dieser Pr�fung das Ergebnis "true" liefert, 
wird die Anweisung ausgef�hrt. Anschlie�end wird die Bedingung erneut gepr�ft usw. 
Die Anweisung wird solange ausgef�hrt, 
bis die �berpr�fung der Schleifenbedingung das Ergebnis "false" liefert.

	while (bedingung){
       anweisung
	}

![Flussdiagramm](https://homepages.fhv.at/fw/fhvwbt/img/07_005_while_schleife-flussidagr.gif)

- Durchlaufende Schleife / Do-While-Schleife (fu�gesteuert):

Gleich wie die While-Schleife mit Ausnahme, dass die Anweisung vor �berpr�fung der Bedingung erfolgt.

![Fluss-Do-While](https://homepages.fhv.at/fw/fhvwbt/img/07_010_do_while.gif)

- Z�hlschleife / For-Schleife:

Die Z�hlschleife wird dann verwendet, 
wenn die Anzahl der Schleifendurchl�ufe festgelegt werden soll. 
Bei einer for-Schleife wird eine spezielle Variable, 
die so genannte Z�hlvariable verwendet, um die Anzahl der Schleifendurchl�ufe zu z�hlen. 
Die for-Schleife wird beendet, 
wenn der Wert der Z�hlvariablen eine bestimmte Bedingung nicht mehr erf�llt.

	for (Initialisierung; Abbruchbedingung; Wert�nderung) {
     Anweisungen
	}

![Fluss-For](https://homepages.fhv.at/fw/fhvwbt/img/07_014_for_schleife-flussdiagr.gif)

- Foreach-Schleife (in C#)

In CSharp gibt es eine weitere Art von Schleifen, die "foreach" Schleife. Sie wird bei
"Sammlungen" verwendet. Zum Beispiel bei Listen, Arrays, usw. Grunds�tzlich bei iterierbaren
Objekten. Mit der foreach-Schleife erspart man sich das deklarieren von Variablen um �berhaupt �ber das
Objekt iterieren zu k�nnen. Wie schon der Name sagt f�hrt diese Schleife die Anweisung f�r jedes vorhandene
Objekt in der Sammlung aus

Beispiel:

	int[] example = new int[] {1, 2, 3, 4, 5};

mit for-Schleife:

	for (i = 0, i < example.length; i++)
	{
		Console.WriteLine(example[i]);
	}

mit foreach:

	foreach(int number in example)
	{
		Console.WriteLine(number);
	}

