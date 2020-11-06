---
title: Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 8e11f734410e266aa4c175551e8a3fbf5d9236c9
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888905"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="81cec-102">Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="81cec-102">Calling Asynchronous Methods Using IAsyncResult</span></span>

<span data-ttu-id="81cec-103">Typen in .NET-Bibliotheken und Klassenbibliotheken von Drittanbietern können Methoden bereitstellen, mit denen eine Anwendung weiterhin ausgeführt werden kann, während diese asynchrone Vorgänge in anderen Threads als dem Hauptanwendungsthread ausführt.</span><span class="sxs-lookup"><span data-stu-id="81cec-103">Types in the .NET libraries and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="81cec-104">In den folgenden Abschnitten werden Codebeispiele beschrieben und angegeben, die die verschiedenen Möglichkeiten für den Aufruf asynchroner Methoden mit dem Entwurfsmuster <xref:System.IAsyncResult> veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="81cec-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="81cec-105">[Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](blocking-application-execution-by-ending-an-async-operation.md)</span><span class="sxs-lookup"><span data-stu-id="81cec-105">[Blocking Application Execution by Ending an Async Operation](blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="81cec-106">[Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md)</span><span class="sxs-lookup"><span data-stu-id="81cec-106">[Blocking Application Execution Using an AsyncWaitHandle](blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="81cec-107">[Abrufen des Status eines asynchronen Vorgangs](polling-for-the-status-of-an-asynchronous-operation.md)</span><span class="sxs-lookup"><span data-stu-id="81cec-107">[Polling for the Status of an Asynchronous Operation](polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="81cec-108">[Verwenden eines AsyncCallback-Delegaten zum Beenden eines asynchronen Vorgangs](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)</span><span class="sxs-lookup"><span data-stu-id="81cec-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81cec-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81cec-109">See also</span></span>

- [<span data-ttu-id="81cec-110">Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))</span><span class="sxs-lookup"><span data-stu-id="81cec-110">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="81cec-111">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="81cec-111">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
