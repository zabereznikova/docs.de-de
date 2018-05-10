---
title: Was ist die Windows Communication Foundation?
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], technology overview
- technology overview [WCF]
- WCF [WCF], technology overview
ms.assetid: 40e1009d-ef15-450b-9848-62eabe5e5738
ms.openlocfilehash: e49b393b9dd09a513066a6cb3612ad9f938e9adb
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="what-is-windows-communication-foundation"></a>Was ist die Windows Communication Foundation?
Windows Communication Foundation (WCF) ist ein Framework zum Erstellen von dienstorientierten Anwendungen. Mit WCF können Sie Daten als asynchrone Nachrichten von einem Dienstendpunkt zu einem anderen senden. Ein Dienstendpunkt kann Teil eines fortwährend verfügbaren von IIS gehosteten Diensts oder ein in einer Anwendung gehosteter Dienst sein. Ein Endpunkt kann ein Client eines Diensts sein, der Daten von einem Dienstendpunkt anfordert. Die Nachrichten können einfach aus einem als XML gesendeten einzelnen Zeichen oder Wort oder aus einem komplexen Strom binärer Daten bestehen. Einige Beispielszenarios enthalten Folgendes:  
  
-   Ein sicherer Dienst zur Verarbeitung von Geschäftstransaktionen.  
  
-   Ein Dienst, der aktuelle Daten für andere Dienste bereitstellt, z. B. für Netzwerkverkehrberichtsdienste oder andere Überwachungsdienste.  
  
-   Ein Chatdienst, mit dem zwei Personen in Echtzeit kommunizieren oder Daten austauschen können.  
  
-   Eine Dashboardanwendung, die Daten von einem oder mehreren Diensten abfragt und logisch darstellt.  
  
-   Macht einen mit Windows Workflow Foundation implementierten Workflow als WCF-Dienst verfügbar.  
  
-   Eine Silverlight-Anwendung zum Abfragen aktueller Datenfeeds von einem Dienst.  
  
 Beim Erstellen solcher Anwendungen möglich ist, bevor das Vorhandensein von WCF wurde, wird von WCF in die Entwicklung von Endpunkten einfacher als je zuvor. Zusammenfassend WCF entwickelt, um einen leichten von Webdiensten und Webdienstclients zu ermöglichen.  
  
## <a name="features-of-wcf"></a>Funktionen von WCF  
 WCF bietet die folgende Gruppe von Funktionen. Weitere Informationen finden Sie unter [Details zur WCF-Funktion](../../../docs/framework/wcf/feature-details/index.md).  
  
-   **Dienstausrichtung**  
  
     Ein Vorteil der Verwendung des WS-Standards ist, dass WCF Ihnen die ermöglicht Erstellung *dienstorientierten* Anwendungen. Dienstorientierte Architektur (SOA) wird von Webdiensten für das Senden und Empfangen von Daten verwendet. Der allgemeine Vorteil der Dienste ist, dass sie untereinander lose verknüpft und nicht hartcodiert sind. Eine lose verknüpfte Beziehung impliziert, dass ein beliebiger Client, der auf einer beliebigen Plattform erstellt wurde, mit einem beliebigen Dienst verbunden werden kann, so lange die wesentlichen Vereinbarungen erfüllt sind.  
  
-   **Interoperabilität**  
  
     WCF implementiert aktuelle Industriestandards für die Webdienstinteroperabilität. Weitere Informationen zu den unterstützten Standards finden Sie unter [Interoperabilität und Integration](../../../docs/framework/wcf/feature-details/interoperability-and-integration.md).  
  
-   **Mehrere Nachrichtenmuster**  
  
     Nachrichten werden in einem von mehreren Mustern ausgetauscht. Das gängigste Muster ist das Anforderung-Antwort-Muster, bei dem ein Endpunkt Daten von einem zweiten Endpunkt abfragt. Der zweite Endpunkt antwortet. Es gibt noch weitere Muster, wie z. B. eine unidirektionale Nachricht, bei der ein einzelner Endpunkt eine Nachricht ohne Erwartung einer Antwort sendet. Ein komplexeres Muster ist das Duplex-Nachrichtenaustauschmuster, bei dem zwei Endpunkte eine Verbindung herstellen und sich wie bei einem Programm für Sofortnachrichten gegenseitig Daten senden. Weitere Informationen zum Implementieren verschiedener Muster, die mithilfe von WCF finden Sie unter [Verträge](../../../docs/framework/wcf/feature-details/contracts.md).  
  
