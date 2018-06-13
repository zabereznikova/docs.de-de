---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: ba35f948143aff3de575e966aaec87f32f6f14b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473775"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="d4d54-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="d4d54-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="d4d54-103">Einem nicht reagierenden Koordinator wurde eine Prepared-Nachrichtenwiederholung gesendet.</span><span class="sxs-lookup"><span data-stu-id="d4d54-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d4d54-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4d54-104">Description</span></span>  
 <span data-ttu-id="d4d54-105">Wird nachverfolgt, wenn vom lokalen Transaktions-Manager eine Prepared-Nachrichtenwiederholung an einen übergeordneten Koordinator gesendet werden musste, da innerhalb eines festgelegten Zeitraums keine Antwort erhalten wurde.</span><span class="sxs-lookup"><span data-stu-id="d4d54-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d4d54-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d4d54-106">Troubleshooting</span></span>  
 <span data-ttu-id="d4d54-107">Untersuchen Sie mögliche Netzwerk- oder Produktprobleme, aufgrund derer die Antwort möglicherweise nicht rechtzeitig eingeht.</span><span class="sxs-lookup"><span data-stu-id="d4d54-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="d4d54-108">Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten.</span><span class="sxs-lookup"><span data-stu-id="d4d54-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="d4d54-109">Beide Probleme haben eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge.</span><span class="sxs-lookup"><span data-stu-id="d4d54-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d54-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4d54-110">See Also</span></span>  
 [<span data-ttu-id="d4d54-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d4d54-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="d4d54-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="d4d54-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="d4d54-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="d4d54-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
