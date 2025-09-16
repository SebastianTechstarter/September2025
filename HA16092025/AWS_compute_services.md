# AWS Compute Services

## Services - wofür genutzt?

### ECR
- Elastic Container Registry
- Private Registry zum Speichern und Verwalten eigener Docker-Images.

### ECS
- Elastic Container Service
- Organisation von Containern auf EC2-Instanzen. Der Server wird vom Nutzer verwaltet

### Fargate
- Fargate ist die Serverless-Variante für Container. Eigene EC2-Instanzen dafür sind nicht nötig.

### Lambda
- Führt Code, Skripte u.ä. ereignisgesteuert aus. Dafür werden keine eigenen dauerhaft laufenden Server benötigt.

### API Gateway
- Stellt HTTP-Endpunkte bereit und verbindet sie z.B. mit Lambda-Funktionen

### Batch
- Führt große, planbare Jobs in Batches aus, besonders bei rechenintensiven Aufgaben.

### Lightsail
- Einfacher Einstieg für kleine Server oder Stacks, schnell eingerichtet, mit reduzierter Oberfläche.

## Leitfragen:

### Was unterscheidet ECS auf EC2 von Fargate - und wann würdest Du welches nutzen?
- ECS aud EC2: der Nutzer betreibt die Server selbst und hat volle Kontrolle über die genutzten Instanzen und mehr Flexibilität bei Hardware und Betriebssystem
- Fargate: Serverless, also muss der Nutzer sich nicht um Server und Infrastruktur kümmern. Dies ist ideal für die Arbeit mit einfachen oder dynamischen Containern.

### Warum ist Lambda + API Gatewayein gutes Muster für schlanke Backends? Nenne einen typischen Usecase.
- eine Liste von Produkten in einem Webshop. Hier werden auf Anfrage Daten aus der Datenbank abgerufen.

### DynamoDB vs. RDS: Wann passt welches Datenmodell im Serverless-Kontext?
- DynamoDB: NoSQL, ideal für stark skalierbare Anwendungen, die schnellen Lese- und Schreibzugriff erfordern.
- RDS: Relationale Datenbank, die für komplexe Abfragen, Joins und Transaktionen geeignet ist.

### Batch vs. Lambda in einem Satz: Wofür ist Batch besser geeignet?
Batch ist besser für lange und rechenintensivere Jobs, die planbar sind und nach Plan genutzt werden. Lambda arbeitet ja eher "spontan" bzw. nach Bedarf.