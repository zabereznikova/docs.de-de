---
title: "Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
Der WS\-AT\-Protokolldienst hat während des Wartens auf eine Antwort auf eine ausgehende Nachricht von einem flüchtigen Teilnehmer das Zeitlimit überschritten.Das Transaktionsergebnis ist möglicherweise zweifelhaft, wenn der Teilnehmer zurückkehrt.  
  
## Beschreibung  
 Wird nachverfolgt, wenn ein flüchtiger Teilnehmer sich zu Commit oder Abbruch entschieden hat, aber nicht innerhalb eines vorgegebenen Zeitraums auf eine Commit\- oder Rollback\-Anforderung geantwortet hat.  
  
## Problembehandlung  
 Stellen Sie sicher, dass alle flüchtigen Teilnehmer fähig sind, innerhalb des gegebenen Zeitraums zu antworten.Der Standardzeitraum beträgt 180 Sekunden.Wenn dies ungenügend ist, erhöhen Sie die `VolatileOutcomeDelay`\-Zeitgeberrichtlinie für WS\-AT.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)