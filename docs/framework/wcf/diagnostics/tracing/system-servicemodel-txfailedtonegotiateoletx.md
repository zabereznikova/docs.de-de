---
title: "System.ServiceModel.TxFailedToNegotiateOleTx | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.ServiceModel.TxFailedToNegotiateOleTx
Die OleTransactions\-Protokollverhandlung wurde nicht für den angegebenen Koordinationskontext abgeschlossen.  
  
## Beschreibung  
 Verfolgt nach, wann eine eingehende Transaktion mit OleTx\-Informationen die angehängten OleTx\-Informationen nicht verwenden kann und stattdessen wieder zur Nutzung des WS\-AT zurückkehrt.  
  
## Problembehandlung  
 Gibt ein potenzielles Problem mit MSDTC RPC\-Kommunikation zwischen den Computern an.Wenn viele dieser Ablaufverfolgungen im Protokoll angezeigt werden, kann sich eine drastische Abnahme der Leistung ergeben.Wenn OleTx nicht gewünscht wird, legen Sie `OleTxUpgradeEnabled` in der WS\-AT\-Registrierungskonfiguration auf 0 \(null\) fest.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)