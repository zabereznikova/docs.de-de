---
title: "Microsoft.Transactions.TransactionBridge.PreparedMessageRetry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
Einem nicht reagierenden Koordinator wurde eine Prepared\-Nachrichtenwiederholung gesendet.  
  
## Beschreibung  
 Wird nachverfolgt, wenn vom lokalen Transaktions\-Manager eine Prepared\-Nachrichtenwiederholung an einen übergeordneten Koordinator gesendet werden musste, da innerhalb eines festgelegten Zeitraums keine Antwort erhalten wurde.  
  
## Problembehandlung  
 Untersuchen Sie mögliche Netzwerk\- oder Produktprobleme, die verhindern, dass die Antwort nicht rechtzeitig eingeht.Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten.Beide Probleme haben eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)