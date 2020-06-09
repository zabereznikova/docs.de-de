---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 3b9a3703e49c3932f62fcfb6994c9028b074bbe8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594412"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a>Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
Der Zustandsautomat für eine Koordinatoreintragung wechselte in den abgeschlossenen Zustand.  
  
## <a name="description"></a>BESCHREIBUNG  
 Aufgezeichnet, wenn der lokale Transaktions-Manager davon ausgeht, dass eine übergeordnete Koordinatoreintragung die 2PC-Verarbeitung abgeschlossen hat. Das Ergebnis der Eintragung kann "Übermittelt", "Abgebrochen" oder "Vergessen" sein. Eine Aufzeichnung erfolgt auch, wenn der lokale Transaktions-Manager während der Vorbereitungsphase ReadOnly angibt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
