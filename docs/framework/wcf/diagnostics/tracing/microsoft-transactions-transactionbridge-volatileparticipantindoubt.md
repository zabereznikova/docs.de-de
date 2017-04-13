---
title: "Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
Der WS\-AT\-Protokolldienst hat eine Prepared\- oder eine Replay\-Nachricht von einem nicht erkannten flüchtigen Teilnehmer empfangen.Dem Teilnehmer wurde ein Fehler zurückgegeben, der aussagt, dass das Ergebnis der Transaktion zweifelhaft ist.  
  
## Beschreibung  
 Verfolgt nach, wann der lokale Transaction Manager eine Prepared\- oder Replay\-Nachricht von einer flüchtigen Eintragung erhält, die er bereits vergessen hat.  
  
## Problembehandlung  
 Untersuchen Sie die potenziellen Ursachen von verspätet ankommenden Nachrichten vom flüchtigen Teilnehmer.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)