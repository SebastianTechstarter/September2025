# globale Infrastruktur

## Leitfragen:

### Warum senkt die Nähe einer Region oder Edge-Location die Latenz?
- durch die räumliche Nähe müssen die Daten nicht über weite Distanzen durch das öffentliche Internet gescickt werden.
- Dadurch sinken die Verzögerungen bei der Datenverarbeitung.

### Was unterscheidet CloudFront von S3 Transfer Acceleration?
- Cloud Front verteilt Inhalte wie Webseiten, Videos oder Dateien an viele Nutzer über ein weltweites CDN (Content Delivery Network).
- S3 Transfer Acceleration beschleunigt ausschließlich den Datentransfer zwischen Clients und einem bestimmten S3-Bucket, indem der schnellste Weg über Edge-Locations genommen wird.

### In welchem Fall würdest Du Weighted Routing in Route 53 einsetzen, und wann Latency Routing?
- Weighted Routing eignet sich, wenn der Traffic auf unterschiedliche Ziele verteilt werden soll, bspw. für Tests etc.
- Latency Routing wird genutzt, wenn die User automatisch zum Server mit der geringsten Latenz weitergeleitet werden sollen.

### Was ist der Vorteil des AWS Global Accelerator im Vergleich zum normalen Internet-Routing?
- Global Accelerator nutzt das AWS-Netzwerk, das stabiler und schneller als das öffentliche Internet ist.

### Nenne ein Beispiel, wann ein Unternehmen Outposts einsetzen würde.
- Wenn ein Unternehmen sich keine hohe Latenz leisten kann und jede Sekunde zählt.
- Beispiele: Finanzsektor, Medizin

### Warum ist Wavelength besonders für 5G-Anwendungen relevant?
- Wavelength stellt AWS-Services direkt im Netz des Mobilfunkanbieters bereit und ermöglicht so eine niedrige Latenz.

### Welchen Nutzen haben Local Zones für Nutzer in bestimmten Städten?
- Local Zones bringen zusätzliche Rechenkapazität gerade in dicht besiedelten Gebieten, in denen ein hohes Datenaufkommen zu erwarten ist.
- Dadurch lassen sich bspw. Echtzeitdienste flüssiger bereitstellen.