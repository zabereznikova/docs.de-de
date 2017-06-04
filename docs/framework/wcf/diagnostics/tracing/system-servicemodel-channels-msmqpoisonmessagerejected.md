---
title: "System.ServiceModel.Channels.MsmqPoisonMessageRejected | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqPoisonMessageRejected
Nicht verarbeitbare Nachrichten wurden abgelehnt.  
  
## Beschreibung  
 Die Ablaufverfolgung gibt an, dass eine nicht verarbeitbare Nachricht erkannt und anschließend abgelehnt wurde.Dies geschieht, wenn die `ReceiveErrorHandling`\-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.Die abgelehnte Nachricht wird zurück an die [Warteschlange für unzustellbare Nachrichten](http://go.microsoft.com/fwlink/?LinkId=99544) des Absenders gesendet.  
  
 Weitere Informationen darüber, wann Nachrichten beschädigt werden und wie Sie den Dienst konfigurieren, damit sie richtig verarbeitet werden, finden Sie unter [Behandlung nicht verarbeitbarer Nachrichten](http://go.microsoft.com/fwlink/?LinkId=99546) \(Seite möglicherweise auf Englisch\).Weitere Informationen zur Bedeutung einer abgelehnten Nachricht in MSMQ finden Sie unter [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) \(Seite möglicherweise auf Englisch\).  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Behandlung nicht verarbeitbarer Nachrichten](http://go.microsoft.com/fwlink/?LinkId=99546)   
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)