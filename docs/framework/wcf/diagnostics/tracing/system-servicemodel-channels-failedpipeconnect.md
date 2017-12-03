---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1386d9ac7f58e4dd692bbca3ca3915bc3fe453f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a>System.ServiceModel.Channels.FailedPipeConnect
Ein Versuch, eine Verbindung mit dem benannten Pipeendpunkt herzustellen, ist fehlgeschlagen. Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung auf Informationsebene gibt an, dass keine Verbindung mit einem Named-Pipe-Endpunkt hergestellt werden konnte. Dies kann vorkommen, wenn der Named-Pipe-Endpunkt nicht gefunden wird oder ausgelastet ist. Der Verbindungsaufbau wird solange in kurzen Zeitintervallen weiter versucht, bis die Verbindung hergestellt wurde oder das mit OpenTimeout festgelegte Zeitlimit überschritten wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung beheben](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
