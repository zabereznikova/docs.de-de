---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 339ba8df7e782281fcec962ff6c6f01988122b3a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a>System.ServiceModel.Channels.FailedAcceptFromPool
Fehler beim Versuch, eine gepoolte Verbindung erneut zu verwenden. Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.  
  
## <a name="description"></a>Beschreibung  
 Diese Informationsablaufverfolgung gibt an, dass während des Versuchs, eine zusammengeführte Verbindung wiederzuverwenden, ein Fehler aufgetreten ist Dies kann geschehen, weil die zusammengeführte Verbindung nicht kompatibel, nicht bereit oder noch immer aktiv war. Weitere Versuche, andere zusammengeführte Verbindungen wiederzuverwenden werden innerhalb des gegebenen Timeout unternommen, und eine neue Verbindung wird für den Fall erstellt, dass keine verwendbaren Verbindungen gefunden werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung beheben](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
