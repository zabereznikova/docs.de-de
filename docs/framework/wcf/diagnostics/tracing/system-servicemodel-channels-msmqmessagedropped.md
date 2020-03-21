---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674797"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ hat die Nachricht verworfen.  
  
## <a name="description"></a>Beschreibung  
 Die Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht gelöscht wurde. MSMQ-Nachrichten können gelöscht werden, wenn Windows Communication Foundation (WCF) (wird entweder mit NetMsmqBinding oder MsmqIntegrationBinding verwendet) nicht verarbeiten kann. Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.  
  
 Eine beschädigte Nachricht wird gelöscht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Drop` festgelegt ist. Eine gelöschte Nachricht wird aus der Warteschlange entfernt und ist nicht mehr wiederherstellbar.  
  
 Weitere Informationen dazu, wann Nachrichten zu Gift werden und wie Sie Ihren Dienst so konfigurieren, dass er entsprechend behandelt wird, finden Sie unter [Gift-Nachrichten-Handhabung](../../feature-details/poison-message-handling.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Behandlung nicht verarbeitbarer Nachrichten](../../feature-details/poison-message-handling.md)
