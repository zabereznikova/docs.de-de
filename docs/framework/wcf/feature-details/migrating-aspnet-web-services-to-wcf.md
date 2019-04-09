---
title: Migrieren von ASP.NET-Webdiensten zu WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: 703088cdaae69d90d71fb950912538ea0662229b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211087"
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migrieren von ASP.NET-Webdiensten zu WCF
ASP.NET stellt .NET Framework-Klassenbibliotheken und Tools zum Erstellen von Webdiensten sowie Funktionen für Hostingdienste innerhalb von Internetinformationsdienste (IIS) bereit. Windows Communication Foundation (WCF) bietet .NET Framework-Klassenbibliotheken, Tools und Hostingfunktionen zum Aktivieren von Softwareentitäten zur Kommunikation über alle Protokolle, einschließlich von Webdiensten verwendet werden.  Migrieren von ASP.NET-Webdiensten zu WCF ermöglicht Ihren Anwendungen nutzen Sie die Vorteile der neuen Features und Verbesserungen, die für WCF eindeutig sind.  
  
 WCF bietet einige wichtige Vorteile in Bezug auf ASP.NET-Webdienste. WCF bietet Tools, die verwendet werden können, wenn Softwareentitäten vorgenommen werden müssen, um miteinander zu kommunizieren, ASP.NET Web Services-Tools sind ausschließlich für die Erstellung von Webdiensten. Dadurch wird die Zahl der Technologien reduziert, mit denen Entwickler vertraut sein müssen, um verschiedene Softwarekommunikationsszenarien bedienen zu können, was zu einer Senkung der Kosten für Softwareentwicklungsressourcen sowie zu einem schnelleren Abschluss von Softwareentwicklungsprojekten führt.  
  
 Sogar für webdienstentwicklungsprojekte unterstützt WCF mehr Webdienstprotokolle als ASP.NET Web Services-Support. Diese zusätzlichen Protokolle sorgen für ausgereiftere Projektmappen, die u. a. zuverlässige Sitzungen und Transaktionen implizieren.  
  
 WCF unterstützt mehr Protokolle zum Transportieren von Nachrichten als ASP.NET-Webdienste. ASP.NET-Webdienste unterstützen nur das Senden von Nachrichten mit HTTP (Hypertext Transfer Protocol). WCF unterstützt sendende von Nachrichten mithilfe von HTTP als auch das Protokoll TCP (Transmission Control), named Pipes und Microsoft Message Queuing (MSMQ). Noch wichtiger ist, kann WCF erweitert werden, um Unterstützung weiterer Transportprotokolle. Aus diesem Grund kann Software entwickelt wurde, mithilfe von WCF an die Arbeit mit einer größeren Vielfalt verschiedener Softwareprogramme, was zu einer Erhöhung der potenziellen Rendite angepasst werden.  
  
 WCF bietet umfangreicheren Funktionen für die Bereitstellung sowie Verwaltung von Anwendungen als ASP.NET-Webdienste. Neben einem Konfigurationssystem, das ASP.NET ebenfalls verfügt, bietet WCF einen Konfigurations-Editor, aktivitätsablaufverfolgung von Absendern zu Empfängern und zurück über zahlreiche Vermittler, einen Ablaufverfolgungs-Viewer, nachrichtenprotokollierung, eine große Anzahl von Leistungsindikatoren und Unterstützung für Windows-Verwaltungsinstrumentation.  
  
 Betrachten Sie diese potenziellen Vorteile von WCF, relativ zur ASP.NET Web Services, wenn Sie verwenden oder möglicher Verwendung von ASP.NET Web Services stehen Ihnen mehrere Optionen:  
  
-   Fahren Sie mit ASP.NET Web Services verwenden und die von WCF angebotenen Vorteile verzichten.  
  
-   Verwenden Sie weiterhin die ASP.NET-Webdienste mit dem Ziel Einführung von WCF zu einem Zeitpunkt in der Zukunft. Die Themen in diesem Abschnitt wird erläutert, wie die Perspektiven verwenden, neue ASP.NET-Webdienstanwendungen zusammen mit zukünftigen WCF-Anwendungen zu maximieren. Die Themen in diesem Abschnitt wird auch erläutert, wie erstellen Sie neue ASP.NET-Webdienste so zu WCF Migrieren zu vereinfachen. Jedoch wenn Schutz der Dienste wichtig ist oder Zuverlässigkeit oder transaktionszusicherungen erforderlich sind, oder wenn benutzerdefinierte Verwaltungsfunktionen erstellt werden müssen, und es ist eine bessere Option, um WCF zu übernehmen. WCF ist für genau diese Szenarien konzipiert.  
  
-   Übernehmen Sie WCF für die neue Entwicklung, während Sie weiterhin Ihre vorhandenen ASP.NET-Webdienstanwendungen zu verwalten. Diese Vorgehensweise ist wahrscheinlich optimal. Den Vorteilen von WCF, während die Kosten für das Ändern der vorhandenen Anwendungen verwenden das ersetzen. In diesem Szenario können neue WCF-Anwendungen mit vorhandenen ASP.NET-Anwendungen gleichzeitig vorhanden sein. Neue WCF-Anwendungen werden in der Lage, vorhandene ASP.NET-Webdienste verwenden, und WCF kann verwendet werden, neue operative Funktionen in vorhandenen ASP.NET-ANWENDUNGEN laufen, da der ASP.NET-Kompatibilitätsmodus von WCF-Programmierung.  
  
-   Übernehmen Sie WCF, und migrieren Sie vorhandene ASP.NET-Webdienstanwendungen zu WCF. Sie können diese Option aus, um die vorhandenen Anwendungen mit Funktionen von WCF zu verbessern oder zu reproduzieren, die Funktionalität von vorhandenen ASP.NET-Webdiensten innerhalb neuer, die leistungsfähige WCF-Anwendungen.  
  
> [!NOTE]
>  Vorsicht geboten, wenn ein WCF-Dienst gehostet wird von IIS 5.x und ASP.NET deinstalliert wird. Wenn ein WCF-Dienst gehostet wird, von IIS 5.x, den Code für den Dienst können angefordert werden, wenn ASP.NET deinstalliert wird. Beim Deinstallieren von ASP.NET auf einem Betriebssystem, auf denen IIS ausgeführt wird 5.x und WCF deinstalliert wird, eine mit der Erweiterung .svc-Datei wird als Textdatei betrachtet und der Inhalt, einschließlich Quellcode, an die anfordernde Person zurückgegeben.  
  
 Dieser Abschnitt beschreibt diese Optionen ausführlich, vergleicht ASP.NET-Webdienste zu WCF und enthält Anweisungen dazu, wie Sie Ihre ASP.NET Web Services-Code zu WCF migrieren.  
  
## <a name="see-also"></a>Siehe auch

- [Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
- [Vorbereitungen für Windows Communication Foundation: einfachere Migration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
- [Übernehmen von Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)
- [Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
- [Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
