---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: f79f5703c621951029f3e7f6a36a3d0ebeca58a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33477450"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a>System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
Empfangen einer Nachricht über einen HTTP-Kanal fehlgeschlagen.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung kann als Warnung oder ein Fehler ausgegeben werden. In beiden Fällen wird die Ablaufverfolgung ausgegeben, wenn für eine eingehende http-Anforderung kein kompatibler Listener gefunden wird und die HTTP-Anforderung gelöscht wird. Dies kann der Fall sein, weil das http-Verb der Anforderung von keinem http-Listener erkannt wurde oder weil kein Listener die Adresse abgehört hat, an welche die Anforderung gerichtet war. Die Ablaufverfolgung wird als Warnung ausgegeben, wenn es sich um einen selbstgehosteten Dienst handelt, Sie wird als Fehler ausgegeben, wenn der Dienst in IIS gehostet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