-   **Dienstmetadaten**  
  
     WCF unterstützt die publishing Metadaten in den Formaten der Branchenstandards, z. B. WSDL, XML-Schema und WS-Richtlinie. Diese Metadaten kann verwendet werden, automatisch generieren und Konfigurieren von Clients für den Zugriff auf WCF-Dienste. Metadaten können per HTTP und HTTPS oder mit dem Austauschstandard für Webdienstmetadaten veröffentlicht werden. Weitere Informationen finden Sie unter [Metadaten](../../../docs/framework/wcf/feature-details/metadata.md).  
  
-   **Datenverträge**  
  
     Da WCF integriert ist mit der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], enthält er auch Code-codefreundliche Methoden für die Verträge, die Sie durchsetzen möchten. Einer der universalen Vertragstypen ist der Datenvertrag. Beim Codieren des Diensts mit Visual C# oder Visual Basic lassen sich Daten am einfachsten durch das Erstellen von Klassen verwalten, die eine Datenentität mit zur Datenentität gehörenden Eigenschaften darstellen. WCF bietet ein umfassendes System für die Arbeit mit Daten in diese einfache Weise. Nachdem Sie die Klassen erstellt haben, die Daten darstellen, werden vom Dienst automatisch die Metadaten erstellt, mit denen Clients die von Ihnen entworfenen Datentypen verarbeiten können. Weitere Informationen finden Sie unter [mithilfe von Datenverträgen](../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
  
-   **Sicherheit**  
  
     Nachrichten können zu Datenschutzzwecken verschlüsselt werden, und die Benutzer können zur Authentifizierung aufgefordert werden, bevor Sie Berechtigung zum Empfangen von Nachrichten erhalten. Sicherheit kann mit bekannten Standards wie SSL oder WS-SecureConversation implementiert werden. Weitere Informationen finden Sie unter [Sicherheit (WPF)](../../../docs/framework/wcf/feature-details/security.md).  
  
-   **Mehrfache Transporte und Codierungen**  
  
     Nachrichten können mithilfe der zahlreichen integrierten Transportprotokolle und -codierungen versendet werden. Die gängigste Protokoll- und Codierungsmethode Text codiert SOAP-Nachrichten über das HyperText Transfer-Protokoll (HTTP) für die Verwendung im World Wide Web gesendet wird. Alternativ können Sie zum Senden von Nachrichten über TCP, mit dem Namen WCF Pipes oder MSMQ. Diese Nachrichten können als Text oder mit einem optimierten Binärformat codiert werden.  Binärdaten können mit dem MTOM-Standard effizient gesendet werden. Wenn keine der bereitgestellten Transport- oder Codierungsmöglichkeiten Ihren Erfordernissen entspricht, können Sie eine benutzerdefinierte Transport- oder Codierungsmöglichkeit erstellen. Weitere Informationen zu von WCF unterstützten Transporten und Codierungen finden Sie unter [Transporte](../../../docs/framework/wcf/feature-details/transports.md).  
  
-   **Zuverlässige Nachrichtensendung und Nachrichten in Warteschlangen**  
  
     WCF unterstützt zuverlässigen Nachrichtenaustausch mit zuverlässigen Sitzungen über WS-Reliable Messaging implementiert und mithilfe von MSMQ. Weitere Informationen zu Unterstützung Nachrichten zuverlässig und in der Warteschlange in WCF finden Sie unter [Warteschlangen und zuverlässige Sitzungen](../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).  
  
-   **Permanente Nachrichten**  
  
     Bei einer permanenten Nachricht handelt es sich um eine Nachricht, die niemals aufgrund einer Unterbrechung der Kommunikation verloren geht. Die Nachrichten in einem Muster für permanente Nachrichten werden immer in einer Datenbank gespeichert. Wird die Verbindung unterbrochen, kann mit der Datenbank der Nachrichtenaustausch nach der erneuten Herstellung der Verbindung fortgesetzt werden. Sie können auch eine permanente Meldung mithilfe der Windows Workflow Foundation (WF) erstellen. Weitere Informationen finden Sie unter [Workflowdienste](../../../docs/framework/wcf/feature-details/workflow-services.md).  
  
