---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 562399c1d45dc73c7c88bd165e9f95ee1bcfa19d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125080"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a>System.ServiceModel.Channels.MsmqPoisonMessageRejected
Nicht verarbeitbare Nachrichten wurden abgelehnt.  
  
## <a name="description"></a>Beschreibung  
 Die Ablaufverfolgung gibt an, dass eine nicht verarbeitbare Nachricht erkannt und anschließend abgelehnt wurde. Dies geschieht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist. Eine abgelehnte Nachricht wird zurück an des Absenders des übermittelt [Dead Letter-Warteschlange](https://go.microsoft.com/fwlink/?LinkId=99544).  
  
 Finden Sie unter [Behandlung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkId=99546) Weitere Einzelheiten, wann Nachrichten beschädigt werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren. Finden Sie unter [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) Weitere Einzelheiten, was eine abgelehnte Nachricht in MSMQ bedeutet.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Handhabung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkId=99546)
- [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548)
