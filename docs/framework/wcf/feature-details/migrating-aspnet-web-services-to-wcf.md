---
title: Migrieren von ASP.NET-Webdiensten zu WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ca1eb73842f3f7dac5557c1eafff637396d317a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migrieren von ASP.NET-Webdiensten zu WCF
ASP.NET stellt .NET Framework-Klassenbibliotheken und Tools zum Erstellen von Webdiensten sowie Funktionen für Hostingdienste innerhalb von Internetinformationsdienste (IIS) bereit. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet .NET Framework-Klassenbibliotheken, Tools und Hostingfunktionen für die Kommunikation von Softwareentitäten mit beliebigen Protokollen, einschließlich Protokollen, die von Webdiensten verwendet werden.  Durch Migrieren von ASP.NET-Webdiensten zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] können Ihre Anwendungen neue Funktionen und Verbesserungen nutzen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eindeutig sind.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet einige wichtige Vorteile in Bezug auf ASP.NET-Webdienste. Während ASP.NET-Webdienste einzig zum Erstellen von Webdiensten dienen, bietet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Tools, die verwendet werden können, wenn Softwareentitäten miteinander kommunizieren müssen. Dadurch wird die Zahl der Technologien reduziert, mit denen Entwickler vertraut sein müssen, um verschiedene Softwarekommunikationsszenarien bedienen zu können, was zu einer Senkung der Kosten für Softwareentwicklungsressourcen sowie zu einem schnelleren Abschluss von Softwareentwicklungsprojekten führt.  
  
 Sogar für Webdienstentwicklungsprojekte unterstützt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mehr Webdienstprotokolle als die ASP.NET-Unterstützung für Webdienste. Diese zusätzlichen Protokolle sorgen für ausgereiftere Projektmappen, die u. a. zuverlässige Sitzungen und Transaktionen implizieren.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt mehr Protokolle zum Transportieren von Nachrichten als ASP.NET-Webdienste. ASP.NET-Webdienste unterstützen nur das Senden von Nachrichten mit HTTP (Hypertext Transfer Protocol). [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt das Senden von Nachrichten mit HTTP, TCP (Transmission Control Protocol), Named Pipes und Microsoft Message Queuing (MSMQ). Darüber hinaus kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zur Unterstützung weiterer Transportprotokolle erweitert werden. Mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] entwickelte Software kann daher angepasst werden, um mit einer größeren Vielfalt verschiedener Softwareprogramme zusammenzuarbeiten, was zu einer Erhöhung der potenziellen Rendite führt.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet umfangreichere Funktionen zum Bereitstellen und Verwalten von Anwendungen als ASP.NET-Webdienste. Neben einem Konfigurationssystem, über das ASP.NET ebenfalls verfügt, bietet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen Konfigurations-Editor, Aktivitätsablaufverfolgung von Absendern zu Empfängern und zurück über zahlreiche Vermittler, einen Ablaufverfolgungs-Viewer, Nachrichtenprotokollierung, zahlreiche Leistungsindikatoren und Unterstützung für die Windows-Verwaltungsinstrumentation.  
  
 Angesichts dieser potenziellen Vorteile von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] im Vergleich zu ASP.NET-Webdiensten haben Sie bei Verwendung oder möglicher Verwendung von ASP.NET-Webdiensten mehrere Möglichkeiten:  
  
-   Sie können die ASP.NET-Webdienste weiter verwenden und auf die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] angebotenen Vorteile verzichten.  
  
-   Sie können die ASP.NET-Webdienste mit der Absicht weiter verwenden, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in absehbarer Zeit zu übernehmen. In den Themen dieses Abschnitts wird erläutert, wie Sie die Perspektiven maximieren, neue ASP.NET-Webdienstanwendungen in Verbindung mit künftigen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen zu verwenden. Außerdem wird in den Themen dieses Abschnitts beschrieben, wie Sie neue ASP.NET-Webdienste so erstellen, dass eine Migration zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erleichtert wird. Wenn jedoch der Schutz der Dienste wichtig ist oder Zuverlässigkeit oder Transaktionszusicherungen erforderlich sind oder wenn benutzerdefinierte Verwaltungsfunktionen erstellt werden müssen, sollten Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementieren. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist für genau diese Szenarien vorgesehen.  
  
-   Implementieren Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] für neue Entwicklungen, und behalten Sie gleichzeitig Ihre vorhandenen ASP.NET-Webdienstanwendungen bei. Diese Vorgehensweise ist wahrscheinlich optimal. Sie können so von den Vorteilen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] profitieren und gleichzeitig die Kosten sparen, die zum Ändern der vorhandenen Anwendungen notwendig wären. In diesem Szenario können neue [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen neben vorhandenen ASP.NET-Anwendungen laufen. Neue [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen können vorhandene ASP.NET-Webdienste verwenden, und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann dazu verwendet werden, neue operative Funktionen in vorhandenen ASP.NET-Anwendungen im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-ASP.NET-Kompatibilitätsmodus zu programmieren.  
  
-   Implementieren Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], und migrieren Sie vorhandene ASP.NET-Webdienstanwendungen zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Mit dieser Möglichkeit können Sie vorhandene Anwendungen mit Funktionen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verbessern oder die Funktionen von vorhandenen ASP.NET-Webdiensten innerhalb neuer, leistungsstärkerer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen reproduzieren.  
  
> [!NOTE]
>  Vorsicht ist geboten, wenn ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst von IIS 5.x gehostet wird und ASP.NET deinstalliert wird. Wenn ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst von IIS 5.x gehostet wird, kann beim Deinstallieren von ASP.NET der Code für den Dienst angefordert werden. Wenn ASP.NET auf einem Betriebssystem deinstalliert wird, auf dem IIS 5.x ausgeführt und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deinstalliert wird, wird eine Datei mit der Erweiterung .svc als Textdatei betrachtet und der Inhalt, einschließlich Quellcode, wird an den Anforderer zurückgegeben.  
  
 Dieser Abschnitt beschreibt diese Optionen ausführlich, vergleicht ASP.NET-Webdienste mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und bietet Anleitungen für die Migration Ihres ASP.Net-Webdienstcodes zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [Windows Communication Foundation eingeführt](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
