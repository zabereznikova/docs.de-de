---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.date: 03/30/2017
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
ms.openlocfilehash: 472821d880433cd6a3292838a48bcb0b5bb34c43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152294"
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a>System.ServiceModel.Channels.FailedPipeConnect
Ein Versuch, eine Verbindung mit dem benannten Pipeendpunkt herzustellen, ist fehlgeschlagen. Ein weiterer Versuch wird innerhalb des angegebenen Timeouts unternommen.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung auf Informationsebene gibt an, dass keine Verbindung mit einem Named-Pipe-Endpunkt hergestellt werden konnte. Dies kann vorkommen, wenn der Named-Pipe-Endpunkt nicht gefunden wird oder ausgelastet ist. Der Verbindungsaufbau wird solange in kurzen Zeitintervallen weiter versucht, bis die Verbindung hergestellt wurde oder das mit OpenTimeout festgelegte Zeitlimit überschritten wurde.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
