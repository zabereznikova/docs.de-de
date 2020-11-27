---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 28b83b293570adf3b1cfdc15c77afd0f0cf768eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259024"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="22ba5-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="22ba5-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>

<span data-ttu-id="22ba5-103">Einem nicht reagierenden Koordinator wurde eine Wiederholungsaufforderung für eine Commit-Nachricht geschickt.</span><span class="sxs-lookup"><span data-stu-id="22ba5-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="22ba5-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="22ba5-104">Description</span></span>  

 <span data-ttu-id="22ba5-105">Verfolgt nach, ob vom lokalen Transaktions-Manager eine Commit-Nachricht an einen übergeordneten Koordinator gesendet werden musste, da binnen eines festgelegten Zeitraums keine Antwort erhalten wurde.</span><span class="sxs-lookup"><span data-stu-id="22ba5-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="22ba5-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="22ba5-106">Troubleshooting</span></span>  

 <span data-ttu-id="22ba5-107">Untersuchen Sie mögliche Netzwerk- oder Produktprobleme, aufgrund derer die Antwort möglicherweise nicht rechtzeitig eingeht.</span><span class="sxs-lookup"><span data-stu-id="22ba5-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="22ba5-108">Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten.</span><span class="sxs-lookup"><span data-stu-id="22ba5-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="22ba5-109">Beide Probleme haben eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge.</span><span class="sxs-lookup"><span data-stu-id="22ba5-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ba5-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22ba5-110">See also</span></span>

- [<span data-ttu-id="22ba5-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="22ba5-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="22ba5-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="22ba5-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="22ba5-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="22ba5-113">Administration and Diagnostics</span></span>](../index.md)
