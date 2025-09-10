# Hausaufgabe zu IAM und CLI

### Unterschied zwischen IAM-User und IAM-Rolle
- Ein IAM-User ist ein fest angelegter Benutzer, der eigene Zugangsdaten hat.
- eine IAM-Rolle ist eine Rolle, die temporär angenommen wird, um bestimmte Aufgaben zu erledigen.

### Warum ist das "Least-Privilege-Prinzip" wichtig?
- Ein User soll nur die Berechtigungen bekommen, die er benötigt. 
    - So viel wie nötig - so wenig wie möglich.
- Das verringert die Gefahr von Missbrauch und / oder Fehlern.

### Was ist eine Passwort-Policy und wofür wird sie genutzt?
- Die Passwort-Policy legt die Regeln fest, wie Passwörter aufgebaut sein sollen, bspw.:
    - Mindestanzahl an Zeichen
    - Sonderzeichen / Zahlen
    - Haltbarkeit / Ablaufzeit
- Dies erhöht die Sicherheit, indem User nicht zu einfache Passwörter verwenden.

### Unterschied zwischen Zugriff über Management-Konsole, CLI und SDK
- Management-Konsole: grafische Weboberfläche ("Klicki-bunti")
- CLI: Befehlszeile im Terminal. Ideal für Skripte und Automatisierung
- SDK: Programmierschnittstelle, um Dienste direkt aus Anwendungen heraus zu bedienen

### Best Practices für IAM
- Root-Account schützen: nur für Verwaltung und Konfiguration nutzen - nicht für tägliche Aufgaben
- Regelmäßige Überprüfung: Berrechtigungen regelmäßig prüfen und ungenutzte User, Rollen oder Berechtigungen entfernen.