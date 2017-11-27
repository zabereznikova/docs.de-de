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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1992a209bb58c0a0d6f181eb2f1ec546d50372ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="84f16-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="84f16-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="84f16-103">Der WS-AT-Protokolldienst hat während des Wartens auf eine Antwort auf eine ausgehende Nachricht von einem flüchtigen Teilnehmer das Zeitlimit überschritten.</span><span class="sxs-lookup"><span data-stu-id="84f16-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="84f16-104">Das Transaktionsergebnis ist möglicherweise zweifelhaft, wenn der Teilnehmer zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="84f16-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="84f16-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84f16-105">Description</span></span>  
 <span data-ttu-id="84f16-106">Wird nachverfolgt, wenn ein flüchtiger Teilnehmer sich zu Commit oder Abbruch entschieden hat, aber nicht innerhalb eines vorgegebenen Zeitraums auf eine Commit- oder Rollback-Anforderung geantwortet hat.</span><span class="sxs-lookup"><span data-stu-id="84f16-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="84f16-107">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="84f16-107">Troubleshooting</span></span>  
 <span data-ttu-id="84f16-108">Stellen Sie sicher, dass alle flüchtigen Teilnehmer fähig sind, innerhalb des gegebenen Zeitraums zu antworten.</span><span class="sxs-lookup"><span data-stu-id="84f16-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="84f16-109">Der Standardzeitraum beträgt 180 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="84f16-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="84f16-110">Wenn dies ungenügend ist, erhöhen Sie die `VolatileOutcomeDelay`-Zeitgeberrichtlinie für WS-AT.</span><span class="sxs-lookup"><span data-stu-id="84f16-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f16-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84f16-111">See Also</span></span>  
 [<span data-ttu-id="84f16-112">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="84f16-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="84f16-113">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="84f16-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="84f16-114">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="84f16-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
