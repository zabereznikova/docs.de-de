---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b8199398e4e0bfe8ad42f6c8ba8adb11e883236e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="1742e-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="1742e-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="1742e-103">Eine Prepare-Nachrichtenwiederholung wurde an einen Teilnehmer gesendet, der nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="1742e-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1742e-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1742e-104">Description</span></span>  
 <span data-ttu-id="1742e-105">Wird nachverfolgt, wenn vom lokalen Transaktions-Manager eine Prepare-Nachricht an einen untergeordneten Teilnehmer gesendet werden musste, da binnen eines festgelegten Zeitraums keine Antwort erhalten wurde.</span><span class="sxs-lookup"><span data-stu-id="1742e-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1742e-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1742e-106">Troubleshooting</span></span>  
 <span data-ttu-id="1742e-107">Untersuchen Sie mögliche Netzwerk- oder Produktprobleme, aufgrund derer die Antwort möglicherweise nicht rechtzeitig eingeht.</span><span class="sxs-lookup"><span data-stu-id="1742e-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="1742e-108">Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten.</span><span class="sxs-lookup"><span data-stu-id="1742e-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="1742e-109">Beide Probleme können eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="1742e-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1742e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1742e-110">See Also</span></span>  
 [<span data-ttu-id="1742e-111">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="1742e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="1742e-112">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="1742e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="1742e-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="1742e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
