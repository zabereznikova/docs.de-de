---
title: "Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
Der Zustandsautomat für eine Koordinatoreintragung wechselte in den abgeschlossenen Zustand.  
  
## Beschreibung  
 Aufgezeichnet, wenn der lokale Transaktions\-Manager davon ausgeht, dass eine übergeordnete Koordinatoreintragung die 2PC\-Verarbeitung abgeschlossen hat.Das Ergebnis der Eintragung kann "Übermittelt", "Abgebrochen" oder "Vergessen" sein.Eine Aufzeichnung erfolgt auch, wenn der lokale Transaktions\-Manager während der Vorbereitungsphase ReadOnly angibt.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)