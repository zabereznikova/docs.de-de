---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 2d874cebe96b9caa99032e2881e19ec9cd34d047
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259010"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="67e7e-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="67e7e-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>

<span data-ttu-id="67e7e-103">Der Zustandsautomat für eine Koordinatoreintragung wechselte in den abgeschlossenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="67e7e-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="67e7e-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="67e7e-104">Description</span></span>  

 <span data-ttu-id="67e7e-105">Aufgezeichnet, wenn der lokale Transaktions-Manager davon ausgeht, dass eine übergeordnete Koordinatoreintragung die 2PC-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="67e7e-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="67e7e-106">Das Ergebnis der Eintragung kann "Übermittelt", "Abgebrochen" oder "Vergessen" sein.</span><span class="sxs-lookup"><span data-stu-id="67e7e-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="67e7e-107">Eine Aufzeichnung erfolgt auch, wenn der lokale Transaktions-Manager während der Vorbereitungsphase ReadOnly angibt.</span><span class="sxs-lookup"><span data-stu-id="67e7e-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e7e-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67e7e-108">See also</span></span>

- [<span data-ttu-id="67e7e-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="67e7e-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="67e7e-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="67e7e-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="67e7e-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="67e7e-111">Administration and Diagnostics</span></span>](../index.md)
