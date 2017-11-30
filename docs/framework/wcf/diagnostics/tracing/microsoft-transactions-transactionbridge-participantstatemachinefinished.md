---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 53ac142c8c7d8004020210ffb3c0dcb2355a5b61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="6a07c-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="6a07c-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="6a07c-103">Der Zustandsautomat für eine Teilnehmereintragung ist in den fertigen Zustand eingetreten.</span><span class="sxs-lookup"><span data-stu-id="6a07c-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6a07c-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a07c-104">Description</span></span>  
 <span data-ttu-id="6a07c-105">Wird nachverfolgt, wenn eine untergeordnete Teilnehmereintragung die 2pc-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="6a07c-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="6a07c-106">Das Ergebnis der Eintragung kann "Übermittelt" oder "Abgebrochen" sein.</span><span class="sxs-lookup"><span data-stu-id="6a07c-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="6a07c-107">Es wird auch nachverfolgt, ob sich ein Teilnehmer während der Vorbereitung für "Schreibgeschützt" entscheidet.</span><span class="sxs-lookup"><span data-stu-id="6a07c-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a07c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a07c-108">See Also</span></span>  
 [<span data-ttu-id="6a07c-109">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="6a07c-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="6a07c-110">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="6a07c-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="6a07c-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="6a07c-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
