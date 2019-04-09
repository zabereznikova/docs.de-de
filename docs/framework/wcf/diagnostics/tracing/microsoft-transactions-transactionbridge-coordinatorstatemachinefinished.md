---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: bffaed4976d82202eaea9ce50f6d389548fdabfd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144825"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="52929-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="52929-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="52929-103">Der Zustandsautomat für eine Koordinatoreintragung wechselte in den abgeschlossenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="52929-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="52929-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52929-104">Description</span></span>  
 <span data-ttu-id="52929-105">Aufgezeichnet, wenn der lokale Transaktions-Manager davon ausgeht, dass eine übergeordnete Koordinatoreintragung die 2PC-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="52929-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="52929-106">Das Ergebnis der Eintragung kann "Übermittelt", "Abgebrochen" oder "Vergessen" sein.</span><span class="sxs-lookup"><span data-stu-id="52929-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="52929-107">Eine Aufzeichnung erfolgt auch, wenn der lokale Transaktions-Manager während der Vorbereitungsphase ReadOnly angibt.</span><span class="sxs-lookup"><span data-stu-id="52929-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52929-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52929-108">See also</span></span>

- [<span data-ttu-id="52929-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="52929-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="52929-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="52929-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="52929-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="52929-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
