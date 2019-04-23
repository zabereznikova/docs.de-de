---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170728"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="d9753-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="d9753-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="d9753-103">Der Zustandsautomat für eine Teilnehmereintragung ist in den fertigen Zustand eingetreten.</span><span class="sxs-lookup"><span data-stu-id="d9753-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d9753-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9753-104">Description</span></span>  
 <span data-ttu-id="d9753-105">Wird nachverfolgt, wenn eine untergeordnete Teilnehmereintragung die 2pc-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="d9753-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="d9753-106">Das Ergebnis der Eintragung kann "Übermittelt" oder "Abgebrochen" sein.</span><span class="sxs-lookup"><span data-stu-id="d9753-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="d9753-107">Es wird auch nachverfolgt, ob sich ein Teilnehmer während der Vorbereitung für "Schreibgeschützt" entscheidet.</span><span class="sxs-lookup"><span data-stu-id="d9753-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9753-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9753-108">See also</span></span>

- [<span data-ttu-id="d9753-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d9753-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d9753-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="d9753-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d9753-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="d9753-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
