# Hausaufgabe

## Was ist der Unterschied zwischen EBS und Instance Store?
- EBS ist ein Blockspeicher, der lange erhalten bleibt und unabhängig von Instanzen existiert.
- Instance Store ist sehr schnell. Die Daten gehen allerdings verloren, wenn die Instanz gestoppt oder neugestartet wird. (Ähnlich wie beim RAM)

## Wann würdest Du ein AMI einsetzen und welchen Vorteil bietet es?
- Das AMI ist ein Image einer Instanz und kann gut verwendet werden, um nach Vorlage eine Instanz zu starten.
- Vorteil: Einfache Reproduktion und Zeitersparnis

## In welchen Szenarien würdest Du EFS nutzen?
- Sinnvoll bei Szenarien, in denen mehrere Maschinen auf einen gemeinsamen Speicher zugreifen müssen (Webserver, Datenbank, etc.)

## Wofür eignet sich FSx for Windows und wofür FSx for Lustre?
- FSx for Windows eignet sich für windowsbasierte Anwendungen, sodass Windows-Clients und Windows-Server nahtlos auf AWS-Instanzen zugreifen können
- FSx for Lustre eignet sich für hochpperformante Anwendungen mit großen Datenmengen (bspw. Video-Rendering oder KI-Training)

## Was passiert, wenn man in einer Auto-Scaling-Group alle Instanzen löscht?
- Die ASG erstellt automatisch neue Instanzen, um die gewünschte Kapazität wieder bereitzustellen.

## Was ist der Vorteil einer dynamischen Skalierung im Vergleich zu einer geplanten Skalierung?
- dynamische Skalierung reagiert felxibel auf Laständerungen, indem es automatisch nachskaliert.
- geplante Skalierung skaliert nur zu festgelegten Zeiten hoch oder runter.