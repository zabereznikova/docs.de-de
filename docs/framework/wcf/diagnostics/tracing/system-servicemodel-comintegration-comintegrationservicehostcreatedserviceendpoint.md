---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87eac8f0e3949ac47c7bb2915a87043bdc205b8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
Nachricht kann nicht verschoben oder gelöscht werden.  
  
## <a name="description"></a>Beschreibung  
 Die Ablaufverfolgung gibt an, dass beim Versuch, eine MSMQ-Nachricht zu verschieben, zu löschen oder abzulehnen ein Fehler aufgetreten ist.  
  
 MSMQ-Nachrichten werden von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] verwendet (wenn entweder mit der NetMsmqBinding oder der MsmqIntegrationBinding benutzt). Diese Ablaufverfolgung ist bezieht sich auf den ausgewählten Wert der `ReceiveErrorHandling`-Eigenschaft von NetMsmqBinding oder MsmqIntegrationBinding.  
  
 Diese Ablaufverfolgung weist nicht auf einen Fehler des gesamten Systems hin. Sie gibt jedoch an, dass die ausgewählte Disposition für nicht verarbeitbare Nachrichten für eine Nachricht fehlgeschlagen ist. Finden Sie unter [verarbeitbarer Behandlung von](http://go.microsoft.com/fwlink/?LinkID=99546) detaillierte Informationen auf, wenn Nachrichten werden und wie Sie den Dienst, damit sie richtig verarbeitet konfigurieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
