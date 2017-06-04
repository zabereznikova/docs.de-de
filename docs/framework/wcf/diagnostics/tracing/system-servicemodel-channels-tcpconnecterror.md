---
title: "System.ServiceModel.Channels.TcpConnectError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 22d93797-072e-405d-a3e0-5c519ddf290b
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# System.ServiceModel.Channels.TcpConnectError
Der TCP\-Verbindungsvorgang ist fehlgeschlagen.  
  
## Beschreibung  
 Diese Ablaufverfolgung auf Warnungsebene gibt an, dass mit einem TCP\-Endpunkt keine Verbindung hergestellt werden konnte.Dies kann geschehen, wenn der Remoteendpunkt nicht über eine gegebene IP\-Adresse bzw. einen IP\-Anschluss antwortet.Diese Ablaufverfolgung kann ignoriert werden, wenn nachfolgende Versuche, mit anderen gültigen IP\-Adressen eine Verbindung herzustellen \(z. B. IPv4\- oder IPv6\-Adressen oder anderen IP\-Adressen, die einen gegebenen Hostnamen darstellen\), erfolgreich sind.Die Ausnahme in dieser Ablaufverfolgung kann weitere Informationen über den Fehler enthalten.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)