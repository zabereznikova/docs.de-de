---
title: "WCF und ASP.NET-Web-API | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 08ceded3-fd9a-4467-9715-c4cbd9c7228e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# WCF und ASP.NET-Web-API
WCF ist das einheitliche Programmiermodell von Microsoft, mit dem dienstorientierte Anwendungen erstellt werden können.Es ermöglicht Entwicklern das Erstellen sicherer, zuverlässiger und transaktiver Lösungen für die plattformübergreifende Integration und bietet unfassende Interoperabilität mit vorhandenen Investitionen.\(Die [ASP.NET\-Web\-API](http://www.asp.net/web-api) ist ein Framework, das die einfache Erstellung von HTTP\-Diensten für eine breite Palette von Clients unterstützt, darunter auch Browser und mobile Geräte.Die ASP.NET\-Web\-API ist eine ideale Plattform zum Erstellen von RESTful\-Anwendungen in .NET Framework.Die Informationen in diesem Thema sollen Sie dabei unterstützen, die für Ihre Anforderungen optimal geeignete Technologie zu finden.  
  
## Wahl der richtigen Technologie  
 In der folgenden Tabelle sind die wichtigsten Funktionen der jeweiligen Technologie beschrieben.  
  
|WCF|ASP.NET\-Web\-API|  
|---------|-----------------------|  
|Ermöglicht das Erstellen von Diensten, die mehrere Transportprotokolle \(HTTP, TCP, UDP und benutzerdefinierte Transporte\) und das Wechseln zwischen den Protokollen unterstützen.|nur HTTPEin erstklassiges Programmiermodell für HTTP. Unterstützt insbesondere den Zugriff von verschiedenen Browsern, mobilen Geräten usw. und bietet eine große Reichweite.|  
|Ermöglicht das Erstellen von Diensten, die mehrere Codierungen \(textbasiert, MTOM und binär\) desselben Nachrichtentyps sowie den Wechsel zwischen den Codierungen unterstützen.|Ermöglicht das Erstellen von Web\-APIs, die eine Vielzahl von Medientypen einschließlich XML, JSON usw. unterstützen.|  
|Unterstützt das Erstellen von Diensten mit WS\-\*\-Standards, z. B. zuverlässigem Messaging, Transaktionen und Nachrichtensicherheit.|Verwendet Standardprotokolle und \-formate wie HTTP, WebSockets, SSL, JQuery, JSON und XML.Höher entwickelte Protokolle wie zuverlässiges Messaging oder Transaktionen werden nicht unterstützt.|  
|Unterstützt die Nachrichtenaustauschmuster "Anforderung\-Antwort", "Unidirektional" und "Duplex".|HTTP entspricht dem Muster "Anforderung\-Antwort", durch [SignalR](https://github.com/SignalR/SignalR) und die WebSockets\-Integration können jedoch weitere Muster unterstützt werden.|  
|WCF\-SOAP\-Dienste können in WSDL beschrieben werden und bieten automatisierten Tools die Möglichkeit, selbst für Dienste mit komplexen Schemas Clientproxys zu generieren.|Es gibt zahlreiche Methoden zur Beschreibung einer Web\-API, von automatisch generierten HTML\-Hilfeseiten mit Informationen zu Codeausschnitten bis hin zu strukturierten Metadaten für integrierte OData\-APIs.|  
|Im Lieferumfang von .NET Framework enthalten.|Im Lieferumfang von .NET Framework enthalten, steht jedoch auch als unabhängiges Out\-of\-Band\-Download bereit, da es sich um eine Open Source\-API handelt.|  
  
 Verwenden Sie WCF zum Erstellen zuverlässiger, sicherer Webdienste, auf die über eine Vielzahl von Transporten zugegriffen werden kann.Verwenden Sie die ASP.NET\-Web\-API zum Erstellen HTTP\-basierter Dienste, auf die von vielen verschiedenen Clients zugegriffen werden kann.Verwenden Sie die ASP.NET\-Web\-API, wenn Sie neue REST\-Dienste entwerfen und erstellen.Obwohl WCF das Schreiben von REST\-Diensten bis zu einem gewissen Grad unterstützt, bietet die ASP.NET\-Web\-API umfassendere REST\-Unterstützung. Darüber hinaus werden zukünftige Optimierungen an REST\-Funktionen in der ASP.NET\-Web\-API vorgenommen.Wenn Sie bei einem vorhandenen WCF\-Dienst zusätzliche REST\-Endpunkte verfügbar machen möchten, verwenden Sie WCF und <xref:System.ServiceModel.WebHttpBinding>.  
  
## Siehe auch  
 [Was ist die Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)   
 [Wesentliche Windows Communication Foundation\-Begriffe](../../../docs/framework/wcf/fundamental-concepts.md)   
 [WCF and ASP.NET Web API](../../../docs/framework/wcf/wcf-and-aspnet-web-api.md)