---
title: Was ist die Windows Communication Foundation?
description: Erfahren Sie mehr über die Windows Communication Foundation, die ein Framework zum entwickeln Dienst orientierter Anwendungen ist.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], technology overview
- technology overview [WCF]
- WCF [WCF], technology overview
ms.assetid: 40e1009d-ef15-450b-9848-62eabe5e5738
ms.openlocfilehash: 84cb45d62409769a79fa6a401fdb1aa6934c4099
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245608"
---
# <a name="what-is-windows-communication-foundation"></a>Was ist die Windows Communication Foundation?
Windows Communication Foundation (WCF) ist ein Framework zum Aufbauen von Dienst orientierten Anwendungen. Mithilfe von WCF können Sie Daten als asynchrone Nachrichten von einem Dienst Endpunkt an einen anderen senden. Ein Dienstendpunkt kann Teil eines fortwährend verfügbaren von IIS gehosteten Diensts oder ein in einer Anwendung gehosteter Dienst sein. Ein Endpunkt kann ein Client eines Diensts sein, der Daten von einem Dienstendpunkt anfordert. Die Nachrichten können einfach aus einem als XML gesendeten einzelnen Zeichen oder Wort oder aus einem komplexen Strom binärer Daten bestehen. Einige Beispielszenarios enthalten Folgendes:

- Ein sicherer Dienst zur Verarbeitung von Geschäftstransaktionen.

- Ein Dienst, der aktuelle Daten für andere Dienste bereitstellt, z. B. für Netzwerkverkehrberichtsdienste oder andere Überwachungsdienste.

- Ein Chatdienst, mit dem zwei Personen in Echtzeit kommunizieren oder Daten austauschen können.

- Eine Dashboardanwendung, die Daten von einem oder mehreren Diensten abfragt und logisch darstellt.

- Macht einen mit Windows Workflow Foundation implementierten Workflow als WCF-Dienst verfügbar.

- Eine Silverlight-Anwendung zum Abfragen aktueller Datenfeeds von einem Dienst.

Obwohl das Erstellen solcher Anwendungen vor dem vorhanden sein von WCF möglich war, macht WCF die Entwicklung von Endpunkten einfacher als je zuvor. Zusammenfassend ist WCF so konzipiert, dass es einen verwaltbaren Ansatz zum Erstellen von Webdiensten und Webdienst Clients bietet.

## <a name="features-of-wcf"></a>Funktionen von WCF

WCF umfasst die folgenden Features. Weitere Informationen finden Sie unter [Details zur WCF-Funktion](./feature-details/index.md).

- **Dienstausrichtung**

     Eine Folge der Verwendung von WS-Standards besteht darin, dass WCF es Ihnen ermöglicht, *Dienst orientierte* Anwendungen zu erstellen. Dienstorientierte Architektur (SOA) wird von Webdiensten für das Senden und Empfangen von Daten verwendet. Der allgemeine Vorteil der Dienste ist, dass sie untereinander lose verknüpft und nicht hartcodiert sind. Eine lose verknüpfte Beziehung impliziert, dass ein beliebiger Client, der auf einer beliebigen Plattform erstellt wurde, mit einem beliebigen Dienst verbunden werden kann, so lange die wesentlichen Vereinbarungen erfüllt sind.

- **Interoperabilität**

     WCF implementiert moderne Industriestandards für die Interoperabilität von Webdiensten. Weitere Informationen zu den unterstützten Standards finden Sie unter [Interoperabilität und Integration](./feature-details/interoperability-and-integration.md).

- **Mehrere Nachrichtenmuster**

     Nachrichten werden in einem von mehreren Mustern ausgetauscht. Das gängigste Muster ist das Anforderung-Antwort-Muster, bei dem ein Endpunkt Daten von einem zweiten Endpunkt abfragt. Der zweite Endpunkt antwortet. Es gibt noch weitere Muster, wie z. B. eine unidirektionale Nachricht, bei der ein einzelner Endpunkt eine Nachricht ohne Erwartung einer Antwort sendet. Ein komplexeres Muster ist das Duplex-Nachrichtenaustauschmuster, bei dem zwei Endpunkte eine Verbindung herstellen und sich wie bei einem Programm für Sofortnachrichten gegenseitig Daten senden. Weitere Informationen zum Implementieren verschiedener Nachrichtenaustausch Muster mithilfe von WCF finden Sie unter [Verträge](./feature-details/contracts.md).

