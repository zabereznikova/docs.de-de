---
title: "System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
Nachricht kann nicht verschoben oder gelöscht werden.  
  
## Beschreibung  
 Die Ablaufverfolgung gibt an, dass beim Versuch, eine MSMQ\-Nachricht zu verschieben, zu löschen oder abzulehnen ein Fehler aufgetreten ist.  
  
 MSMQ\-Nachrichten werden von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] verwendet \(wenn entweder mit der NetMsmqBinding oder der MsmqIntegrationBinding benutzt\). Diese Ablaufverfolgung ist bezieht sich auf den ausgewählten Wert der `ReceiveErrorHandling`\-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding.  
  
 Diese Ablaufverfolgung weist nicht auf einen Fehler des gesamten Systems hin.  Sie gibt jedoch an, dass die ausgewählte Disposition für nicht verarbeitbare Nachrichten für eine Nachricht fehlgeschlagen ist.  Weitere Informationen darüber, wann Nachrichten beschädigt werden und wie Sie den Dienst konfigurieren, damit sie richtig verarbeitet werden, finden Sie unter [Behandlung nicht verarbeitbarer Nachrichten](http://go.microsoft.com/fwlink/?LinkID=99546).  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)