---
title: "Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
Der Zustandsautomat für eine Teilnehmereintragung ist in den fertigen Zustand eingetreten.  
  
## Beschreibung  
 Wird nachverfolgt, wenn eine untergeordnete Teilnehmereintragung die 2pc\-Verarbeitung abgeschlossen hat.Das Ergebnis der Eintragung kann "Übermittelt" oder "Abgebrochen" sein.Es wird auch nachverfolgt, ob sich ein Teilnehmer während der Vorbereitung für "Schreibgeschützt" entscheidet.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)