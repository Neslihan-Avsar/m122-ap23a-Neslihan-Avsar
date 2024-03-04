# 03 - Shellprogrammierung

### Erstellen und Ausführung eines Shellscripts

```
$ touch hello_world.sh
$ vi hello_world.sh
```

Hier wird das File ```hello_world.sh``` erstellt und im Texteditor geöffnet.  

```
#!/bin/bash

echo "Hello, World!"
```

Hier wird im File spezifiziert, dass es mit Bash ausgeführt werden sollte und "Hello, World!" anzeigen sollte.  

```
$ chmod +x hello_world.sh
$ ./hello_world.sh

"Hello, World!"
```

Hier wird das File ausführbar gemacht und anschliessend getestet/ausgefürt.

### Variablen

So erstellt und verwendet man Variablen:

```
$ name="Neslihan"
$ echo $name

"Neslihan"
```

Mit dem ```=``` Operator wird es declariert und definiert Es kann auch so gelöscht werden:

```
$ name=
```

Mit dem ```readonly``` Keyword kann eine Variabel zuer Konstante werden (bzw. es darf nicht verändert werden=).

```
$ readonly name="Neslihan"
$ name="NeuerName" # DIES WIRD NICHT FUNKTIONIEREN, DA ES SCHREIBGESCHÜTZT IST
```

Wichtige Regeln:
1.  Beim ```=``` Operator darf kein Abstand daneben stehen.
2.  Die Variablen sind case-sensitive (```$ $VAR != $var```)
3.  Wenn eine schon bestehende Variable referenziert wird, muss es vorne mit ```$``` beginnen.
4.  Eine Variable darf nicht mit einer Zahl beginnen.

Einige automatisch verwalteten Variablen von Bash sind folgende:
- `$LOGNAME` Login-Name des aktiven Benutzers
- `$0` Name des aufgerufenen Shellscripts
- `$>0` (1-9, ab 10 ist es in {}) Parameter des aufgerufenen Shellscripts
- `$#` Anzahl der Parameter des aufgerufenen Shellscripts
- `$$` Die Prozessnummer des aufgerufenen Shellscripts
- `$?` Der Beendigungsstatus eines Shellscripts
- `$!` Die Prozessnummer des zuletzt gestarteten Hintergrundprozesses
- `$PWD` Aktuelles Arbeitsverzeichnis
- `$OLDPWD` Der Wert ist das zuvor besuchte Arbeitsverzeichnis; wird vom Kommando cd gesetzt
- `$HOME` Heimverzeichnis für den Benutzer; Standardwert für cd
- `$UID` Die User-ID des Anwenders. Diese Kennung ist in der Datei /etc/passwd dem Benutzernamen zugeordnet
- `$PATH` Suchpfad für die Kommandos (Programme)
- `$CDPATH` Suchpfad für das cd-Kommando
- `$SHELL` Zeigt die aktuelle Shell mit dem Pfad an
- `$RANDOM` Pseudo-Zufallszahl zwischen 0 bis 32767
- `$REPLY` Bei Menüs (select) enthält REPLY die ausgewählte Nummer
- `$SECONDS` Enthält die Anzahl von Sekunden, die seit dem Start (Login) der aktuellen Shell vergangen ist
- `$PROMPT_COMMAND` Hier kann ein Kommando angegeben werden, das vor jeder Eingabeaufforderung automatisch ausgeführt wird
- `$PS1` Primärer Prompt; Prompt zur Eingabe von Befehlen
- `$TZ` Legt die Zeitzone fest (hierzulande MET = Middle European Time)

Zum Ausrechnen von arithmetische Operationen:

```
$ var=$((Int-Arithmetik))
# ODER
$ var=$[Int-Artithmetik]

# ES GEHT AUCH OHNE EINER ZUWEISUNG
$ [$var++]
```

Dabei muss man Fliesskommazahlen mit dem Pipe-Tool ```bc``` anzeigen lassen.  
Die typischen C-Style Operatoren können verwendet werden.

Übergabe von Arguments/Parameter läuft so:

```
$ set tim bill an fred
      $1  $2   $3 $4
$ echo $*

tim bill an fred
# HIER WURDEN ALLE WIDERGEBEN DURCH DEN WILDCARD *

$ echo $#

4
# HIER WURDE DIE ANZAHL PARAMETER WIDERGEBEN
```

### Schleifen/Kontrollstrukturen

Hier ist ein Beispiel eines for-loops:

```
for datei in *.txt
do
  echo $datei
  [-r £datei] && echo " ist lesbar"
  [-w $datei] && echo " ist schreibar"
done
```

In diesem Fall werden auch if-statements verwendet (boolean).

### Standardeingabe und -ausgabe

- `stdin` ist die Standardeingabe (0)
- `stdout` ist die Standardausgabe (1)
- `stderr` ist die Standardfehlerausgabe (2)

Mit `>` kann man eine Datei überschreiben und mit `>>` etwas an einer Datei anhängen.  
So wird die `stdout` umgeleitet.  

Will man die Ausgabe zusammenkoppeln mit einer anderen oder sie unterdrücken, kann man dies so erreichen:

```
# JETZT WERDEN ALLE NORMALE UND FEHLERHAFTEN AUSGABEN NACH OUTPUT.TXT GELEITET UND NICHT AUF DEM BILDSCHIRM ANGEZEIGT
$ ./script > output.txt 2>&1
```

und 

```
# JETZT WIRD ALLES AUSSER FEHLERMELDUNGEN NACH OUTPUT.TXT GELEITET, DA 2 ZUM LINUX-DATENSCHREDDER UMGELEITET WURDE
$ ./script > output.txt 2>/dev/null
```

Zur Eingabe von User Inputs:

```
# HIER WIRD ES AUF INPUT MODE UMGESCHALTET + DAS KEYWORD fertig WIRD VERWENDET
$ sort << fertig
$ 3
$ 2
$ 1
$ fertig

1
2
3
```

oder mit einer Text-Datei:

```
$ sort < sortThis.txt

1
2
3
```

