---
title: "Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Der WS\-AT\-Protokolldienst hat eine Replay\-Nachricht von einem permanenten Teilnehmer empfangen, der nicht auf die Prepare\-Nachricht geantwortet hat.Infolgedessen wurde die Transaktion abgebrochen.  
  
## Beschreibung  
 Aufgezeichnet, wenn eine Replay\-Nachricht empfangen wird, während ein permanenter Teilnehmer sich immer noch in der Vorbereitung befindet.Dies ist eine ungültige Nachricht für diesen Zustand, und die Transaktion wird abgebrochen.  
  
## Problembehandlung  
 Dieser Fehler kann darauf hinweisen, dass ein permanenter Teilnehmer \(einschließlich untergeordneter Transaktions\-Manager\) nach einem Fehler wiederhergestellt wurde, das Transaktionsergebnis jedoch unsicher ist und der Zustand daher angefordert wird.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)