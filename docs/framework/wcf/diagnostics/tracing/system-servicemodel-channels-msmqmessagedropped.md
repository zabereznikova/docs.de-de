---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 07bef8b391a03f2c011e1d1a7c7fb4fad908e022
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46485417"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ hat die Nachricht verworfen.  
  
## <a name="description"></a>Beschreibung  
 Die Ablaufverfolgung gibt an, dass eine MSMQ-Nachricht gelöscht wurde. MSMQ-Nachrichten können gelöscht werden, wenn Windows Communication Foundation (WCF) (mit NetMsmqBinding oder MsmqIntegrationBinding verwendet) nicht verarbeiten kann. Solche Nachrichten werden als beschädigte Nachrichten bezeichnet.  
  
 Eine beschädigte Nachricht wird gelöscht, wenn die `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding auf `Drop` festgelegt ist. Eine gelöschte Nachricht wird aus der Warteschlange entfernt und ist nicht mehr wiederherstellbar.  
  
 Finden Sie unter [Behandlung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkID=99546) Weitere Einzelheiten, wann Nachrichten beschädigt werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [Handhabung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkID=99546)
