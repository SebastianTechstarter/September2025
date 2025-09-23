# AWS VPC und Networking

## Leitfragen

### Was ist eine VPC? Erkläre Zweck und Abgrenzung in 2-3 Sätzen.
- VPC = Virtual Private Cloud
- Eine VPC ist ein isoliertes virtuelles Netzwerk in AWS, in dem Instanzen betrieben werden.
- Dieses Netzwerk ist vom Netzwerk anderer Kunden abgegrenzt und und erlaubt eigenes Routing und IP-Adressen.

### Public vs. Private Subnet: Woran erkennst du sie? Welche Route fehlt im Private Subnet?
- Public Subnet: hat eine Route zum Internet-Gateway.
- Private Subnet: hat keine direkte Route. Es kann nur über NAT-Gateway ins Internet.

### Internet Gateway vs. NAT Gateway: Welche Richtung des Traffics ermöglicht welches Gateway? Nenne ein Beispiel.
- Internet Gateway ermöglicht eingehenden und ausgehenden Datenverkehr vom Internet.
- NAT Gateway ermöglicht ausgehenden Internetverkehr für Private Subnets, aber keine eingehenden Verbindungen.

### Route Tables: Wie steuern sie den Zugriff ins Internet und zwischen Subnetzen?
- Route Tables bestimmen wohin Traffic aus einem Subnetz geht.
    - Route zum Internet Gateway = Internetzugriff (Public Subnet)
    - Route zum NAT-Gateway = private Subnets können raus.
    - Interne Routen = Kommunikation zwischen einzelnen Subnets

### Security Group vs. NACL: Stateful vs. stateless, ALLOW/DENY - wo setzt Du was ein? Gib ein typisches Regelbeispiel.
- Security Groups: stateful, nur ALLOW, gelten pro Instanz
    - SG erlaubt Port 22 (SSH) von Büro IP
- NACLs: Stateless, ALLOW und DENY, gelten für Subnetze
    - NACL blockiert gesamten eingehenden Traffic aus einem verdächtigen IP-Block

### IPv4/IPv6 in AWS: Was bleibt gleich nach dem Stop/Start? Wofür nutzt Du Elastic IPs? (Stichwort: feste öffentliche IPv4)
- Private IPv4: bleibt gleich, auch nach STOP/START
- Public IPv4: ändert sich nach STOP/START
- Elastic IP: feste öffentliche IPv4, z.B. für Web-API

### VPC Endpoints: Gateway vs. Interface - nenne je ein passendes Einsatzszenario.
- Gateway Endpoint: Für S3/DynamoDB, weil direkter kostenloser Zugriff ohne NAT/Internet Gateway
- Interface Endpoint: ENI in Subnet, für Services wie SSM oder Secrets Manager

### VPC-Peering-Regeln: Warum sind überlappende CIDRs ein Problem? Was bedeutet "nicht transitiv" in der Praxis?
- Wenn CIDRs sich überlappen, dann sind Routen nicht eindeutig
- Nicht transitiv bedeutet, dass A und C nicht zwingend miteinander kommunizieren können, nur weil A mit B und B mit C spricht.

### VPC Flow Logs: Wohin kann man sie schreiben und wofür nutzt du sie in der Praxis?
- Schreiben kann man sie in S3, CloudWatch Logs, Kinesis Firehose
- Praxisanwendung: Analyse von Verbindungsfehlern, Security Monitoring

### Site-to-Site VPN vs. Direct Connect: Unterschiede, Vor- und Nachteile und ein Usecase je Technologie.
- S2S- VPN: Tunnel über das Inernet, schnell und günstig einzurichten, höhere Latenz.
    - Backup oder Testverbindung ins On-Premise-Netz
- Direct-Connect: dedizierte Leitung, geringere Latenz, aber teurer.
    - produktive ERP-Systeme mit konstantem Datenaustausch

### Client VPN: In welchem Szenario ist es sinnvoller als ein klassisches S2S-VPN?
- Client VPN ist sinnvoll für Remote-User aus dem Homeoffice oder von unterwegs.
- S2S verbindet ganze Standorte miteinander und das ist wenig sinnvoll in dem Kontext.

### Transit Gateway: Warum erleichtert es komplexe Topologien gegenüber vielen Peering-Verbindungen?
- Vereinfacht große Umgebungen, da es als zentraler Hub funktioniert. 
- Statt vieler Peering-Verbindungen reicht eine Verbindung pro VPC zum Transit Gateway.

### Troubleshooting-Fall: Eine Instanz im Private Subnet kommt nicht ins Internet - welche 3 Checks machst Du der Reihe nach?
1) Route 0.0.0.0/0 zeigt korrekt auf ein NAT-Gateway?
2) NAT Gateway existiert im Public Subnet mit Internet-Gateway-Anbindung?
3) Security Group/NACL erlauben ausgehen Traffic?