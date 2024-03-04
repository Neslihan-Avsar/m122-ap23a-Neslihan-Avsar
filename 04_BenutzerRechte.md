# 04 - Benutzerverwaltung und Rechte

### Benutzer erstellen, löschen und verändern

- `useradd <user>` fügt einen User namens `<user>` hinzu
- `userdel <user>` löscht den User `<user>`
- `passwd <user>` ändert den Passwort des Users `<user>`
- `logout` oder `exit` loggt den aktuellen Benutzer aus dem System
- `who` zeigt alle angemeldeten Benutzer an
- `whoami` zeigt den aktuellen Benutzernamen an
- `groups` zeigt die Gruppen des aktuellen Benutzernamen an
- `id` zeigt die Nutzerid und Gruppen des aktuellen Benutzers an
- `su - <user>` wechselt den Sitz von dem aktuellen User zum anderen User `<user>` hinüber

### Rechte verwalten

- `chown <user> <datei>` wechselt den Besitz der Datei oder des Verzeichnisses zu einem anderen User
- `chmod <parameter> <datei>` wechselt die Zugriffsrechte einer Datei oder eines Verzichnisses

mit `r`, `w` und `x` werden jeweils die Parameter für `read`, `write` und `execute` bei einem Benutzer, bei einer Gruppe oder
von anderen (der Rest) gewechselt. Dabei gilt folgendes zu beachten:

```
r = 4
w = 2
x = 1
```

Wenn jemand also die Rechte zu einer Datei als `7` hat,
kann er die Datei lesen, bearbeiten und ausführen, da `7 = 4 + 2 + 1` ist.  
Für den Command muss man es zum Teil als `root` ausführen.
