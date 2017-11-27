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
ms.openlocfilehash: 8beea344d233794ddc36d7fc53db1c01be84399f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="b6607-102">Ein anderes Ereignisprotokoll hat bereits eine Quelle mit diesem Namen registriert.</span><span class="sxs-lookup"><span data-stu-id="b6607-102">Another event log has already registered a source with this name</span></span>
<span data-ttu-id="b6607-103">Es wurde versucht, einen Eintrag in ein Ereignisprotokoll schreiben, bei dem die angegebene Quelle für ein anderes Ereignisprotokoll registriert ist.</span><span class="sxs-lookup"><span data-stu-id="b6607-103">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="b6607-104">Sie müssen die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft Ihrer <xref:System.Diagnostics.EventLog> -Komponenteninstanz festlegen, bevor die Komponente einen Eintrag in ein Protokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="b6607-104">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="b6607-105">In diesem Fall überprüft das System, ob die angegebene Quelle mit dem Ereignisprotokoll registriert ist, in das die Komponente schreibt. Bei Bedarf wird dann <xref:System.Diagnostics.EventLog.CreateEventSource%2A> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b6607-105">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b6607-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b6607-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b6607-107">Entfernen Sie die Zuordnung der Quelle zum ersten Protokoll mithilfe der <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> - oder <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="b6607-107">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2.  <span data-ttu-id="b6607-108">Registrieren Sie die Quelle für das neue Protokoll.</span><span class="sxs-lookup"><span data-stu-id="b6607-108">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6607-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6607-109">See Also</span></span>  
 [<span data-ttu-id="b6607-110">My.Application.Log-Objekt</span><span class="sxs-lookup"><span data-stu-id="b6607-110">My.Application.Log Object</span></span>](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [<span data-ttu-id="b6607-111">Vorgehensweise: entfernen eine Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b6607-111">How to: Remove an Event Source</span></span>](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)  
 [<span data-ttu-id="b6607-112">Vorgehensweise: Hinzufügen von Ihrer Anwendung als Quelle für Einträge im Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="b6607-112">How to: Add Your Application as a Source of Event Log Entries</span></span>](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)
