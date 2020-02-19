---
title: WCF und ASP.NET-Web-API
ms.date: 03/30/2017
ms.assetid: 08ceded3-fd9a-4467-9715-c4cbd9c7228e
ms.openlocfilehash: e058b2ea5e9188c365c679ae46c4d7c9de45e4b9
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452564"
---
# <a name="wcf-and-aspnet-web-api"></a>WCF und ASP.NET-Web-API
WCF ist das einheitliche Programmiermodell von Microsoft, mit dem dienstorientierte Anwendungen erstellt werden können. Es ermöglicht Entwicklern das Erstellen sicherer, zuverlässiger und transaktiver Lösungen für die plattformübergreifende Integration und bietet unfassende Interoperabilität mit vorhandenen Investitionen. [ASP.net-Web-API](https://www.asp.net/web-api) ist ein Framework, das das Erstellen von http-Diensten erleichtert, die eine breite Palette von Clients erreichen, einschließlich Browsern und mobilen Geräten. ASP.NET-Web-API ist eine optimale Plattform zum Erstellen von RESTful-Anwendungen im Kontext des .NET Framework. Die Informationen in diesem Thema sollen Sie dabei unterstützen, die für Ihre Anforderungen optimal geeignete Technologie zu finden.  
  
## <a name="choosing-which-technology-to-use"></a>Wahl der richtigen Technologie  
 In der folgenden Tabelle sind die wichtigsten Funktionen der jeweiligen Technologie beschrieben.  
  
|WCF|ASP.NET Web-API|  
|---------|---------------------|  
|Ermöglicht das Erstellen von Diensten, die mehrere Transportprotokolle (HTTP, TCP, UDP und benutzerdefinierte Transporte) und das Wechseln zwischen den Protokollen unterstützen.|nur HTTP Das erstklassige Programmiermodell für http. Geeignetere Informationen für den Zugriff über verschiedene Browser, Mobile Geräte usw.|  
|Ermöglicht das Erstellen von Diensten, die mehrere Codierungen (textbasiert, MTOM und binär) desselben Nachrichtentyps sowie den Wechsel zwischen den Codierungen unterstützen.|Ermöglicht das Erstellen von Web-APIs, die eine Vielzahl von Medientypen einschließlich XML, JSON usw. unterstützen.|  
|Unterstützt das Erstellen von Diensten mit WS-*-Standards, z. B. zuverlässigem Messaging, Transaktionen und Nachrichtensicherheit.|Verwendet grundlegende Protokolle und Formate wie http, websockets, SSL, JSON und XML. Höher entwickelte Protokolle wie zuverlässiges Messaging oder Transaktionen werden nicht unterstützt.|  
|Unterstützt die Nachrichtenaustauschmuster "Anforderung-Antwort", "Unidirektional" und "Duplex".|HTTP ist Anforderung/Antwort, aber zusätzliche Muster können durch die [signalr](https://github.com/SignalR/SignalR) -und websockets-Integration unterstützt werden.|  
|WCF-SOAP-Dienste können in WSDL beschrieben werden und bieten automatisierten Tools die Möglichkeit, selbst für Dienste mit komplexen Schemas Clientproxys zu generieren.|Es gibt zahlreiche Methoden zur Beschreibung einer Web-API, von automatisch generierten HTML-Hilfeseiten mit Informationen zu Codeausschnitten bis hin zu strukturierten Metadaten für integrierte OData-APIs.|  
|Wird mit dem .NET Framework ausgeliefert.|Wird mit .NET Framework geliefert, ist aber Open Source und auch Out-of-Band als unabhängiger Download verfügbar.|  
  
 Verwenden Sie WCF, um zuverlässige, sichere Webdienste zu erstellen, auf die über eine Vielzahl von Transporten zugegriffen werden kann. Verwenden Sie die ASP.NET-Web-API zum Erstellen HTTP-basierter Dienste, auf die von vielen verschiedenen Clients zugegriffen werden kann. Verwenden Sie die ASP.NET-Web-API, wenn Sie neue REST-Dienste entwerfen und erstellen. Obwohl WCF das Schreiben von REST-Diensten bis zu einem gewissen Grad unterstützt, bietet die ASP.NET-Web-API umfassendere REST-Unterstützung. Darüber hinaus werden zukünftige Optimierungen an REST-Funktionen in der ASP.NET-Web-API vorgenommen. Wenn Sie bei einem vorhandenen WCF-Dienst zusätzliche REST-Endpunkte verfügbar machen möchten, verwenden Sie WCF und <xref:System.ServiceModel.WebHttpBinding>.  
  
## <a name="see-also"></a>Siehe auch

- [Was ist die Windows Communication Foundation?](whats-wcf.md)
- [Wesentliche Windows Communication Foundation-Begriffe](fundamental-concepts.md)