- **Dienstmetadaten**

     WCF unterstützt das Veröffentlichen von Dienst Metadaten mithilfe von Formaten, die in Industriestandards wie WSDL, XML-Schema und WS-Policy angegeben sind. Diese Metadaten können verwendet werden, um Clients für den Zugriff auf WCF-Dienste automatisch zu generieren und zu konfigurieren. Metadaten können per HTTP und HTTPS oder mit dem Austauschstandard für Webdienstmetadaten veröffentlicht werden. Weitere Informationen finden Sie unter [Metadaten](./feature-details/metadata.md).

- **Datenverträge**

     Da WCF mithilfe der .NET Framework erstellt wird, enthält es auch Code freundliche Methoden für die Bereitstellung der Verträge, die Sie erzwingen möchten. Einer der universalen Vertragstypen ist der Datenvertrag. Beim Codieren des Diensts mit Visual C# oder Visual Basic lassen sich Daten am einfachsten durch das Erstellen von Klassen verwalten, die eine Datenentität mit zur Datenentität gehörenden Eigenschaften darstellen. WCF enthält ein umfassendes System für das einfache arbeiten mit Daten. Nachdem Sie die Klassen erstellt haben, die Daten darstellen, werden vom Dienst automatisch die Metadaten erstellt, mit denen Clients die von Ihnen entworfenen Datentypen verarbeiten können. Weitere Informationen finden Sie unter [Verwenden von Daten Verträgen](feature-details/using-data-contracts.md).

- **Security**

     Nachrichten können zu Datenschutzzwecken verschlüsselt werden, und die Benutzer können zur Authentifizierung aufgefordert werden, bevor Sie Berechtigung zum Empfangen von Nachrichten erhalten. Sicherheit kann mit bekannten Standards wie SSL oder WS-SecureConversation implementiert werden. Weitere Informationen finden Sie unter [Sicherheit](./feature-details/security.md).

- **Mehrfache Transporte und Codierungen**

     Nachrichten können mithilfe der zahlreichen integrierten Transportprotokolle und -codierungen versendet werden. Das häufigste Protokoll und die Codierung sind das Senden von Text codierten SOAP-Nachrichten mithilfe des Hypertext Transfer-Protokolls (http) zur Verwendung auf dem World Wide Web. Alternativ können Sie mithilfe von WCF Nachrichten über TCP, Named Pipes oder MSMQ senden. Diese Nachrichten können als Text oder mit einem optimierten Binärformat codiert werden.  Binärdaten können mit dem MTOM-Standard effizient gesendet werden. Wenn keine der bereitgestellten Transport- oder Codierungsmöglichkeiten Ihren Erfordernissen entspricht, können Sie eine benutzerdefinierte Transport- oder Codierungsmöglichkeit erstellen. Weitere Informationen zu von WCF unterstützten Transporten und Codierungen finden Sie unter [Transporte](./feature-details/transports.md).

- **Zuverlässige Nachrichtensendung und Nachrichten in Warteschlangen**

     WCF unterstützt den zuverlässigen Nachrichtenaustausch mit zuverlässigen Sitzungen, die über zuverlässige WS-Messaging-und MSMQ-Funktionen implementiert werden. Weitere Informationen zur Unterstützung von zuverlässigen und in der Warteschlange befindlichen Messaging in WCF finden Sie unter [Warteschlangen und zuverlässige Sitzungen](./feature-details/queues-and-reliable-sessions.md).

- **Permanente Nachrichten**

     Bei einer permanenten Nachricht handelt es sich um eine Nachricht, die niemals aufgrund einer Unterbrechung der Kommunikation verloren geht. Die Nachrichten in einem Muster für permanente Nachrichten werden immer in einer Datenbank gespeichert. Wird die Verbindung unterbrochen, kann mit der Datenbank der Nachrichtenaustausch nach der erneuten Herstellung der Verbindung fortgesetzt werden. Sie können eine permanente Nachricht auch mit dem Windows Workflow Foundation (WF) erstellen. Weitere Informationen finden Sie unter [Workflow Dienste](./feature-details/workflow-services.md).

