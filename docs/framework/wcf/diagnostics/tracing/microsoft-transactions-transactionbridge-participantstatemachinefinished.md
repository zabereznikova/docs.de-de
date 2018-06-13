---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 85b8cc4e5044cc7c87ea784e09c160cc527dddaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473531"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="4744b-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="4744b-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="4744b-103">Der Zustandsautomat für eine Teilnehmereintragung ist in den fertigen Zustand eingetreten.</span><span class="sxs-lookup"><span data-stu-id="4744b-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4744b-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4744b-104">Description</span></span>  
 <span data-ttu-id="4744b-105">Wird nachverfolgt, wenn eine untergeordnete Teilnehmereintragung die 2pc-Verarbeitung abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="4744b-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="4744b-106">Das Ergebnis der Eintragung kann "Übermittelt" oder "Abgebrochen" sein.</span><span class="sxs-lookup"><span data-stu-id="4744b-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="4744b-107">Es wird auch nachverfolgt, ob sich ein Teilnehmer während der Vorbereitung für "Schreibgeschützt" entscheidet.</span><span class="sxs-lookup"><span data-stu-id="4744b-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4744b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4744b-108">See Also</span></span>  
 [<span data-ttu-id="4744b-109">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4744b-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="4744b-110">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="4744b-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="4744b-111">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="4744b-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
