---
title: Was ist die Windows Communication Foundation?
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], technology overview
- technology overview [WCF]
- WCF [WCF], technology overview
ms.assetid: 40e1009d-ef15-450b-9848-62eabe5e5738
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7aecddc617afcaf197aa212e8eea7e1342c029fa
ms.sourcegitcommit: 08684dd61444c2f072b89b926370f750e456fca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="what-is-windows-communication-foundation"></a>Was ist die Windows Communication Foundation?
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] ist ein Framework zum Erstellen von dienstorientierten Anwendungen. Mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]können Sie Daten als asynchrone Nachrichten von einem Dienstendpunkt an einen anderen senden. Ein Dienstendpunkt kann Teil eines fortwährend verfügbaren von IIS gehosteten Diensts oder ein in einer Anwendung gehosteter Dienst sein. Ein Endpunkt kann ein Client eines Diensts sein, der Daten von einem Dienstendpunkt anfordert. Die Nachrichten können einfach aus einem als XML gesendeten einzelnen Zeichen oder Wort oder aus einem komplexen Strom binärer Daten bestehen. Einige Beispielszenarios enthalten Folgendes:  
  
-   Ein sicherer Dienst zur Verarbeitung von Geschäftstransaktionen.  
  
-   Ein Dienst, der aktuelle Daten für andere Dienste bereitstellt, z. B. für Netzwerkverkehrberichtsdienste oder andere Überwachungsdienste.  
  
-   Ein Chatdienst, mit dem zwei Personen in Echtzeit kommunizieren oder Daten austauschen können.  
  
-   Eine Dashboardanwendung, die Daten von einem oder mehreren Diensten abfragt und logisch darstellt.  
  
-   Macht einen mit Windows Workflow Foundation implementierten Workflow als WCF-Dienst verfügbar.  
  
-   Eine Silverlight-Anwendung zum Abfragen aktueller Datenfeeds von einem Dienst.  
  
 Zwar konnten solche Anwendung bereits vor [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]erstellt werden, allerdings ist mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] die Entwicklung von Endpunkten einfacher als je zuvor. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] wurde im Grunde entwickelt, um Benutzern einen leichten Zugang zur Entwicklung von Webdiensten und Webdienstclients zu ermöglichen.  
  
## <a name="features-of-wcf"></a>Funktionen von WCF  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] enthält die folgenden Funktionen. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [WCF Feature Details](../../../docs/framework/wcf/feature-details/index.md).  
  
-   **Dienstausrichtung**  
  
     Ein Vorteil der Verwendung des WS-Standards ist die Möglichkeit, mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] *dienstorientierte* Anwendungen zu erstellen. Dienstorientierte Architektur (SOA) wird von Webdiensten für das Senden und Empfangen von Daten verwendet. Der allgemeine Vorteil der Dienste ist, dass sie untereinander lose verknüpft und nicht hartcodiert sind. Eine lose verknüpfte Beziehung impliziert, dass ein beliebiger Client, der auf einer beliebigen Plattform erstellt wurde, mit einem beliebigen Dienst verbunden werden kann, so lange die wesentlichen Vereinbarungen erfüllt sind.  
  
-   **Interoperabilität**  
  
     [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] implementiert aktuelle Industriestandards für die Webdienstinteroperabilität. [!INCLUDE[crabout](../../../includes/crabout-md.md)] zu den unterstützten Standards finden Sie unter [Interoperability and Integration](../../../docs/framework/wcf/feature-details/interoperability-and-integration.md).  
  
-   **Mehrere Nachrichtenmuster**  
  
     Nachrichten werden in einem von mehreren Mustern ausgetauscht. Das gängigste Muster ist das Anforderung-Antwort-Muster, bei dem ein Endpunkt Daten von einem zweiten Endpunkt abfragt. Der zweite Endpunkt antwortet. Es gibt noch weitere Muster, wie z. B. eine unidirektionale Nachricht, bei der ein einzelner Endpunkt eine Nachricht ohne Erwartung einer Antwort sendet. Ein komplexeres Muster ist das Duplex-Nachrichtenaustauschmuster, bei dem zwei Endpunkte eine Verbindung herstellen und sich wie bei einem Programm für Sofortnachrichten gegenseitig Daten senden. [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Implementieren verschiedener Nachrichtenaustauschmuster mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] finden Sie unter [Contracts](../../../docs/framework/wcf/feature-details/contracts.md).  
  