-   **Transaktionen**  
  
     WCF unterstützt auch Transaktionen, bei denen eines der drei Transaktionsmodelle verwendet wird: WS-AtomicTtransactions, die APIs im <xref:System.Transactions> -Namespace und Microsoft Distributed Transaction Coordinator. Weitere Informationen zur Transaktion-Unterstützung in WCF finden Sie unter [Transaktionen](../../../docs/framework/wcf/feature-details/transactions-in-wcf.md).  
  
-   **Unterstützung für AJAX und REST**  
  
     REST ist ein Beispiel für eine sich weiterentwickelnde Web 2.0-Technologie. WCF kann konfiguriert werden, um "rein" XML-Daten zu verarbeiten, die nicht in einen SOAP-Umschlag umgeben sind. WCF kann auch erweitert werden, um bestimmte XML-Formaten, z. B. ATOM (ein verbreiteter RSS-standard) und auch nicht-XML-Formaten, z. B. JavaScript Object Notation (JSON) zu unterstützen.  
  
-   **Erweiterungen**  
  
     Die WCF-Architektur besteht aus einer Reihe von Erweiterungspunkten. Wenn zusätzliche Fähigkeiten benötigt werden, können Sie an verschiedenen Punkten ansetzen, um das Verhalten eines Diensts anzupassen. Weitere Informationen zu verfügbaren Erweiterungen Punkte finden Sie unter [Erweitern von WCF](../../../docs/framework/wcf/extending/index.md).  
  
## <a name="wcf-integration-with-other-microsoft-technologies"></a>WCF-Integration mit anderen Microsoft-Technologien  
 WCF ist eine flexible Plattform. Aufgrund der hohen Flexibilität wird WCF auch in zahlreichen anderen Produkten von Microsoft verwendet. Durch die Grundlagen von WCF, müssen Sie einen unmittelbaren Vorteil, wenn Sie auch eines dieser Produkte verwenden.  
  
 Die erste Technologie, mit WCF war Windows Workflow Foundation (WF). Workflows vereinfachen die Anwendungsentwicklung durch die kapselnden Schritte im Workflow als "Aktivitäten". In der ersten Version von Windows Workflow Foundation musste ein Entwickler einen Host für den Workflow zu erstellen. Die nächste Version von Windows Workflow Foundation wurde in WCF integriert. Beliebiger Workflow kann problemlos in einem WCF-Dienst gehostet werden darf; dazu können Sie seither WF/WCF einen Projekttyp in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
 Microsoft BizTalk Server R2 nutzt u. a. auch WCF als kommunikationstechnologie. BizTalk wurde zum Empfangen und Umwandeln von Daten aus einem Standardformat in ein anderes entwickelt. Nachrichten müssen an den zentralen Posteingang der Anwendung gesendet werden, wo sie entweder per strikter Zuordnung oder mit einer der BizTalk-Funktionen (z.B. Workflow-Engine) umgewandelt werden können. BizTalk kann jetzt die WCF Line of Business (LOB)-Adapter verwenden, Nachrichten an die MessageBox übermittelt.  
  
 Microsoft Silverlight ist eine Plattform für die Entwicklung interoperabler und leistungsfähiger Webanwendungen, mit denen Entwickler multimediale Websites (z. B. mit Videostreams) erstellen können. Seit Version 2, hat Silverlight als kommunikationstechnologie so Silverlight-Anwendungen WCF-Endpunkten mit WCF integriert.  
  
 Die [!INCLUDE[dublin](../../../includes/dublin-md.md)] -Anwendungsserver wurde speziell für die Bereitstellung und Verwaltung von Anwendungen, die WCF für die Kommunikation verwendet entwickelt. Die [!INCLUDE[dublin2](../../../includes/dublin2-md.md)] enthält umfangreiche bearbeitungs- und Konfigurationsoptionen, die speziell für die WCF-fähigen Anwendungen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel>  
 [Wesentliche Windows Communication Foundation-Begriffe](../../../docs/framework/wcf/fundamental-concepts.md)  
 [Windows Communication Foundation-Architektur](../../../docs/framework/wcf/architecture.md)  
 [Richtlinien und empfohlene Vorgehensweisen](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
 [Tutorial mit ersten Schritten](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Anleitung zur Dokumentation](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [Einfache WCF-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Windows Communication Foundation-Beispiele](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)
