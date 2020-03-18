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
ms.openlocfilehash: 2a9ce8bc2d2edd09ef79c060b9bb173d4d054d02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121318"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="dad96-102">Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="dad96-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="dad96-103">Typen in .NET Framework- und Klassenbibliotheken von Drittanbietern können Methoden bereitstellen, die einer Anwendung während der Durchführung asynchroner Vorgänge die weitere Ausführung in anderen Threads als dem Hauptanwendungsthread ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="dad96-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="dad96-104">In den folgenden Abschnitten werden Codebeispiele beschrieben und angegeben, die die verschiedenen Möglichkeiten für den Aufruf asynchroner Methoden mit dem Entwurfsmuster <xref:System.IAsyncResult> veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="dad96-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="dad96-105">[Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)</span><span class="sxs-lookup"><span data-stu-id="dad96-105">[Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="dad96-106">[Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)</span><span class="sxs-lookup"><span data-stu-id="dad96-106">[Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="dad96-107">[Abrufen des Status eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)</span><span class="sxs-lookup"><span data-stu-id="dad96-107">[Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="dad96-108">[Verwenden eines AsyncCallback-Delegaten zum Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)</span><span class="sxs-lookup"><span data-stu-id="dad96-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad96-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dad96-109">See also</span></span>

- [<span data-ttu-id="dad96-110">Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))</span><span class="sxs-lookup"><span data-stu-id="dad96-110">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="dad96-111">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="dad96-111">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
