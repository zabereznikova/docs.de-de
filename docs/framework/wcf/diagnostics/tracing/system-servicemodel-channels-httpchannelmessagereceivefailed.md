---
title: "System.ServiceModel.Channels.HttpChannelMessageReceiveFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
Empfangen einer Nachricht über einen HTTP\-Kanal fehlgeschlagen.  
  
## Beschreibung  
 Diese Ablaufverfolgung kann als Warnung oder ein Fehler ausgegeben werden.In beiden Fällen wird die Ablaufverfolgung ausgegeben, wenn für eine eingehende http\-Anforderung kein kompatibler Listener gefunden wird und die HTTP\-Anforderung gelöscht wird.Dies kann der Fall sein, weil das http\-Verb der Anforderung von keinem http\-Listener erkannt wurde oder weil kein Listener die Adresse abgehört hat, an welche die Anforderung gerichtet war.Die Ablaufverfolgung wird als Warnung ausgegeben, wenn es sich um einen selbstgehosteten Dienst handelt, Sie wird als Fehler ausgegeben, wenn der Dienst in IIS gehostet wird.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)