-   **Dienstmetadaten**  
  
     [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] unterstützt das Veröffentlichen von Metadaten in den Formaten der Branchenstandards, z. B. WSDL, XML-Schema und WS-Richtlinie. Diese Metadaten können verwendet werden, um Clients für den Zugriff auf [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienste automatisch zu erstellen und zu konfigurieren. Metadaten können per HTTP und HTTPS oder mit dem Austauschstandard für Webdienstmetadaten veröffentlicht werden. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Metadata](../../../docs/framework/wcf/feature-details/metadata.md).  
  
-   **Datenverträge**  
  
     Da [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] mit [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]erstellt wird, enthält es auch codefreundliche Methoden für die Bereitstellung der Verträge, die erzwungen werden sollen. Einer der universalen Vertragstypen ist der Datenvertrag. Beim Codieren des Diensts mit Visual C# oder Visual Basic lassen sich Daten am einfachsten durch das Erstellen von Klassen verwalten, die eine Datenentität mit zur Datenentität gehörenden Eigenschaften darstellen. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] enthält ein umfassendes System für das einfache Arbeiten mit Daten. Nachdem Sie die Klassen erstellt haben, die Daten darstellen, werden vom Dienst automatisch die Metadaten erstellt, mit denen Clients die von Ihnen entworfenen Datentypen verarbeiten können. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Using Data Contracts](../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
  
-   **Sicherheit**  
  
     Nachrichten können zu Datenschutzzwecken verschlüsselt werden, und die Benutzer können zur Authentifizierung aufgefordert werden, bevor Sie Berechtigung zum Empfangen von Nachrichten erhalten. Sicherheit kann mit bekannten Standards wie SSL oder WS-SecureConversation implementiert werden. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Sicherheit](../../../docs/framework/wcf/feature-details/security.md).  
  
-   **Mehrfache Transporte und Codierungen**  
  
     Nachrichten können mithilfe der zahlreichen integrierten Transportprotokolle und -codierungen versendet werden. Die gängigste Protokoll- und Codierungsmethode ist das Senden von textcodierten SOAP-Nachrichten mit dem HyperText Transfer Protocol (HTTP) zur Verwendung im World Wide Web. Alternativ können Sie mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Nachrichten über TCP, Named Pipes oder MSMQ senden. Diese Nachrichten können als Text oder mit einem optimierten Binärformat codiert werden.  Binärdaten können mit dem MTOM-Standard effizient gesendet werden. Wenn keine der bereitgestellten Transport- oder Codierungsmöglichkeiten Ihren Erfordernissen entspricht, können Sie eine benutzerdefinierte Transport- oder Codierungsmöglichkeit erstellen. [!INCLUDE[crabout](../../../includes/crabout-md.md)] indem Sie unterstützten Transporten und Codierungen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] finden Sie unter [Transporte](../../../docs/framework/wcf/feature-details/transports.md).  
  
-   **Zuverlässige Nachrichtensendung und Nachrichten in Warteschlangen**  
  
     [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] unterstützt zuverlässige Nachrichtenaustausch mit zuverlässigen Sitzungen über WS-Reliable Messaging implementiert und mithilfe von MSMQ. [!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Unterstützung von zuverlässigen Nachrichten und Nachrichten in Warteschlangen in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] finden Sie unter [Queues and Reliable Sessions](../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).  
  
-   **Permanente Nachrichten**  
  
     Bei einer permanenten Nachricht handelt es sich um eine Nachricht, die niemals aufgrund einer Unterbrechung der Kommunikation verloren geht. Die Nachrichten in einem Muster für permanente Nachrichten werden immer in einer Datenbank gespeichert. Wird die Verbindung unterbrochen, kann mit der Datenbank der Nachrichtenaustausch nach der erneuten Herstellung der Verbindung fortgesetzt werden. Sie können eine permanente Nachricht auch mit [!INCLUDE[wf](../../../includes/wf-md.md)]erstellen. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Workflow Services](../../../docs/framework/wcf/feature-details/workflow-services.md).  
  
