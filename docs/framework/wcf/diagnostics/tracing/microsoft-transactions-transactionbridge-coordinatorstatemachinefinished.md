---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: abb6a81d22da3a35c754c5d1485c5d612c9cd1e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473132"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="1e2d1-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="1e2d1-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="1e2d1-103">Der Zustandsautomat für eine Koordinatoreintragung wechselte in den abgeschlossenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1e2d1-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e2d1-104">Description</span></span>  
 <span data-ttu-id="1e2d1-105">Aufgezeichnet, wenn der lokale Transaktions-Manager davon ausgeht, dass eine übergeordnete Koordinatoreintragung die 2PC-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="1e2d1-106">Das Ergebnis der Eintragung kann "Übermittelt", "Abgebrochen" oder "Vergessen" sein.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="1e2d1-107">Eine Aufzeichnung erfolgt auch, wenn der lokale Transaktions-Manager während der Vorbereitungsphase ReadOnly angibt.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e2d1-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e2d1-108">See Also</span></span>  
 [<span data-ttu-id="1e2d1-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="1e2d1-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="1e2d1-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="1e2d1-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="1e2d1-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="1e2d1-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
