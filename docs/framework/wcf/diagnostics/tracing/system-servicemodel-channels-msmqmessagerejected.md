---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 87d6e6fc3205fff9bd977ebe77004dfa489098cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681221"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ hat die Nachricht abgelehnt.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht abgelehnt wurde.  
  
 MSMQ-Nachrichten können abgelehnt werden, wenn Windows Communication Foundation (WCF) (mit NetMsmqBinding oder MsmqIntegrationBinding verwendet) nicht verarbeiten kann. Solche Nachrichten werden als beschädigte Nachrichten bezeichnet. Eine beschädigte Nachricht wird abgelehnt, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Reject` festgelegt ist. Eine abgelehnte Nachricht wird zurück an des Absenders des übermittelt [Dead Letter-Warteschlange](https://go.microsoft.com/fwlink/?LinkID=99544).  
  
 Finden Sie unter [Behandlung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkID=99546) Weitere Einzelheiten, wann Nachrichten beschädigt werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.  
  
 Finden Sie unter [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) Weitere Einzelheiten, was eine abgelehnte Nachricht in MSMQ bedeutet.  
  
## <a name="see-also"></a>Siehe auch
- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Handhabung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkID=99546)
- [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548)
