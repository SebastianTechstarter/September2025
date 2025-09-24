# AWS security and compliance

## Leitfragen

### Was schützt AWS und was schützt der Kunde im Shared Responsibility Model konkret?
- AWS: schützt die physischen Komponenten (Hardware, Netzwerke, Virtualisierung, Strom, physische Sicherheit)
- Kunde: schützt 
    - Daten
    - Identitys und Rechte
    - Betriebssysteme und Anwendungen
    - Networkconfig

### Wann reicht Shield Standard und wann braucht man WAF-Regeln (z.B. Rate-Limit/SQLi)?
- Shield Standard:
    - automatisch für alle AWS-Kunden aktiviert
    - schützt vor typischen DDoS-Attacken
- AWS WAF (Web Application Firewall):
    - schützt auf Applikationsebene (Layer 7)
    - Regeln gegen SQL-Injection, XSS, Rate-Limiting, Bot-Traffic
    - sinnvoll für öffentlihe Web-Apps oder APIs

### Wofür nutzt Du KMS vs. ACM vs. SecretsManager - was löst welches Problem?
- KMS (Key Management Service)
    - Verwaltet Keys
    - Nutzt man für Datenverschlüsselung in S3, EBS, RDS usw.
- ACM (AWS Certificate Manager)
    - Verwaltet SSL/TLS-Zertifikate
    - wird für HTTPS genutzt
- Secrets Manager
    - Speichert geheime Informationen (z.B. DB-Passwörter, API-keys)

### Welche Sicherheits-Findings würdest Du zuerst angehen und warum (GuardDUty/INspector)?
- GuardDuty: 
    - überwacht Logs und Netzwerkverkehr
    - macht verdächtige Aktivitäten ausfindig
    - Vorgehensweise: bei Hinweisen auf aktiven Angriff sofort handeln!
- Inspector:
    - scannt EC2, ECR, Lambda
    - findet Schwachstellen und fehlende Patches
    - Vorgehensweise: Fehler zeitnah beheben, da nicht kritisch

### Wie hilft AWS Config/Security Hub beim Nachweis von Compliance?
- Einfacher Nachweis gegenüber Auditoren und Berichterstattung
- AWS Config: 
    - überwacht, ob die Ressourcen regelkonform sind (S3 nicht öffentlich, Verschlüsselung aktiv etc.)
    - liefert eine Historie fürs Audit
- Security Hub:
    - sammelt Findings aus GuardDuty, Inspector, Config
    - gibt einen zentralen Überblick