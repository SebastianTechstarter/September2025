# AWS Cloud Integration & Monitoring

## Leitfragen:

### Wozu Entkopplung? Welche Vorteile bringt eine Queue gegenüber direkter Kopplung?
- Entkopplung reduziert Abhängigkeiten zwischen Diensten und vereinfacht die Skalierung
- Die Queue puffert Nachrichten, sodass sie nacheinander abgearbeitet werden. Das verringert das Verlustrisiko und lässt die Anwendung stabiler laufen.

### SQS vs. SNS: Wann nutze ich welches? Was passiert jeweils mit Nachrichten?
- SQS: wird genutzt, wenn der Empfänger zuverlässig jede Nachricht verarbeiten soll (Message queue)
    - In SQS bleibt die Nachricht in der Queue, bis ein Consumer sie abholt.
- SNS: wird genutzt, um eine Nachricht gleichzeitig an viele Empfänger zu versenden (Broadcast/Pub-Sub)
    - In SNS wir die Nachricht sofort an alle Empfänger verschickt (E-Mail, Lambda etc.)

### Wann Kinesis? Woran erkenne ich, dass ich Streaming statt Queue/Broadcast brauche?
- Kinesis wird genutzt, wenn kontinuierlich große Datenströme in Echtzeit verarbeitet werden müssen (Logs, Klick-streams etc.)
- Streaming braucht man, wenn fortlaufend sehr schnell Daten produziert werden und diese schnell in Echtzeit verarbeitet werden müssen.

### CloudWatch: Was ist eine Metrik, was ein Alarm, woher kommen Logs?
- Eine Metrik ist ein Messwert (z.B. CPU-Auslastung)
- Ein Alarm löst aus, wenn eine Metrik einen zuvor definierten Schwellenwert überschreitet.
- Logs kommen direkt aus Anwendungen oder AWS-Services.

### EventBridge und CloudTrail: Wann nutze ich Zeitplan/Pattern, und wie finde ich in CloudTrail, wer etwas geändert/gelöscht hat?
- Zeitpläne nutzt man für regelmäßige Tasks (z.B. jeden Tag 12 Uhr mittags).
- Event-Patterns werden genutzt, um automatisch auf bestimmt Ereignisse von AWS-Services oder Anwendungen zu reagieren.
- CloudTrail protokolliert alle API-Aufrufe. IM Event-Log sieht man, wer wann was an einer Ressource geändert hat.