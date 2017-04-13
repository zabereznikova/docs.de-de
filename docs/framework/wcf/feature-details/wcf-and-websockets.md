---
title: "WCF und WebSockets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF und WebSockets
Mit .NET Framework 4.5 wird Unterstützung für WebSockets in Windows Communication Foundation eingeführt.WebSockets ist eine effiziente standardbasierte Technologie, die die bidirektionale Kommunikation über die HTTP\-Standardports 80 und 443 ermöglicht.Die Verwendung der standardmäßigen HTTP\-Ports ermöglicht WebSockets die webbasierte Kommunikation über Vermittler.Um die Kommunikation über einen WebSocket\-Transport zu unterstützen, wurden zwei neue Standardbindungen hinzugefügt.<xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>.WebSockets\-spezifische Einstellungen können im <xref:> System.ServiceModel.Channels.HttpTransportBinding?qualifyHint=False&autoUpgrade=True\-Element über den Zugriff auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A>\-Eigenschaft konfiguriert werden.  
  
## In diesem Abschnitt  
 [Verwenden der NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 Erläutert die <xref:System.ServiceModel.NetHttpBinding> und deren Konfiguration.  
  
 [Vorgehensweise: Erstellen eines WCF\-Diensts, der über WebSockets kommuniziert](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Beschreibt, wie ein WCF\-Dienst erstellt wird, der über WebSockets kommuniziert.  
  
## Referenz  
  
## Verwandte Abschnitte