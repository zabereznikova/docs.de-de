---
title: "Microsoft.Transactions.TransactionBridge.CommitMessageRetry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.CommitMessageRetry
Einem nicht reagierenden Koordinator wurde eine Wiederholungsaufforderung für eine Commit\-Nachricht geschickt.  
  
## Beschreibung  
 Verfolgt nach, ob vom lokalen Transaktions\-Manager eine Commit\-Nachricht an einen übergeordneten Koordinator gesendet werden musste, da binnen eines festgelegten Zeitraums keine Antwort erhalten wurde.  
  
## Problembehandlung  
 Untersuchen Sie mögliche Netzwerk\- oder Produktprobleme, aufgrund derer die Antwort möglicherweise nicht rechtzeitig eingeht.Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten.Beide Probleme haben eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)