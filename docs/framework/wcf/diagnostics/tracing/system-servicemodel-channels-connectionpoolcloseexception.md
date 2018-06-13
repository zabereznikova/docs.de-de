---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: f3474fc1bb0ed0d11df6289ed6470447d815f5ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475750"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a>System.ServiceModel.Channels.ConnectionPoolCloseException
Eine Ausnahme ist aufgetreten, während die Verbindungen in diesem Verbindungspool geschlossen wurden.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung auf Fehlerebene gibt an, dass ein Fehler aufgetreten ist, während die Verbindungspools geschlossen von Windows Communication Foundation (WCF) Verbindungspooling-Funktion verwendet. Eine mögliche Ursache dafür ist das fehlgeschlagene Schließen einer gepoolten Verbindung oder einer Gruppe gepoolter Verbindungen innerhalb des CloseTimeout. Wenn diese Ausnahme ausgelöst wird, werden die restlichen nicht geschlossenen Verbindungen innerhalb dieses Pools abgebrochen. Nicht geschlossene Verbindungen innerhalb anderer Pools werden aufgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
