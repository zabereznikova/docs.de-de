---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: d56bbf145c85902d8e5f1fd21f760633121da6da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939217"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
Nachricht kann nicht verschoben oder gelöscht werden.  
  
## <a name="description"></a>Beschreibung  
 Die Ablaufverfolgung gibt an, dass beim Versuch, eine MSMQ-Nachricht zu verschieben, zu löschen oder abzulehnen ein Fehler aufgetreten ist.  
  
 MSMQ-Nachrichten werden von Windows Communication Foundation (WCF) (bei Verwendung mit der NetMsmqBinding oder MsmqIntegrationBinding) verwendet. Diese Ablaufverfolgung bezieht sich auf den ausgewählten Wert, der die `ReceiveErrorHandling` -Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding.  
  
 Diese Ablaufverfolgung weist nicht auf einen Fehler des gesamten Systems hin. Sie gibt jedoch an, dass die ausgewählte Disposition für nicht verarbeitbare Nachrichten für eine Nachricht fehlgeschlagen ist. Finden Sie unter [Behandlung beschädigter Nachrichten](https://go.microsoft.com/fwlink/?LinkID=99546) Weitere Einzelheiten, wann Nachrichten beschädigt werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
