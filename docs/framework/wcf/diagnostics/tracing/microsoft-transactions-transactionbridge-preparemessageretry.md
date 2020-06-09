---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: 0c53c1617f3aa3c5f16ba16e8ec548e46ce22137
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594334"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="7b550-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="7b550-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="7b550-103">Eine Prepare-Nachrichtenwiederholung wurde an einen Teilnehmer gesendet, der nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="7b550-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7b550-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7b550-104">Description</span></span>  
 <span data-ttu-id="7b550-105">Wird nachverfolgt, wenn vom lokalen Transaktions-Manager eine Prepare-Nachricht an einen untergeordneten Teilnehmer gesendet werden musste, da binnen eines festgelegten Zeitraums keine Antwort erhalten wurde.</span><span class="sxs-lookup"><span data-stu-id="7b550-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="7b550-106">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="7b550-106">Troubleshooting</span></span>  
 <span data-ttu-id="7b550-107">Untersuchen Sie mögliche Netzwerk- oder Produktprobleme, aufgrund derer die Antwort möglicherweise nicht rechtzeitig eingeht.</span><span class="sxs-lookup"><span data-stu-id="7b550-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="7b550-108">Ist eine große Anzahl dieser Nachrichten vorhanden, kann dies auf Infrastrukturprobleme oder auf außergewöhnlich hohe Antwortzeiten hindeuten.</span><span class="sxs-lookup"><span data-stu-id="7b550-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="7b550-109">Beide Probleme können eine drastische Verringerung des Transaktionsdurchsatzes innerhalb des Systems zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="7b550-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b550-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b550-110">See also</span></span>

- [<span data-ttu-id="7b550-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="7b550-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="7b550-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="7b550-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7b550-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="7b550-113">Administration and Diagnostics</span></span>](../index.md)
