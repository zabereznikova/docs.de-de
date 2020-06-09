---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: dd2a0b67ec140aa2e6fe1abad8e85c0206abd8ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579020"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a>Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
Der WS-AT-Protokolldienst hat während des Wartens auf eine Antwort auf eine ausgehende Nachricht von einem flüchtigen Teilnehmer das Zeitlimit überschritten. Das Transaktionsergebnis ist möglicherweise zweifelhaft, wenn der Teilnehmer zurückkehrt.  
  
## <a name="description"></a>BESCHREIBUNG  
 Wird nachverfolgt, wenn ein flüchtiger Teilnehmer sich zu Commit oder Abbruch entschieden hat, aber nicht innerhalb eines vorgegebenen Zeitraums auf eine Commit- oder Rollback-Anforderung geantwortet hat.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Stellen Sie sicher, dass alle flüchtigen Teilnehmer fähig sind, innerhalb des gegebenen Zeitraums zu antworten. Der Standardzeitraum beträgt 180 Sekunden.  Wenn dies ungenügend ist, erhöhen Sie die `VolatileOutcomeDelay`-Timerrichtlinie für WS-AT.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
