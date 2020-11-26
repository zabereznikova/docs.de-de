---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: bfa279887339f025e4cb7c9c455fd25098684073
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236610"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing

Der WS-AT-Protokolldienst hat eine Replay-Nachricht von einem permanenten Teilnehmer empfangen, der nicht auf die Prepare-Nachricht geantwortet hat. Infolgedessen wurde die Transaktion abgebrochen.  
  
## <a name="description"></a>BESCHREIBUNG  

 Aufgezeichnet, wenn eine Replay-Nachricht empfangen wird, während ein permanenter Teilnehmer sich immer noch in der Vorbereitung befindet. Dies ist eine ungültige Nachricht für diesen Zustand, und die Transaktion wird abgebrochen.  
  
## <a name="troubleshooting"></a>Problembehandlung

Der Empfang dieses Fehlers kann darauf hindeuten, dass ein dauerhafter Teilnehmer (einschließlich untergeordneter transactionmanagers) nach einem Fehler wieder hergestellt wurde. Es ist jedoch nicht sicher, dass das Transaktions Ergebnis nicht sicher ist, und fordert seinen Status an.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
