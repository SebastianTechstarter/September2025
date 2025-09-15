# Datenbanken und Analytics

### OLTP vs. OLAP: Wann passt RDS / Aurora (Transaktionen) und wann Redshift (Analysen)?
- RDS / Aurora eignet sich für viele kleinere Transaktionen, z.B. Bankbuchungen oder E-Commerce
- Redshift eignet sich für die Analyse großer Datenpakete, z.B. historische Auswertungen und Journale.

### Multi-AZ vs. Read Replica: Worin liegt der Unterschied - und in welcher Situation wählst Du welche Option?
- Multi-AZ sorgt für hohe Verfügbarkeit und Ausfallsicherheit durch Replikation in eine andere Availability-Zone
- Read-Replica erstellt Kopien zur Entlastung des Primary. Hält ein Backup auf Standby bereit, das bei Ausfall des Primarys dessen Aufgaben übernimmt.

### Athena vs. Redshift: Wann reicht SQL auf S3 (Athena) und wann brauchst Du ein Data Warehouse (Redshift)?
- Athena bietet die Möglichkeit direkt mit SQl auf die Daten in S3 zuzugreifen. Athena ist "serverless", d.h. der Nutzer muss keinen Server einrichten. Es wird nur für die abgefragte und durchsuchte Datenmenge gezahlt. Dies kann sinnvoll bei einmaligen Auswertungen von Logdateien o. ä. sein
- Redshift dagegen ist ein Data Warehouse, also ein System, das Daten aus vielen Quellen sammelt, speichert und analysiert. Redshift lohnt sich, wenn regelmäßig große Datenmengen ausgewertet werden müssen. Dieser Service kostet aber mehr, da eine dauerhaft laufende INfrastruktur benötigt wird.

### Shared Responsibility (DB): Nenne je zwei Aufgaben von AWS und Dir (z.B. Betrieb / Backups vs. Datenmodell / Zugriffsrechte).
- AWS: 
    - sorgt für Infrastruktur
    - sorgt für automatische Backups
- Nutzer:
    - verantwortlich für Nutzer- und Zugriffsrechte
    - Daten bzw. Datenqualität

### Glue: Welche Probleme löst AWS Glue im Analytics-Umfeld?
- AWS Glue wird für ETL (Extrahieren, Transformieren und Laden) von Daten genutzt. Diese werden automatisch erkannt, katalogisiert und für Analysen vorbereitet.

### ElastiCache vs. DAX: Worin unterscheiden sich ElastiCache und DAX - wann nimmst Du was?
- ElastiCache wird genutzt, um häufig abgerufene Daten flexibel zu cachen, sodass die Datenbank entlastet werden kann.
- DAX (DynamoDB Accelerator) ist ein spezieller Cache explizit für DynamoDB, um die Datenübertragung zu erhöhen bzw. Latenzen zu verringern.