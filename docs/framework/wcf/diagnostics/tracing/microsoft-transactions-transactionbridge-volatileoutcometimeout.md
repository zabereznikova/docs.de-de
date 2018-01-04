---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1385995165308cb1c2f2e6bd6c8a800a88b7b79e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="988bd-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="988bd-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="988bd-103">Der WS-AT-Protokolldienst hat während des Wartens auf eine Antwort auf eine ausgehende Nachricht von einem flüchtigen Teilnehmer das Zeitlimit überschritten.</span><span class="sxs-lookup"><span data-stu-id="988bd-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="988bd-104">Das Transaktionsergebnis ist möglicherweise zweifelhaft, wenn der Teilnehmer zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="988bd-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="988bd-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="988bd-105">Description</span></span>  
 <span data-ttu-id="988bd-106">Wird nachverfolgt, wenn ein flüchtiger Teilnehmer sich zu Commit oder Abbruch entschieden hat, aber nicht innerhalb eines vorgegebenen Zeitraums auf eine Commit- oder Rollback-Anforderung geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="988bd-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="988bd-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="988bd-107">Troubleshooting</span></span>  
 <span data-ttu-id="988bd-108">Stellen Sie sicher, dass alle flüchtigen Teilnehmer fähig sind, innerhalb des gegebenen Zeitraums zu antworten.</span><span class="sxs-lookup"><span data-stu-id="988bd-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="988bd-109">Der Standardzeitraum beträgt 180 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="988bd-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="988bd-110">Wenn dies ungenügend ist, erhöhen Sie die `VolatileOutcomeDelay`-Zeitgeberrichtlinie für WS-AT.</span><span class="sxs-lookup"><span data-stu-id="988bd-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988bd-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="988bd-111">See Also</span></span>  
 [<span data-ttu-id="988bd-112">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="988bd-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="988bd-113">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="988bd-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="988bd-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="988bd-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
