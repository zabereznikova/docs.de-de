---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b433e5e3c0a961098f82ad601d127290b1d6bd73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ hat die Nachricht abgelehnt.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht abgelehnt wurde.  
  
 MSMQ-Nachrichten können abgelehnt werden, wenn [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (entweder in Verbindung mit NetMsmqBinding oder mit MsmqIntegrationBinding verwendet) sie nicht verarbeiten kann. Solche Nachrichten werden als beschädigte Nachrichten bezeichnet. Eine beschädigte Nachricht wird abgelehnt, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist. Eine abgelehnte Nachricht wird an des Absenders übermittelt [Dead Letter-Warteschlange](http://go.microsoft.com/fwlink/?LinkID=99544).  
  
 Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkID=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.  
  
 Finden Sie unter [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) Weitere Informationen zur Bedeutung der einer abgelehnten Nachricht in MSMQ.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Handhabung beschädigter Nachrichten](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)
