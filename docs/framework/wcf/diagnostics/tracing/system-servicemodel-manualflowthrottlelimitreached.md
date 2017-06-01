---
title: "System.ServiceModel.ManualFlowThrottleLimitReached | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# System.ServiceModel.ManualFlowThrottleLimitReached
System.ServiceModel.ManualFlowThrottleLimitReached  
  
## Beschreibung  
 Das System hat den für die ManualFlowControlLimit\-Drosselung festgelegten Grenzwert erreicht.Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit\-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.  
  
 Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 \(null\) reduziert wird.Eine spätere Änderung auf 0 \(null\) wird nicht verfolgt.Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)