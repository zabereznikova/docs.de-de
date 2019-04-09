---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: bffaed4976d82202eaea9ce50f6d389548fdabfd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144825"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a>Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
Der Zustandsautomat für eine Koordinatoreintragung wechselte in den abgeschlossenen Zustand.  
  
## <a name="description"></a>Beschreibung  
 Aufgezeichnet, wenn der lokale Transaktions-Manager davon ausgeht, dass eine übergeordnete Koordinatoreintragung die 2PC-Verarbeitung abgeschlossen hat. Das Ergebnis der Eintragung kann "Übermittelt", "Abgebrochen" oder "Vergessen" sein. Eine Aufzeichnung erfolgt auch, wenn der lokale Transaktions-Manager während der Vorbereitungsphase ReadOnly angibt.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
