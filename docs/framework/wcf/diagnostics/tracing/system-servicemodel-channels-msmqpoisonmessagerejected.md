---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28924f04dc83387f49c2369c2598c028f9b8d4bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a>System.ServiceModel.Channels.MsmqPoisonMessageRejected
Nicht verarbeitbare Nachrichten wurden abgelehnt.  
  
## <a name="description"></a>Beschreibung  
 Die Ablaufverfolgung gibt an, dass eine nicht verarbeitbare Nachricht erkannt und anschließend abgelehnt wurde. Dies geschieht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist. Eine abgelehnte Nachricht wird an des Absenders übermittelt [Dead Letter-Warteschlange](http://go.microsoft.com/fwlink/?LinkId=99544).  
  
 Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkId=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren. Finden Sie unter [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) Weitere Informationen zur Bedeutung der einer abgelehnten Nachricht in MSMQ.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Handhabung beschädigter Nachrichten](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)
