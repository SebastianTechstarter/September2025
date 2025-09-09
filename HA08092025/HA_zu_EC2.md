# Begriffsklärung

1) vertikales vs. horizontales Skalieren:
    vertikal: einem einzelnen Server mehr Leistung zuweisen (CPU, RAM o.ä.)
    horizontal: zusätzliche Instanzen bzw. Server hinzufügen, um die Last auf mehrere Schultern zu verteilen

2) Load Balancer und SPOF:
    Der Load Balancer (LB) verteilt den Datenverkehr auf mehrere Instanzen. Sollte eine davon ausfallen, sorgt der LB dafür, dass die Adresse dennoch erreichbar ist und nicht komplett lahmgelegt wird. 

3) On-Demand vs. Reserved Instances:
    Bei On-Demand ist man sehr flexibel und bezahlt nur bei Bedarf, kann aber auch kurzfristig alles abstoßen.
    Bei Reserved Instances ist man durch die Reservierung zwar längerfristig gebunden, bekommt dadurch aber Preisvorteile.

# Kaufoptionen

## On-Demand
+ Vorteil: Sehr felxibel: jederzeit Start und Stop innerhalb von wenigen Sekunden möglich.
- Nachteil: Wird bei langer und intensiver Nutzung teurer als andere Lösungen.

## Reserved Instances
+ Vorteil: vergleichsweise günstig bei langer Nutzung.
- Nachteil: Wenig Flexibilität, da man langfristig gebunden ist.