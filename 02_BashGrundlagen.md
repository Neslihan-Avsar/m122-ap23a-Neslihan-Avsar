# 02 - Bash Grundlagen

### Kürzel

- ```~``` ist ein Kürzel fürs Heimatverzeichnis des aktuellen Benutzers.  
- ```/``` ist auch als ```root``` bekannt. Dies ist das Oberste der Hierarchie.  
- Ein ```;``` trennt Befehle innerhalb einer Zeile.  
- Das ```|``` verkettet einzelne Befehle miteinander in einer Zeile.  
- ```#``` wird verwendet um die Zeile zu einem Kommentar um zu wandeln.  
- ```\``` wird verwendet um ein Befehl auf der nächsten Zeile weiterschreiben zu können trotz eines ```newline```-Symbol. - Es wird auch als das ```ESC```-Symbol verwendet.  
- Mit einem ```&``` am Ende des Befehls wird das Befehl im Hintergrund ausgeführt.
- ```*``` wird als Platzhalter (also Wildcard) verwendet für beliebige Zeichen.  
- ```?``` wird als Platzhalter (also Wildcard) verwendet für ein beliebiges Zeichen.  
- ```{}``` wird für Bereiche oder Ausdrücke verwendet.  

### Befehle

- ```reboot``` / ```shutdown -r``` / ```init 6``` startet das System neu.  
- ```halt``` / ```shutdown -h``` / ```poweroff``` schaltet das System ab.  
- ```apropos <keyword>``` durchsucht alle Hildeseiten nach dem ```<keyword>```.  
- ```which <program>``` sucht nach dem Ort des installierten Programmes ```<program>```.  
- ```find <location> -type``` sucht nach Dateien innerhalb eines Verzeichnisses inkl. Unterverzeichnis.
- ```pwd``` zeigt das aktuelle Verzeichnis an.  
- ```cd <location>``` ändert das aktuelle Verzeichnis zu ```<location>```.  
- ```ls <location>``` listet den Verzeichnisinhalt auf im Ort ```<location>```.  
- ```mkdir <location>``` erstellt einen Ordner in dem Zielort ```<location>```.  
- ```rmdir <location>``` entfernt den Ordner vom Zielort ```<location>```.  
- ```cp <file> <newFile>``` oder ```cp <location> <newLocation>``` kopiert Dateien und Verzeichnisse.  
- ```rm <file>``` oder ```rm -r <location>``` löscht Dateien und Verzeichnisse. Ja, auch ```root``` kann gelöscht werden, also bitte Vorsicht!
- ```mv <file> <newFile>``` oder ```mv <location> <newLocation>``` verschiebt Dateien und Verzeichnisse.
- ```touch <location>``` erstellt eine neue Datei in ```location```.
- ```cat <location>``` gibt den Inhalt der Datei aus.
- ```echo <string>``` gibt die Zeichenkette ```<string>``` aus.
- ```wc -w <location>``` oder ```wc -l <location>``` gibt die Anzahl Wörter oder Linien des Inhaltes einer Datei aus.
- ```alias <aliasname>="<command>"``` gibt dir die Möglichkeit, den Befehl ```<command>``` mit einem Alias wie
- ```<aliasname>``` auszuführen, um Zeit zu sparen oder es sich leichter merken zu können.
