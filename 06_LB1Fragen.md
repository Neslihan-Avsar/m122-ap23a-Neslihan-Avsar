# 06 LB1 Fragen

### a) Was macht die folgende Zeile?

```
     ifconfig | grep "Ether" -c

```

Mit `ifconfig` erhält man Informationen über Netzwerkeigenschaften und man kann auch welche konfigurieren.
Mit dem `|` Symbol wird gleich noch einen Ablauf direkt danach angehängt, bevor die Resultate auf dem System Output präsentiert werden.
Mit `grep` kann man Zeichenketten suchen und filtern (in dem Fall ist es `"Ether"`) und mit dem Flag `-c`werden die Matches gezählt.  

---

### b) Was macht die folgende Zeile?

```
     tar -vczf backup.tar.gz /root/
```

Mit `tar` kann man Dateien zusammen komprimieren, wie ein Archive.
Der Flag `-vczf` ist eine Option, wie man es komprimieren kann.
`backup.tar.gz` ist das Targetfile.
`/root/` ist der Ort.

---

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

Mit `cat` kann man den Inhalt einer Datei im System Output anzeigen.
Mit dem `|` Symbol wird gleich noch einen Ablauf direkt danach angehängt, bevor die Resultate auf dem System Output präsentiert werden.
Mit `sort` wird etwas sortiert und nur einen Eintrag für jedes Wort verwendet mit dem Flag `-u` (also `--unique`).

---

### e) Formulieren sie eine for-schleife, welche durch die Zahlen 1 bis 10 läuft und das Produkt der Zahlen mit sich selbst ausgibt.

---

### f) Wie oft laufen folgende cronjobs?

```
     */10 * * * * <befehl1>
     5 8 * * 0 <befehl2>
     0 10 1 * * <befehl3>
```

---

### g) Was macht folgender Befehl? (Zum Testen IP-Adresse anpassen und fping installieren!)

```
     fping -g -c 1 -t250 172.16.6.0/24 2>&1 | grep " 0% " | cut -d " " -f 1 
```

---

### h) Was macht folgendes Skript?

```
	#!/bin/bash
	for i in $( ifconfig | grep "inet" | grep -v "127.0.0.1" | cut -d ":" -f 2 | cut -d "." -f 1-3 ); do
	  #echo $i #Zum Testen entkommentieren
	  for k in $(seq 1 255); do
	      #echo $k #Zum Testen entkommentieren
	      fping -c 1 -t250 $i.$k 2>&1 | grep " 0% " | cut -d " " -f 1 >> ips.txt
	  done
	done
```

---

### i) Was macht folgender Befehl?

```
     find / -user otto -iname "*bash*" -exec cp {} /data/otto/ \;
```

---

### j) Was machen folgende Befehle?

```
      for ip in $(seq 200 254);do echo 192.168.13.$ip; done > ips.txt
      for ip in $(cat ips.txt);do dig -x $ip | grep $ip >> dns.txt; done
```
