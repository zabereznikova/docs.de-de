---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170728"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="daf91-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="daf91-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="daf91-103">Der Zustandsautomat für eine Teilnehmereintragung ist in den fertigen Zustand eingetreten.</span><span class="sxs-lookup"><span data-stu-id="daf91-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="daf91-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="daf91-104">Description</span></span>  
 <span data-ttu-id="daf91-105">Wird nachverfolgt, wenn eine untergeordnete Teilnehmereintragung die 2pc-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="daf91-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="daf91-106">Das Ergebnis der Eintragung kann "Übermittelt" oder "Abgebrochen" sein.</span><span class="sxs-lookup"><span data-stu-id="daf91-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="daf91-107">Es wird auch nachverfolgt, ob sich ein Teilnehmer während der Vorbereitung für "Schreibgeschützt" entscheidet.</span><span class="sxs-lookup"><span data-stu-id="daf91-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf91-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daf91-108">See also</span></span>

- [<span data-ttu-id="daf91-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="daf91-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="daf91-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="daf91-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="daf91-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="daf91-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
