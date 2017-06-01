---
title: "Empfohlene Vorgehensweisen f&#252;r zuverl&#228;ssige Sitzungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Empfohlene Vorgehensweisen f&#252;r zuverl&#228;ssige Sitzungen
In diesem Abschnitt werden empfohlene Vorgehensweisen für zuverlässige Sitzungen erläutert.  
  
## Festlegen von MaxTransferWindowSize  
 In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwenden zuverlässige Sitzungen ein Übertragungsfenster, um Nachrichten für Client und Dienst zu speichern.  Der konfigurierbare Eigenschaft <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> gibt an, wie viele Nachrichten das Übertragungsfenster speichern kann.  
  
 Für die sendende Seite gibt diese Eigenschaft an, wie viele Nachrichten das Übertragungsfenster während des Wartens auf Bestätigungen speichern kann; für die empfangende Seite gibt diese Eigenschaft an, wie viele Nachrichten des Diensts gepuffert werden.  
  
 Die Auswahl der richtigen Größe legt fest, wie effizient das Netzwerk in Verwendung genommen wird, und mit welcher optimalen Kapazität der Dienst ausgeführt wird.  Die folgenden Abschnitte erläutern im Einzelnen, was bei der Auswahl des Werts dieser Eigenschaft berücksichtigt werden muss, und welche Auswirkungen dieser Wert hat.  
  
 Die Standardgröße des Übertragungsfensters fasst 8&\#160;Nachrichten.  
  
### Effiziente Verwendung des Netzwerks  
 Der Begriff *Netzwerk* umfasst in diesem Zusammenhang alles, was zwischen einem Client \(dem Sender\) und einem Dienst \(dem Empfänger\) zur Aufrechterhaltung der Kommunikation verwendet wird.  Dies schließt die Transportverbindungen und alle dazwischen liegenden Vermittler oder Brücken ein, einschließlich SOAP\-Routern oder HTTP\-Proxys und \-Firewalls.  
  
 Die effiziente Verwendung des Netzwerks stellt sicher, dass die Netzwerkkapazität vollständig ausgeschöpft wird.  Sowohl die Datenmenge, die pro Sekunde über das Netzwerk übertragen werden kann \(also die *Datenrate*\) sowie die Zeit, die benötigt wird, um Daten vom Sender zum Empfänger zu übermitteln \(*Latenz* genannt\) wirken sich darauf aus, wie effizient das Netzwerk verwendet wird.  
  
 Für die sendende Seite gibt die Eigenschaft <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> an, wie viele Nachrichten das Übertragungsfenster während des Wartens auf Bestätigungen speichern kann.  Ist daher die Netzwerklatenz hoch, sollten Sie die Größe des Übertragungsfensters erhöhen, um reaktionsschnelles Senden und effiziente Verwendung das Netzwerks sicherzustellen.  
  
 Auch wenn der Sender beispielsweise mit der Datenrate Schritt hält, könnte die Latenz hoch sein, wenn in einem Netzwerk zahlreiche Vermittler zwischen Sender und Empfänger vorhanden sind, oder wenn es bei einem Vermittler bzw. im Netzwerk zu Datenverlusten kommt.  Daher muss der Sender auf Bestätigungen für die Nachrichten in seinem Übertragungsfenster warten, bevor er weitere Nachrichten senden kann.  Je kleiner der Puffer bei hoher Latenz, desto weniger effizient ist die Netzwerkverwendung.  Andererseits kann sich ein zu großes Übertragungsfenster negativ auf den Dienst auswirken, weil der Dienst mit der hohen Senderate des Clients Schritt halten muss.  
  
### Ausführen des Diensts entsprechend der Kapazität  
 Wird das Netzwerk effizient genutzt, möchten Sie, dass auch der Dienst idealerweise mit optimaler Kapazität ausgeführt wird.  Die Eigenschaft für die Größe des Übertragungsfensters beim Empfänger gibt an, wie viele Nachrichten der Empfänger puffern kann.  Diese Nachrichtenpufferung hilft nicht nur der Flusssteuerung im Netzwerk, sondern erlaubt dem Client auch, mit voller Kapazität zu laufen.  Ist zum Beispiel&\#160;1 als Puffergröße festgelegt, und die Nachrichten treffen schneller ein als sie der Client verarbeiten kann, verwirft das Netzwerk möglicherweise Nachrichten, und Netzwerkkapazität wird verschwendet oder unzureichend ausgenutzt.  
  
 Die Verwendung eines Puffers erhöht die Verfügbarkeit des Diensts, weil er Nachrichten empfangen und puffern kann, während er gleichzeitig vorher empfangene Nachrichten verarbeitet.  
  
 Es wird empfohlen, für den Sender und den Empfänger den gleichen Wert für die `MaxTransferWindowSize`\-Eigenschaft zu verwenden.  
  
