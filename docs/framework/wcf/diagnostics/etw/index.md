---
title: "Analytic Tracing with ETW | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "diagnostics [WCF], analytic tracing"
  - "administration [WCF], analytic tracing"
  - "analytic tracing [WCF]"
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Analytic Tracing with ETW
Mit der analytischen Ablaufverfolgung von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] können Sie während der Ausführung eines [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Diensts die Diagnoseinformationen erfassen.Die Ereignisse der analytischen Ablaufverfolgung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] werden im [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Stapel an wichtigen Punkten ausgegeben, um in einer Produktionsumgebung die Problembehandlung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Diensten zu ermöglichen.Die analytische Ablaufverfolgung für [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienste hat minimale Auswirkungen auf die Leistung eines Produktservers, der [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]\-[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienste hostet. Der Grund dafür ist, dass diese Ereignisse auf sehr effiziente Weise an eine ETW\-Sitzung \(Event Tracing for Windows, Ereignisablaufverfolgung für Windows\) ausgegeben werden.  
  
## In diesem Abschnitt  
 [Übersicht über die analytische Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Erläutert, wie die analytische Ablaufverfolgung von [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] funktioniert.  
  
 [Dynamisches Aktivieren der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Erläutert, wie Sie die Ablaufverfolgung per ETW dynamisch aktivieren und deaktivieren.  
  
 [Konfigurieren der Ablaufverfolgung des Nachrichtenflusses](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Beschreibt, wie die Ablaufverfolgung des Nachrichtenflusses konfiguriert wird.  
  
 [Ereignisverweis der analytischen Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Zeigt eine Tabelle von Ereignis\-IDs mit den dazugehörigen Ereignisebenen, Ereignisnachrichten und Schlüsselwörtern an.  
  
## Siehe auch  
 [WCF\-Dienste und Ereignisablaufverfolgung für Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)   
 [Nachverfolgen von Ereignissen in der Ereignisablaufverfolgung in Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)