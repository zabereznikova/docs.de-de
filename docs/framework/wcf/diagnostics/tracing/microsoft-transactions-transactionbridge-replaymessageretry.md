---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 162452d5d12859571d78ef19cf1d838953ee7acd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596206"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a>Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
Einem nicht reagierenden Koordinator wurde eine Wiederholungsaufforderung für eine Wiederholungsnachricht geschickt.  
  
## <a name="description"></a>BESCHREIBUNG  
 Wird nachverfolgt, wenn vom lokalen Transaktions-Manager eine Wiederholungsnachricht an einen übergeordneten Koordinator gesendet werden musste, da binnen eines festgelegten Zeitraums keine Antwort erhalten wurde.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Untersuchen Sie mögliche Netzwerk- oder Produktprobleme, aufgrund derer die Antwort möglicherweise nicht rechtzeitig eingeht.  Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten. Beide Probleme haben eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