### Aktivieren der Flusssteuerung  
 Die Flusssteuerung ist ein Mechanismus, der sicherstellt, dass Sender und Empfänger miteinander Schritt halten, dass also die Nachrichten so schnell verarbeitet und beantwortet werden, wie sie erstellt wurden.  Eine vernünftige Größe des Übertragungsfensters von Client und Dienst stellt sicher, dass Sender und Empfänger ausreichend synchron arbeiten.  
  
 Es wird dringend empfohlen, die Eigenschaft <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> auf true festzulegen, wenn Sie eine zuverlässige Sitzung zwischen einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst verwenden.  
  
## Festlegen von MaxPendingChannels  
 Wenn Sie einen Dienst schreiben, der für die Kommunikation mit verschiedenen Clients zuverlässige Sitzungen verwendet, ist es möglich, dass mehrere Clients gleichzeitig eine zuverlässige Sitzung mit dem Dienst einrichten.  Die Antwort des Diensts hängt in diesen Fällen von der `MaxPendingChannels`\-Eigenschaft ab.  
  
 Wenn der Sender einen zuverlässige Sitzungskanal zum Empfänger erstellt, dann begründet ein Handshake zwischen ihnen eine zuverlässige Sitzung.  Ist die zuverlässige Sitzung eingerichtet, wird der Kanal für seine Annahme durch den Dienst in eine Warteschlange ausstehender Kanäle eingereiht.  Die `MaxPendingChannels`\-Eigenschaft gibt an, wie viele Kanäle in diesem Zustand sein können.  
  
 Es ist möglich, dass sich der Dienst in einem Zustand befindet, in dem er keine weiteren Kanäle annehmen kann.  Ist die Warteschlange voll, wird der Versuch, eine zuverlässige Sitzung einzurichten, zurückgewiesen. Der Client muss dies dann erneut versuchen.  
  
 Es ist auch möglich, dass die sich in der Warteschlange befindenden Kanäle für längere Zeit dort verbleiben.  In der Zwischenzeit könnte bei der zuverlässigen Sitzung ein Inaktivitätstimeout auftreten, wodurch der Kanal in einen Fehlerzustand übergeht.  
  
 Daher sollten Sie, wenn Sie einen Dienst schreiben, der mehrere Clients gleichzeitig bedient, einen Wert wählen, der Ihren Anforderungen entspricht.  Ein zu hoher Wert der `MaxPendingChannels`\-Eigenschaft behindert Ihr Workingset.  
  
 Der Standardwert von <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> ist 4.  
  
## Zuverlässige Sitzungen und Hosting  
 Wenn Sie Webhosting für einen Dienst mit zuverlässigen Sitzungen verwenden, sollten Sie sich immer an die folgenden wichtigen Überlegungen halten:  
  
-   Zuverlässige Sitzungen sind zustandsbehaftet, und der Zustand wird in der AppDomain beibehalten.  Dies bedeutet, dass alle Nachrichten, die Teil einer zuverlässigen Sitzung sind, in der gleichen AppDomain verarbeitet werden müssen.  Für Webfarmen und Webgärten, bei denen die Größe der Farm oder des Gartens \> 1 ist, kann die Einhaltung dieser Beschränkung nicht garantiert werden.  
  
-   Bei zuverlässigen Sitzungen, die duale HTTP\-Kanäle \(beispielsweise `WsDualHttpBinding`\) verwenden, können mehr HTTP\-Verbindungen als der Standardwert 2 pro Client erforderlich sein.  Das bedeutet, dass eine zuverlässige Duplexsitzung bis zu zwei Verbindungen in jede Richtung erfordern kann, weil gleichzeitig ausgeführte Anwendungen und Protokollnachrichten über jeden Weg und zu jeder Zeit Übertragungen vornehmen.  Dies bedeutet, dass unter gewissen Bedingungen, die vom Nachrichtenaustauschmuster des Diensts abhängen, ein Deadlock bei einem im Internet gehosteten Dienst auftritt, der duale HTTP\-Verbindungen und zuverlässige Sitzungen verwendet.  Fügen Sie, um die Zahl der zulässigen HTTP\-Verbindungen pro Client zu erhöhen, Folgendes in die entsprechende Konfigurationsdatei ein \(beispielsweise in die Datei web.config des jeweiligen Diensts\):  
  
```  
<configuration>  
   <system.net>  
      <connectionManagement>  
         <add name = "*" maxconnection = "XX" />  
      </connectionManagement>  
   </system.net>  
</configuration>  
```  
  
 "XX" steht für die Anzahl der benötigten Verbindungen.  In diesem Fall sollte das Minimum&\#160;4 sein.