- **Transaktionen**

     WCF unterstützt auch Transaktionen, bei denen eines der drei Transaktions Modelle verwendet wird: WS-AtomicTransactions, die APIs im <xref:System.Transactions> -Namespace und Microsoft Distributed Transaction Coordinator. Weitere Informationen zur Transaktionsunterstützung in WCF finden Sie unter [Transaktionen](./feature-details/transactions-in-wcf.md).

- **Unterstützung für AJAX und REST**

     REST ist ein Beispiel für eine sich weiterentwickelnde Web 2.0-Technologie. WCF kann so konfiguriert werden, dass "einfache" XML-Daten verarbeitet werden, die nicht in einem SOAP-Umschlag umschließt werden. WCF kann auch zur Unterstützung spezifischer XML-Formate erweitert werden, wie z. b. Atom (ein beliebter RSS-Standard) und sogar nicht-XML-Formate, wie z. b. JavaScript Object Notation (JSON).

- **Erweiterbarkeit**

     Die WCF-Architektur verfügt über eine Reihe von Erweiterungs Punkten. Wenn zusätzliche Fähigkeiten benötigt werden, können Sie an verschiedenen Punkten ansetzen, um das Verhalten eines Diensts anzupassen. Weitere Informationen zu verfügbaren Erweiterbarkeits Punkten finden Sie unter [Erweitern von WCF](./extending/index.md).

## <a name="wcf-integration-with-other-microsoft-technologies"></a>WCF-Integration mit anderen Microsoft-Technologien

WCF ist eine flexible Plattform. Aufgrund dieser extrem flexiblen Flexibilität wird WCF auch in mehreren anderen Microsoft-Produkten verwendet. Wenn Sie sich mit den Grundlagen von WCF vertraut machen, haben Sie einen unmittelbaren Vorteil, wenn Sie auch eines dieser Produkte verwenden.

Die erste Technologie, die mit WCF gekoppelt werden soll, war der Windows Workflow Foundation (WF). Workflows vereinfachen die Anwendungsentwicklung, indem Schritte im Workflow als "Aktivitäten" gekapselt werden. In der ersten Version von Windows Workflow Foundation musste ein Entwickler einen Host für den Workflow erstellen. Die nächste Version von Windows Workflow Foundation wurde in WCF integriert. Dies ermöglichte, dass jeder Workflow in einem WCF-Dienst problemlos gehostet werden konnte. Wählen Sie hierzu in Visual Studio 2012 oder höher automatisch den WF/WCF-Projekttyp aus.

Microsoft BizTalk Server R2 nutzt WCF auch als Kommunikationstechnologie. BizTalk wurde zum Empfangen und Umwandeln von Daten aus einem Standardformat in ein anderes entwickelt. Nachrichten müssen an den zentralen Posteingang der Anwendung gesendet werden, wo sie entweder per strikter Zuordnung oder mit einer der BizTalk-Funktionen (z.B. Workflow-Engine) umgewandelt werden können. BizTalk kann nun den WCF Line of Business (LOB)-Adapter verwenden, um Nachrichten an das Meldungs Feld zu senden.

Microsoft Silverlight ist eine Plattform für die Entwicklung interoperabler und leistungsfähiger Webanwendungen, mit denen Entwickler multimediale Websites (z. B. mit Videostreams) erstellen können. Ab Version 2 ist in Silverlight WCF als Kommunikationstechnologie integriert, um Silverlight-Anwendungen mit WCF-Endpunkten zu verbinden.

Die Hostingfeatures des Windows Server AppFabric-Anwendungs Servers sind speziell für die Bereitstellung und Verwaltung von Anwendungen konzipiert, die WCF für die Kommunikation verwenden. Zu den Hostingfeatures zählen umfangreiche Tools und Konfigurationsoptionen, die speziell für WCF-fähige Anwendungen entworfen wurden.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel>
- [Wesentliche Windows Communication Foundation-Begriffe](fundamental-concepts.md)
- [Windows Communication Foundation-Architektur](architecture.md)
- [Richtlinien und empfohlene Vorgehensweisen](guidelines-and-best-practices.md)
- [Tutorial zu den ersten Schritten](getting-started-tutorial.md)
- [Anleitung zur Dokumentation](guide-to-the-documentation.md)
- [Einfache WCF-Programmierung](basic-wcf-programming.md)
- [Windows Communication Foundation-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751514%28v=vs.90%29)
