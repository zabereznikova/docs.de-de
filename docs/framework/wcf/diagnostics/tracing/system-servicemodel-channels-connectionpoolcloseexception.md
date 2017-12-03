---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d4e8eee0ebc3702445b41d1f81742d18dfa98d44
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException
Eine Ausnahme ist aufgetreten, während die Verbindungen in diesem Verbindungspool geschlossen wurden.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung auf Fehlerebene gibt an, dass der Fehler aufgetreten ist, während die Verbindungspools geschlossen wurden, die von der Funktion für Verbindungspooling von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] verwendet werden. Eine mögliche Ursache dafür ist das fehlgeschlagene Schließen einer gepoolten Verbindung oder einer Gruppe gepoolter Verbindungen innerhalb des CloseTimeout. Wenn diese Ausnahme ausgelöst wird, werden die restlichen nicht geschlossenen Verbindungen innerhalb dieses Pools abgebrochen. Nicht geschlossene Verbindungen innerhalb anderer Pools werden aufgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung beheben](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
