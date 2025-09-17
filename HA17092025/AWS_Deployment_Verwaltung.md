# AWS Deployment und Verwaltung

## Leitfragen

### CDK: In welchen Fällen bringt CDK echte Vorteile gegenüber reinem YAML? Nenne ein Beispiel für ein wiederverwendbares Konstrukt.
- CDK steht für "Cloud Deployment Kit"
- Bringt Vorteile gegenüber Yaml, wenn man eine komplexe Infrastruktur hat, die wiederkehrend ist. Durch die angewandte Programmiersprache kann man Schliefen einbauen, sodass bspw. mehrere unterschiedliche Buckets gleichzeitig aufgebaut werden. In Yaml müsste man für jeden Bucket ein eigenes Skript schreiben. bei CDK reicht eins.

### Beanstalk: Welche Teile der Infrastruktur übernimmt Beanstalk automatisch und was musst Du weiterhin im Blick behalten?
- Beanstalk übernimmt: Provisionierung von EC2, Security Groups, Load Balancer, Scaling,, Health-Checks, IP-Zuweisung
- Nutzer übernimmt: Anwendungscode, Abhängigkeiten, Kosten, Logging, Monitoring

### Code-Services: Wer macht Build, wer Orchestrierung, wer Deploy? Wie passt CodeArtifact dazu?
- Code Build: Führt Builds und Tests aus.
- Code Pipeline: Steuert den Ablauf von Build --> Test --> Deploy
- Code Deploy: spielt die Anwendung auf Zielumgebunen auf
- Code Artifact: dient als internes Paket-Repo für Builds und Deployments

### SSM: Wann Parameter-Store, wann Session-Manager? Nenne je einen konkreten Einsatzfall.
- Parameter-Store: zum Speichern eines DB-Passworts oder API-keys, die von Anwendungen abgerufen werden.
- Session Manager: eine Shell auf der EC2-Instanz öffnen, ohne SSH-Keys und Port 22 öffnen zu müssen.