---
title: "Der in \"EventLogSource\" angegebene Quellenname ist für ein anderes als in \"EventLogName\" angegebenes Protokoll registriert"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0a100789486dda403f483489e73accbf219374c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="61b4d-102">Der in "EventLogSource" angegebene Quellenname ist für ein anderes als in "EventLogName" angegebenes Protokoll registriert</span><span class="sxs-lookup"><span data-stu-id="61b4d-102">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>
<span data-ttu-id="61b4d-103">`EventLog` versucht, auf eine Quelle zu verweisen, die für ein anderes Protokoll registriert ist.</span><span class="sxs-lookup"><span data-stu-id="61b4d-103">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="61b4d-104">Wenn Sie Einträge in ein Ereignisprotokoll schreiben, müssen Sie die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="61b4d-104">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="61b4d-105">Die <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft registriert die Komponente beim Ereignisprotokoll als gültige Quelle für Einträge.</span><span class="sxs-lookup"><span data-stu-id="61b4d-105">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="61b4d-106">Eine einzelne Quelle kann nur jeweils einem Ereignisprotokoll zugeordnet werden (und somit Einträge jeweils in nur ein Ereignisprotokoll schreiben).</span><span class="sxs-lookup"><span data-stu-id="61b4d-106">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="61b4d-107">Wenn Sie den Versuch unternehmen, einen Eintrag zu schreiben, ohne zuerst die Komponente als gültige Quelle zu registrieren, registriert das System standardmäßig die Quelle automatisch beim Ereignisprotokoll. Dazu wird der Wert der <xref:System.Diagnostics.EventLog.Source%2A> -Eigenschaft als Quellzeichenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="61b4d-107">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="61b4d-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="61b4d-108">To correct this error</span></span>  
  
-   <span data-ttu-id="61b4d-109">Stellen Sie sicher, dass die Quelle beim richtigen Protokoll registriert ist.</span><span class="sxs-lookup"><span data-stu-id="61b4d-109">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="61b4d-110">Verwenden Sie dazu die <xref:System.Diagnostics.EventLog.CreateEventSource%2A> -Methode oder eine ihrer Überladungen, um eine Zeichenfolge anzugeben, die die Komponente beim Ereignisprotokoll eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="61b4d-110">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b4d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61b4d-111">See Also</span></span>  
 [<span data-ttu-id="61b4d-112">Verwalten von Ereignisprotokollen</span><span class="sxs-lookup"><span data-stu-id="61b4d-112">Administering Event Logs</span></span>](http://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [<span data-ttu-id="61b4d-113">-Ereignisprotokollverweise</span><span class="sxs-lookup"><span data-stu-id="61b4d-113">Event Log References</span></span>](http://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [<span data-ttu-id="61b4d-114">Vorgehensweise: Hinzufügen von Ihrer Anwendung als Quelle für Einträge im Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="61b4d-114">How to: Add Your Application as a Source of Event Log Entries</span></span>](http://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [<span data-ttu-id="61b4d-115">Vorgehensweise: entfernen eine Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="61b4d-115">How to: Remove an Event Source</span></span>](http://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
