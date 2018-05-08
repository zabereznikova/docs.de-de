---
title: Migrieren von ASP.NET-Webdiensten zu WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: 7d43c66952d17a91e38ae1b086478b9416321b8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migrieren von ASP.NET-Webdiensten zu WCF
ASP.NET stellt .NET Framework-Klassenbibliotheken und Tools zum Erstellen von Webdiensten sowie Funktionen für Hostingdienste innerhalb von Internetinformationsdienste (IIS) bereit. Windows Communication Foundation (WCF) bietet .NET Framework-Klassenbibliotheken, Tools und Hostingfunktionen für Softwareentitäten für die Kommunikation über alle Protokolle, einschließlich von Webdiensten verwendet.  Migrieren von ASP.NET-Webdiensten zu WCF können Ihre Anwendungen neue Funktionen und Verbesserungen, die nur für die WCF nutzen.  
  
 WCF bietet einige wichtige Vorteile in Bezug auf ASP.NET-Webdienste. WCF bietet Tools, die verwendet werden können, wenn Softwareentitäten müssen miteinander kommunizieren, während ASP.NET-Webdienste einzig zum Erstellen von Web Services erhalten. Dadurch wird die Zahl der Technologien reduziert, mit denen Entwickler vertraut sein müssen, um verschiedene Softwarekommunikationsszenarien bedienen zu können, was zu einer Senkung der Kosten für Softwareentwicklungsressourcen sowie zu einem schnelleren Abschluss von Softwareentwicklungsprojekten führt.  
  
 Sogar für webdienstentwicklungsprojekte unterstützt WCF mehr Webdienstprotokolle als Unterstützung der ASP.NET Web-Dienste. Diese zusätzlichen Protokolle sorgen für ausgereiftere Projektmappen, die u. a. zuverlässige Sitzungen und Transaktionen implizieren.  
  
 WCF unterstützt mehr Protokolle zum Transportieren von Nachrichten als ASP.NET-Webdienste. ASP.NET-Webdienste unterstützen nur das Senden von Nachrichten mit HTTP (Hypertext Transfer Protocol). WCF unterstützt sendende von Nachrichten mithilfe von HTTP als auch den TCP Transmission Control Protocol (), named Pipes und Microsoft Message Queuing (MSMQ). Noch wichtiger ist, kann WCF erweitert werden, um die Unterstützung weiterer Transportprotokolle. Aus diesem Grund kann Software mithilfe von WCF entwickelt wurden, funktionieren nun zusammen mit einer größeren Vielfalt verschiedener Softwareprogramme Datendurchsatzrate zu erhöhen, der potenziellen Rendite angepasst werden.  
  
 WCF bietet umfangreichere Funktionen für die Bereitstellung und Verwaltung von Anwendungen als ASP.NET-Webdienste bietet. Neben einem Konfigurationssystem, das ASP.NET ebenfalls verfügt, bietet WCF einen Konfigurations-Editor, aktivitätsablaufverfolgung von Absendern zu Empfängern und zurück über zahlreiche Vermittler, einen Ablaufverfolgungs-Viewer, nachrichtenprotokollierung, zahlreiche Leistungsindikatoren und Unterstützung für Windows-Verwaltungsinstrumentation.  
  
 Betrachten Sie diese potenziellen Vorteile von WCF relativ zur ASP.NET Web Services, wenn Sie mit oder möglicher Verwendung von ASP.NET-Webdiensten stehen Ihnen mehrere Optionen:  
  
-   ASP.NET-Webdienste verwenden und die angebotenen Vorteile verzichten, die von WCF auf Weiter.  
  
-   Verwenden Sie weiterhin ASP.NET-Webdienste absehbarer einführen WCF zu einem Zeitpunkt in der Zukunft. Die Themen in diesem Abschnitt wird erläutert, wie Maximieren Sie die potenziellen Kunden für die neue ASP.NET-Webdienstanwendungen zusammen mit zukünftigen WCF-Anwendungen verwenden können. Die Themen in diesem Abschnitt wird auch erläutert, wie neue ASP.NET Web Services, um sie zu WCF migrieren erleichtern erstellen. Jedoch wenn Schutz der Dienste wichtig ist oder Zuverlässigkeit oder transaktionszusicherungen erforderlich sind, oder wenn benutzerdefinierte Verwaltungsfunktionen erstellt werden müssen, und es ist eine bessere Option übernehmen, WCF. WCF ist für genau diese Szenarien ausgelegt.  
  
-   Übernahme von WCF für Neuentwicklungen, während die Verarbeitung fortgesetzt, um Ihre vorhandenen ASP.NET-Webdienstanwendungen zu verwalten. Diese Vorgehensweise ist wahrscheinlich optimal. Den Vorteilen von WCF, während die Kosten für das Ändern der vorhandenen Anwendungen notwendig Ersatz. In diesem Szenario können neue WCF-Clientanwendungen vorhandenen ASP.NET-ANWENDUNGEN laufen gleichzeitig vorhanden sein. Neue WCF-Anwendungen sind in der Lage, vorhandene ASP.NET-Webdienste verwenden, und WCF kann neue operative Funktionen in vorhandenen ASP.NET-ANWENDUNGEN laufen nach ASP.NET-Kompatibilitätsmodus von WCF-Programmierung verwendet werden.  
  
-   Übernehmen Sie WCF und migrieren Sie vorhandene ASP.NET-Webdienstanwendungen zu WCF. Sie können diese Option, um vorhandenen Anwendungen mit Funktionen von WCF zu verbessern oder zu reproduzieren, die Funktionalität von vorhandenen ASP.NET-Webdiensten innerhalb neuer, leistungsfähigere WCF-Anwendungen.  
  
> [!NOTE]
>  Vorsicht geboten, wenn ein WCF-Dienst gehostet wird von IIS 5.x und ASP.NET deinstalliert wird. Wenn ein WCF-Dienst gehostet wird, von IIS 5.x, den Code für den Dienst kann angefordert werden, wenn ASP.NET deinstalliert wird. Wenn ASP.NET auf einem Betriebssystem, auf denen IIS ausgeführt wird deinstalliert wird 5.x und WCF deinstalliert wird, eine Datei mit der Erweiterung .svc als Textdatei betrachtet wird und der Inhalt, einschließlich Quellcode, wird an den anforderer zurückgegeben.  
  
 Dieser Abschnitt beschreibt diese Optionen ausführlich, vergleicht ASP.NET-Webdienste nach WCF und enthält Anweisungen zum Migrieren von Codes ASP.NET-Webdienste nach WCF.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [Übernehmen von Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
