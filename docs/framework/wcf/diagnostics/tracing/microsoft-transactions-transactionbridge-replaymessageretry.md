---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 23a0113488b1b1ef0bc161d4134b9325ef81406c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236714"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="4d6da-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="4d6da-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>

<span data-ttu-id="4d6da-103">Einem nicht reagierenden Koordinator wurde eine Wiederholungsaufforderung für eine Wiederholungsnachricht geschickt.</span><span class="sxs-lookup"><span data-stu-id="4d6da-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4d6da-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d6da-104">Description</span></span>  

 <span data-ttu-id="4d6da-105">Wird nachverfolgt, wenn vom lokalen Transaktions-Manager eine Wiederholungsnachricht an einen übergeordneten Koordinator gesendet werden musste, da binnen eines festgelegten Zeitraums keine Antwort erhalten wurde.</span><span class="sxs-lookup"><span data-stu-id="4d6da-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4d6da-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="4d6da-106">Troubleshooting</span></span>  

 <span data-ttu-id="4d6da-107">Untersuchen Sie mögliche Netzwerk- oder Produktprobleme, aufgrund derer die Antwort möglicherweise nicht rechtzeitig eingeht.</span><span class="sxs-lookup"><span data-stu-id="4d6da-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="4d6da-108">Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten.</span><span class="sxs-lookup"><span data-stu-id="4d6da-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="4d6da-109">Beide Probleme haben eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge.</span><span class="sxs-lookup"><span data-stu-id="4d6da-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6da-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d6da-110">See also</span></span>

- [<span data-ttu-id="4d6da-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4d6da-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="4d6da-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="4d6da-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4d6da-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="4d6da-113">Administration and Diagnostics</span></span>](../index.md)
