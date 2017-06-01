---
title: "System.ServiceModel.Channels.MsmqMessageRejected | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMessageRejected
MSMQ hat die Nachricht abgelehnt.  
  
## Beschreibung  
 Diese Ablaufverfolgung gibt an, dass eine MSMQ\-Nachricht abgelehnt wurde.  
  
 MSMQ\-Nachrichten können abgelehnt werden, wenn [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] \(entweder in Verbindung mit NetMsmqBinding oder mit MsmqIntegrationBinding verwendet\) sie nicht verarbeiten kann.Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.Eine beschädigte Nachricht wird abgelehnt, wenn die `ReceiveErrorHandling`\-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist.Eine abgelehnte Nachricht wird zurück an die [Warteschlange für unzustellbare Nachrichten](http://go.microsoft.com/fwlink/?LinkID=99544) \(Seite möglicherweise auf Englisch\) des Absenders gesendet.  
  
 Weitere Informationen darüber, wann Nachrichten beschädigt werden und wie Sie den Dienst konfigurieren, damit sie richtig verarbeitet werden, finden Sie unter [Behandlung nicht verarbeitbarer Nachrichten](http://go.microsoft.com/fwlink/?LinkID=99546) \(Seite möglicherweise auf Englisch\).  
  
 Weitere Informationen darüber, was eine abgelehnte Nachricht in MSMQ bedeutet, finden Sie unter [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) \(Seite möglicherweise auf Englisch\).  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [Behandlung nicht verarbeitbarer Nachrichten](http://go.microsoft.com/fwlink/?LinkID=99546)   
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)