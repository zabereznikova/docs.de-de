---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: bd6c9124e6346437e2bb35df620e00bad13b60f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258945"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="435a8-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="435a8-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>

<span data-ttu-id="435a8-103">Der Zustandsautomat für eine Teilnehmereintragung ist in den fertigen Zustand eingetreten.</span><span class="sxs-lookup"><span data-stu-id="435a8-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="435a8-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="435a8-104">Description</span></span>  

 <span data-ttu-id="435a8-105">Wird nachverfolgt, wenn eine untergeordnete Teilnehmereintragung die 2pc-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="435a8-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="435a8-106">Das Ergebnis der Eintragung kann "Übermittelt" oder "Abgebrochen" sein.</span><span class="sxs-lookup"><span data-stu-id="435a8-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="435a8-107">Es wird auch nachverfolgt, ob sich ein Teilnehmer während der Vorbereitung für "Schreibgeschützt" entscheidet.</span><span class="sxs-lookup"><span data-stu-id="435a8-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="435a8-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="435a8-108">See also</span></span>

- [<span data-ttu-id="435a8-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="435a8-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="435a8-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="435a8-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="435a8-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="435a8-111">Administration and Diagnostics</span></span>](../index.md)
