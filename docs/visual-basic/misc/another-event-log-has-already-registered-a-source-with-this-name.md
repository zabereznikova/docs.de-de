---
title: Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f04afd5d061a44f572d95abfb0173ad6fa2ac27
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="15296-102">Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.</span><span class="sxs-lookup"><span data-stu-id="15296-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="15296-103">Es wurde versucht, einen Eintrag in ein Ereignisprotokoll schreiben, bei dem die angegebene Quelle für ein anderes Ereignisprotokoll registriert ist.</span><span class="sxs-lookup"><span data-stu-id="15296-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="15296-104">Sie müssen die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft Ihrer <xref:System.Diagnostics.EventLog> -Komponenteninstanz festlegen, bevor die Komponente einen Eintrag in ein Protokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="15296-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="15296-105">In diesem Fall überprüft das System, ob die angegebene Quelle mit dem Ereignisprotokoll registriert ist, in das die Komponente schreibt. Bei Bedarf wird dann <xref:System.Diagnostics.EventLog.CreateEventSource%2A> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="15296-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="15296-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="15296-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="15296-107">Entfernen Sie die Zuordnung der Quelle zum ersten Protokoll mithilfe der <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> - oder <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="15296-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2.  <span data-ttu-id="15296-108">Registrieren Sie die Quelle für das neue Protokoll.</span><span class="sxs-lookup"><span data-stu-id="15296-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15296-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15296-109">See Also</span></span>  
 [<span data-ttu-id="15296-110">Wohin "My.Application.log"</span><span class="sxs-lookup"><span data-stu-id="15296-110">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  

