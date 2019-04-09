---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 0c9e79709f5929e1fa123a8d1695ca720046e9e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190872"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="c998b-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="c998b-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="c998b-103">Einem nicht reagierenden Koordinator wurde eine Wiederholungsaufforderung für eine Wiederholungsnachricht geschickt.</span><span class="sxs-lookup"><span data-stu-id="c998b-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c998b-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c998b-104">Description</span></span>  
 <span data-ttu-id="c998b-105">Wird nachverfolgt, wenn vom lokalen Transaktions-Manager eine Wiederholungsnachricht an einen übergeordneten Koordinator gesendet werden musste, da binnen eines festgelegten Zeitraums keine Antwort erhalten wurde.</span><span class="sxs-lookup"><span data-stu-id="c998b-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c998b-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c998b-106">Troubleshooting</span></span>  
 <span data-ttu-id="c998b-107">Untersuchen Sie mögliche Netzwerk- oder Produktprobleme, aufgrund derer die Antwort möglicherweise nicht rechtzeitig eingeht.</span><span class="sxs-lookup"><span data-stu-id="c998b-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="c998b-108">Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten.</span><span class="sxs-lookup"><span data-stu-id="c998b-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="c998b-109">Beide Probleme haben eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge.</span><span class="sxs-lookup"><span data-stu-id="c998b-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c998b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c998b-110">See also</span></span>

- [<span data-ttu-id="c998b-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c998b-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="c998b-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="c998b-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c998b-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="c998b-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
