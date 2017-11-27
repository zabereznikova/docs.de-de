---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c9a456e668560cb2172de80295b731a6103aa7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="f0013-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="f0013-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="f0013-103">Der Zustandsautomat für eine Koordinatoreintragung wechselte in den abgeschlossenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="f0013-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f0013-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0013-104">Description</span></span>  
 <span data-ttu-id="f0013-105">Aufgezeichnet, wenn der lokale Transaktions-Manager davon ausgeht, dass eine übergeordnete Koordinatoreintragung die 2PC-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="f0013-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="f0013-106">Das Ergebnis der Eintragung kann "Übermittelt", "Abgebrochen" oder "Vergessen" sein.</span><span class="sxs-lookup"><span data-stu-id="f0013-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="f0013-107">Eine Aufzeichnung erfolgt auch, wenn der lokale Transaktions-Manager während der Vorbereitungsphase ReadOnly angibt.</span><span class="sxs-lookup"><span data-stu-id="f0013-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0013-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0013-108">See Also</span></span>  
 [<span data-ttu-id="f0013-109">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f0013-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f0013-110">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="f0013-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f0013-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="f0013-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
