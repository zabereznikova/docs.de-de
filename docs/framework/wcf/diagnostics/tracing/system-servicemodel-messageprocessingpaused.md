---
title: "System.ServiceModel.MessageProcessingPaused | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.MessageProcessingPaused
System.ServiceModel.MessageProcessingPaused  
  
## Beschreibung  
 Zwischen den Threads wurde umgeschaltet, während sie eine Nachricht verarbeitet haben.  
  
 Nachrichtenverarbeitung kann aus den folgenden Gründen angehalten werden:  
  
-   ConcurrencyMode ist einzeln oder wiedereintrittsfähig, und der Dienst verarbeitet eine andere Nachricht.  
  
-   Transaktion wird aktiviert, und der Dienst verarbeitet eine andere Transaktion.  
  
-   Der Synchronisierungskontext ist nicht aktuell.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)