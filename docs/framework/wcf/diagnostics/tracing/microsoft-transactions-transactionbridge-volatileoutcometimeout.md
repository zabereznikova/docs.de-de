---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: b64f61d25c3be87019151cbf560becd3384ec182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475630"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="4663f-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="4663f-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="4663f-103">Der WS-AT-Protokolldienst hat während des Wartens auf eine Antwort auf eine ausgehende Nachricht von einem flüchtigen Teilnehmer das Zeitlimit überschritten.</span><span class="sxs-lookup"><span data-stu-id="4663f-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="4663f-104">Das Transaktionsergebnis ist möglicherweise zweifelhaft, wenn der Teilnehmer zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="4663f-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4663f-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4663f-105">Description</span></span>  
 <span data-ttu-id="4663f-106">Wird nachverfolgt, wenn ein flüchtiger Teilnehmer sich zu Commit oder Abbruch entschieden hat, aber nicht innerhalb eines vorgegebenen Zeitraums auf eine Commit- oder Rollback-Anforderung geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="4663f-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4663f-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="4663f-107">Troubleshooting</span></span>  
 <span data-ttu-id="4663f-108">Stellen Sie sicher, dass alle flüchtigen Teilnehmer fähig sind, innerhalb des gegebenen Zeitraums zu antworten.</span><span class="sxs-lookup"><span data-stu-id="4663f-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="4663f-109">Der Standardzeitraum beträgt 180 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="4663f-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="4663f-110">Wenn dies ungenügend ist, erhöhen Sie die `VolatileOutcomeDelay`-Zeitgeberrichtlinie für WS-AT.</span><span class="sxs-lookup"><span data-stu-id="4663f-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4663f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4663f-111">See Also</span></span>  
 [<span data-ttu-id="4663f-112">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4663f-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="4663f-113">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="4663f-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="4663f-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="4663f-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
