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
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="61099-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="61099-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="61099-103">Der WS-AT-Protokolldienst hat während des Wartens auf eine Antwort auf eine ausgehende Nachricht von einem flüchtigen Teilnehmer das Zeitlimit überschritten.</span><span class="sxs-lookup"><span data-stu-id="61099-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="61099-104">Das Transaktionsergebnis ist möglicherweise zweifelhaft, wenn der Teilnehmer zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="61099-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="61099-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="61099-105">Description</span></span>  
 <span data-ttu-id="61099-106">Wird nachverfolgt, wenn ein flüchtiger Teilnehmer sich zu Commit oder Abbruch entschieden hat, aber nicht innerhalb eines vorgegebenen Zeitraums auf eine Commit- oder Rollback-Anforderung geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="61099-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="61099-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="61099-107">Troubleshooting</span></span>  
 <span data-ttu-id="61099-108">Stellen Sie sicher, dass alle flüchtigen Teilnehmer fähig sind, innerhalb des gegebenen Zeitraums zu antworten.</span><span class="sxs-lookup"><span data-stu-id="61099-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="61099-109">Der Standardzeitraum beträgt 180 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="61099-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="61099-110">Wenn dies ungenügend ist, erhöhen Sie die `VolatileOutcomeDelay`-Timerrichtlinie für WS-AT.</span><span class="sxs-lookup"><span data-stu-id="61099-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61099-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61099-111">See also</span></span>

- [<span data-ttu-id="61099-112">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="61099-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="61099-113">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="61099-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="61099-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="61099-114">Administration and Diagnostics</span></span>](../index.md)
