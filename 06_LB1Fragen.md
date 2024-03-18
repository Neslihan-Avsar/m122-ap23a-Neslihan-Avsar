# 06 LB1 Fragen

### a) Was macht die folgende Zeile?

```
     ifconfig | grep "Ether" -c

```

Mit `ifconfig` erhält man Informationen über Netzwerkeigenschaften und man kann auch welche konfigurieren.
Mit dem `|` Symbol wird gleich noch einen Ablauf direkt danach angehängt, bevor die Resultate auf dem System Output präsentiert werden.
Mit `grep` kann man Zeichenketten suchen und filtern (in dem Fall ist es `"Ether"`) und mit dem Flag `-c`werden die Matches gezählt.  

### b) Was macht die folgende Zeile?

```
     tar -vczf backup.tar.gz /root/
```

Mit `tar` kann man Dateien zusammen komprimieren, wie ein Archive.
Der Flag `-vczf` ist eine Option, wie man es komprimieren kann.
`backup.tar.gz` ist das Targetfile.
`/root/` ist der Ort.

### c) Füllen sie eine Datei `namen.txt` mit folgendem Inhalt (Inhalt copy-paste)

```
     Otto
     Peter
     Martin
     Christian
     Andrea
     Tim
     Sven
     Heinz
     Bob
```

Dies kann man mit diesem Command machen:
```
     touch namen.txt
     namen.txt << END
```

Damit kann man die Datei `namen.txt` erstellen mittels `touch` und dann in die Datei das schreiben, was man will, bis man
`END` schreibt:

```
     Otto
     Peter
     Martin
     Christian
     Andrea
     Tim
     Sven
     Heinz
     Bob
     END #Hier hört es auf und es wird nicht mit geschrieben
```

### Was macht der folgender Befehl?

```
	cat namen.txt | sort -u
```
