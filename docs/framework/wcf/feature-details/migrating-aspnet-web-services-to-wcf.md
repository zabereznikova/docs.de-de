---
title: Migrieren von ASP.NET-Webdiensten zu WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: fa707a4246d5bc9940417072c098b2973140f878
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598800"
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migrieren von ASP.NET-Webdiensten zu WCF
ASP.NET stellt .NET Framework-Klassenbibliotheken und Tools zum Erstellen von Webdiensten sowie Funktionen für Hostingdienste innerhalb von Internetinformationsdienste (IIS) bereit. Windows Communication Foundation (WCF) stellt .NET Framework Klassenbibliotheken, Tools und Hostingfunktionen bereit, mit denen die Kommunikation von Software Entitäten mithilfe von Protokollen ermöglicht wird, einschließlich derjenigen, die von Webdiensten verwendet werden.  Durch die Migration von ASP.NET-Webdiensten zu WCF können Ihre Anwendungen neue Features und Verbesserungen nutzen, die für WCF spezifisch sind.  
  
 WCF bietet verschiedene wichtige Vorteile im Vergleich zu ASP.NET-Webdiensten. Obwohl es sich bei den ASP.NET-Webdienst Tools ausschließlich um Webdienste handelt, stellt WCF Tools bereit, die verwendet werden können, wenn Software Entitäten für die Kommunikation untereinander erstellt werden müssen. Dadurch wird die Zahl der Technologien reduziert, mit denen Entwickler vertraut sein müssen, um verschiedene Softwarekommunikationsszenarien bedienen zu können, was zu einer Senkung der Kosten für Softwareentwicklungsressourcen sowie zu einem schnelleren Abschluss von Softwareentwicklungsprojekten führt.  
  
 Auch für Webdienst-Entwicklungsprojekte unterstützt WCF mehr Webdienst Protokolle als die Unterstützung von ASP.NET-Webdiensten. Diese zusätzlichen Protokolle sorgen für ausgereiftere Projektmappen, die u. a. zuverlässige Sitzungen und Transaktionen implizieren.  
  
 WCF unterstützt mehr Protokolle zum Transportieren von Nachrichten als ASP.NET-Webdienste. ASP.NET-Webdienste unterstützen nur das Senden von Nachrichten mit HTTP (Hypertext Transfer Protocol). WCF unterstützt das Senden von Nachrichten mithilfe von http sowie das Transmission Control Protocol (TCP), Named Pipes und Microsoft Message Queuing (MSMQ). Wichtiger ist, dass WCF erweitert werden kann, um zusätzliche Transportprotokolle zu unterstützen. Aus diesem Grund kann die mit WCF entwickelte Software so angepasst werden, dass Sie mit einer größeren Vielfalt anderer Software zusammenarbeitet, sodass die potenzielle Rendite erhöht werden kann.  
  
 WCF bietet weitaus umfangreichere Funktionen für die Bereitstellung und Verwaltung von Anwendungen als ASP.net Web Services. Zusätzlich zu einem Konfigurationssystem, das ASP.net auch hat, bietet WCF einen Konfigurations-Editor, Aktivitäts Ablauf Verfolgung von Absendern zu Empfängern und zurück über eine beliebige Anzahl von Vermittler, einen Ablaufverfolgungs-Viewer, Nachrichten Protokollierung, zahlreiche Leistungsindikatoren und Unterstützung für Windows-Verwaltungsinstrumentation.  
  
 Wenn Sie diese potenziellen Vorteile von WCF im Vergleich zu ASP.NET-Webdiensten verwenden oder die ASP.NET-Webdienste verwenden, haben Sie mehrere Optionen:  
  
- Verwenden Sie weiterhin ASP.NET-Webdienste, und stellen Sie die Vorteile von WCF bereit.  
  
- Verwenden Sie ASP.NET-Webdienste weiterhin mit der Absicht, WCF zu einem späteren Zeitpunkt zu verwenden. In den Themen in diesem Abschnitt wird erläutert, wie Sie die Chancen für die Verwendung neuer ASP.NET-Webdienst Anwendungen in Verbindung mit zukünftigen WCF-Anwendungen maximieren können. In den Themen in diesem Abschnitt wird auch erläutert, wie neue ASP.NET-Webdienste erstellt werden, um die Migration zu WCF zu vereinfachen. Wenn das Sichern der Dienste jedoch wichtig ist oder Zuverlässigkeit oder Transaktions Zusicherungen erforderlich sind oder wenn benutzerdefinierte Verwaltungsfunktionen erstellt werden müssen, ist es eine bessere Option, WCF zu übernehmen. WCF ist für genau solche Szenarien konzipiert.  
  
- Übernehmen Sie WCF für die neue Entwicklung, während Sie weiterhin vorhandene ASP.NET-Webdienst Anwendungen verwalten. Diese Vorgehensweise ist wahrscheinlich optimal. Dies führt zu den Vorteilen von WCF und spart gleichzeitig die Kosten für die Änderung der vorhandenen Anwendungen. In diesem Szenario können neue WCF-Anwendungen zusammen mit vorhandenen ASP.NET-Anwendungen vorhanden sein. Neue WCF-Anwendungen können vorhandene ASP.NET-Webdienste verwenden, und WCF kann verwendet werden, um neue operative Funktionen in vorhandene ASP.NET-Anwendungen zu programmieren, indem der WCF ASP.NET-Kompatibilitätsmodus verwendet wird.  
  
- Übernehmen Sie WCF, und migrieren Sie vorhandene ASP.NET-Webdienst Anwendungen zu WCF. Sie können diese Option auswählen, um die vorhandenen Anwendungen mit den von WCF bereitgestellten Funktionen zu verbessern oder die Funktionalität vorhandener ASP.NET-Webdienste in neuen, leistungsfähigeren WCF-Anwendungen zu reproduzieren.  
  
> [!NOTE]
> Es muss sorgfältig vorgegangen werden, wenn ein WCF-Dienst von IIS 5. x gehostet wird und ASP.NET deinstalliert wird. Wenn ein WCF-Dienst von IIS 5. x gehostet wird, kann der Code für den Dienst angefordert werden, wenn ASP.NET deinstalliert wird. Wenn ASP.net auf einem Betriebssystem deinstalliert wird, auf dem IIS 5. x ausgeführt wird, und WCF deinstalliert wird, wird eine Datei mit der Erweiterung. svc als Textdatei betrachtet, und der Inhalt, einschließlich des Quellcodes, wird an den Anforderer zurückgegeben.  
  
 In diesem Abschnitt werden diese Optionen ausführlich beschrieben. es werden ASP.NET-Webdienste mit WCF verglichen und Anweisungen zum Migrieren des ASP.NET-Webdienst Codes zu WCF bereitstellt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft](anticipating-adopting-wcf-migration.md)
- [Vorbereitungen für Windows Communication Foundation: einfachere Migration in der Zukunft](anticipating-adopting-the-wcf-easing-future-integration.md)
- [Übernehmen von Windows Communication Foundation](adopting-wcf.md)
- [Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards](comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
- [Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung](comparing-aspnet-web-services-to-wcf-based-on-development.md)
