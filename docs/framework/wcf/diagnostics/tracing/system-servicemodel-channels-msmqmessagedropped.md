---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d4b819b47d682a81bdcc031cc6b09604b072be7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ hat die Nachricht verworfen.  
  
## <a name="description"></a>Beschreibung  
 Die Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht gelöscht wurde. MSMQ-Nachrichten können gelöscht werden, wenn [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (unter Verwendung von NetMsmqBinding oder MsmqIntegrationBinding) sie nicht verarbeiten kann. Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.  
  
 Eine beschädigte Nachricht wird gelöscht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Drop` festgelegt ist. Eine gelöschte Nachricht wird aus der Warteschlange entfernt und ist nicht mehr wiederherstellbar.  
  
 Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkID=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung beheben](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Handhabung beschädigter Nachrichten](http://go.microsoft.com/fwlink/?LinkID=99546)
