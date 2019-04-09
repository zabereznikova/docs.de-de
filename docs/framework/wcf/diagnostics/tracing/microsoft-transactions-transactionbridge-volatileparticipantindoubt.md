---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9434f2f902a50a37fb3efee22fd3b18b33af9129
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138969"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a>Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
Der WS-AT-Protokolldienst hat eine Prepared- oder eine Replay-Nachricht von einem nicht erkannten flüchtigen Teilnehmer empfangen. Dem Teilnehmer wurde ein Fehler zurückgegeben, der aussagt, dass das Ergebnis der Transaktion zweifelhaft ist.  
  
## <a name="description"></a>Beschreibung  
 Verfolgt nach, wann der lokale Transaktions-Manager eine Prepared- oder Replay-Nachricht von einer flüchtigen Eintragung erhält, die er bereits vergessen hat.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Untersuchen Sie die potenziellen Ursachen von verspätet ankommenden Nachrichten vom flüchtigen Teilnehmer.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
