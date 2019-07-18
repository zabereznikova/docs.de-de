---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486766"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Der WS-AT-Protokolldienst hat eine Replay-Nachricht von einem permanenten Teilnehmer empfangen, der nicht auf die Prepare-Nachricht geantwortet hat. Infolgedessen wurde die Transaktion abgebrochen.  
  
## <a name="description"></a>Beschreibung  
 Aufgezeichnet, wenn eine Replay-Nachricht empfangen wird, während ein permanenter Teilnehmer sich immer noch in der Vorbereitung befindet. Dies ist eine ungültige Nachricht für diesen Zustand, und die Transaktion wird abgebrochen.  
  
## <a name="troubleshooting"></a>Problembehandlung

Dieser Fehler kann angeben, dass ein permanenter Teilnehmer (einschließlich untergeordneter Transaktions-Manager) nach Fehler wiederhergestellt wurde Es ist jedoch das Transaktionsergebnis nicht genau wissen, und fordert den Status.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