-   **Transaktionen**  
  
     WCF unterstützt auch Transaktionen, bei denen eines der drei Transaktionsmodelle verwendet wird: WS-AtomicTtransactions, die APIs im <xref:System.Transactions> -Namespace und Microsoft Distributed Transaction Coordinator. [!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Transaktionsunterstützung in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] finden Sie unter [Transaktionen](../../../docs/framework/wcf/feature-details/transactions-in-wcf.md).  
  
-   **Unterstützung für AJAX und REST**  
  
     REST ist ein Beispiel für eine sich weiterentwickelnde Web 2.0-Technologie. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kann für die Verarbeitung einfacher XML-Daten, die nicht von einem SOAP-Umschlag umgeben sind, konfiguriert werden. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kann außerdem für die Unterstützung spezifischer XML-Formate, z. B. ATOM (ein verbreiteter RSS-Standard), und sogar für die Unterstützung von Nicht-XML-Formaten, z. B. JavaScript Object Notation (JSON), erweitert werden.  
  
-   **Erweiterungen**  
  
     Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Architektur verfügt über eine Reihe von Erweiterungspunkten. Wenn zusätzliche Fähigkeiten benötigt werden, können Sie an verschiedenen Punkten ansetzen, um das Verhalten eines Diensts anzupassen. [!INCLUDE[crabout](../../../includes/crabout-md.md)] verfügbaren Erweiterungspunkten finden Sie unter [Erweitern von WCF](../../../docs/framework/wcf/extending/index.md).  
  
## <a name="wcf-integration-with-other-microsoft-technologies"></a>WCF-Integration mit anderen Microsoft-Technologien  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ist eine flexible Plattform. Aufgrund der hohen Flexibilität wird [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] auch in zahlreichen anderen Produkten von Microsoft eingesetzt. Durch Kenntnisse der Grundlagen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]besitzen Sie einen unmittelbaren Vorteil, wenn Sie auch eines dieser Produkte verwenden.  
  
 Die erste Technologie, die mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kombiniert wurde, war Windows Workflow Foundation (WF). Workflows vereinfachen die Anwendungsentwicklung durch die kapselnden Schritte im Workflow als "Aktivitäten". In der ersten Version von [!INCLUDE[wf2](../../../includes/wf2-md.md)]musste ein Entwickler einen Host für den Workflow erstellen. Die darauffolgende Version von [!INCLUDE[wf2](../../../includes/wf2-md.md)] war mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]kombiniert. Ein beliebiger Workflow kann seither leicht in einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst gehostet werden. Wählen Sie hierzu in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]einfach WF/WCF als Projekttyp aus.  
  
 Microsoft BizTalk Server R2 nutzt u. a. ebenfalls [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] als Kommunikationstechnologie. BizTalk wurde zum Empfangen und Umwandeln von Daten aus einem Standardformat in ein anderes entwickelt. Nachrichten müssen an den zentralen Posteingang der Anwendung gesendet werden, wo sie entweder per strikter Zuordnung oder mit einer der BizTalk-Funktionen (z. B. Workflowmodul) umgewandelt werden können. BizTalk kann nun den Line of Business (LOB)-Adapter von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] verwenden, um Nachrichten an den Posteingang zu senden.  
  
 Microsoft Silverlight ist eine Plattform für die Entwicklung interoperabler und leistungsfähiger Webanwendungen, mit denen Entwickler multimediale Websites (z. B. mit Videostreams) erstellen können. Seit Version 2 ist [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] als Kommunikationstechnologie in Silverlight integriert und verbindet so Silverlight-Anwendungen mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Endpunkten.  
  
 Der [!INCLUDE[dublin](../../../includes/dublin-md.md)] -Anwendungsserver wurde speziell für die Bereitstellung und Verwaltung von Anwendungen entwickelt, die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] zur Kommunikation verwenden. Der [!INCLUDE[dublin2](../../../includes/dublin2-md.md)] -Server beinhaltet leistungsfähige Bearbeitungs- und Konfigurationsoptionen, die speziell für mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]kompatible Anwendungen konzipiert wurden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel>  
 [Wesentliche Windows Communication Foundation-Begriffe](../../../docs/framework/wcf/fundamental-concepts.md)  
 [Windows Communication Foundation-Architektur](../../../docs/framework/wcf/architecture.md)  
 [Richtlinien und empfohlene Vorgehensweisen](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
 [Tutorial mit ersten Schritten](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Anleitung zur Dokumentation](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [Einfache WCF-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Windows Communication Foundation-Beispiele](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)
