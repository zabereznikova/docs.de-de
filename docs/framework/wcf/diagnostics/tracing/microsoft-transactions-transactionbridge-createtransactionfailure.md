---
title: "Microsoft.Transactions.TransactionBridge.CreateTransactionFailure | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
Es konnte keine Transaktion erstellt werden.  
  
## Beschreibung  
 Diese Ablaufverfolgung wird generiert, wenn MSDTC keine Transaktion erstellen kann.  Dies kann aufgrund von unzureichenden Ressourcen, zu wenig Protokollspeicherplatz oder anderen Fehlern vorkommen.  
  
## Problembehandlung  
 Überprüfen Sie die Statuszeichenfolge innerhalb der Ablaufverfolgungsnachricht, um zu bestimmen, ob ein ausführbares Element vorhanden ist.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)