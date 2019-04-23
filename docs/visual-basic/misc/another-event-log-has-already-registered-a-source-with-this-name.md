---
title: Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: d932869504b2d8a5f3a948b190e5528bfcfa664f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314671"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="e175f-102">Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.</span><span class="sxs-lookup"><span data-stu-id="e175f-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="e175f-103">Es wurde versucht, einen Eintrag in ein Ereignisprotokoll schreiben, bei dem die angegebene Quelle für ein anderes Ereignisprotokoll registriert ist.</span><span class="sxs-lookup"><span data-stu-id="e175f-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="e175f-104">Sie müssen die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft Ihrer <xref:System.Diagnostics.EventLog> -Komponenteninstanz festlegen, bevor die Komponente einen Eintrag in ein Protokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="e175f-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="e175f-105">In diesem Fall überprüft das System, ob die angegebene Quelle mit dem Ereignisprotokoll registriert ist, in das die Komponente schreibt. Bei Bedarf wird dann <xref:System.Diagnostics.EventLog.CreateEventSource%2A> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e175f-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e175f-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e175f-106">To correct this error</span></span>  
  
1. <span data-ttu-id="e175f-107">Entfernen Sie die Zuordnung der Quelle zum ersten Protokoll mithilfe der <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> - oder <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="e175f-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2. <span data-ttu-id="e175f-108">Registrieren Sie die Quelle für das neue Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e175f-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e175f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e175f-109">See also</span></span>

- [<span data-ttu-id="e175f-110">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="e175f-110">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
