---
title: 'Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="1db19-102">Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="1db19-102">How to: Handle Exceptions in a PLINQ Query</span></span>
<span data-ttu-id="1db19-103">Im erste Beispiel in diesem Thema wird gezeigt, wie behandelt die <xref:System.AggregateException?displayProperty=nameWithType> , die bei der Ausführung einer PLINQ-Abfrage ausgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="1db19-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="1db19-104">Im zweite Beispiel wird gezeigt, wie Try / Catch-Blöcke in Delegate so nah wie möglich an, in dem die Ausnahme ausgelöst wird, versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1db19-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="1db19-105">Auf diese Weise können Sie sie abfangen, sobald sie auftreten, und die Ausführung der Abfrage möglicherweise weiterhin.</span><span class="sxs-lookup"><span data-stu-id="1db19-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="1db19-106">Wenn Ausnahmen mittels Bubbling wieder an den Verbindungsthread übergeben werden können, ist es möglich, dass eine Abfrage nach dem Auslösen der Ausnahme weiterhin einige Elemente verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="1db19-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>  
  
 <span data-ttu-id="1db19-107">In einigen Fällen Wenn PLINQ, auf die sequenzielle Ausführung ausgewichen und eine Ausnahme auftritt, die Ausnahme möglicherweise werden direkt weitergegeben, und nicht umschlossen eine <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="1db19-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="1db19-108">Darüber hinaus <xref:System.Threading.ThreadAbortException>s immer direkt weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="1db19-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1db19-109">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio wird in der Zeile, die die Ausnahme auslöst und zeigt eine Fehlermeldung an, die besagt, dass "nicht vom Benutzercode behandelten Ausnahme."</span><span class="sxs-lookup"><span data-stu-id="1db19-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="1db19-110">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="1db19-110">This error is benign.</span></span> <span data-ttu-id="1db19-111">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="1db19-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="1db19-112">Zum verhindern, dass Visual Studio den ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="1db19-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="1db19-113">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="1db19-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="1db19-114">Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="1db19-114">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1db19-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1db19-115">Example</span></span>  
 <span data-ttu-id="1db19-116">Dieses Beispiel zeigt, wie Sie den Try / Catch-Blöcke, um den Code zu konzentrieren, die Ausführung der Abfrage zum Abfangen von einem <xref:System.AggregateException?displayProperty=nameWithType>s, die ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="1db19-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 <span data-ttu-id="1db19-117">Die Abfrage kann nicht in diesem Beispiel fortgesetzt, nachdem die Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1db19-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="1db19-118">Nach der Dauer der Anwendungscode, der die Ausnahme abfängt, wurde der PLINQ die Abfrage bereits für alle Threads beendet.</span><span class="sxs-lookup"><span data-stu-id="1db19-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1db19-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1db19-119">Example</span></span>  
 <span data-ttu-id="1db19-120">Im folgende Beispiel wird gezeigt, wie zum Platzieren von eines Try-Catch-Blocks in einen Delegaten, die es ermöglichen, eine Ausnahme abfangen und Fortsetzen der Ausführung der Abfrage möglich wird.</span><span class="sxs-lookup"><span data-stu-id="1db19-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1db19-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1db19-121">Compiling the Code</span></span>  
  
-   <span data-ttu-id="1db19-122">Kompilieren und Ausführen dieser Beispiele, kopieren Sie sie in PLINQ-Datenbeispiel, und rufen Sie die Methode aus.</span><span class="sxs-lookup"><span data-stu-id="1db19-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1db19-123">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="1db19-123">Robust Programming</span></span>  
 <span data-ttu-id="1db19-124">Abgefangen Sie eine Ausnahme nicht, es sei denn, Sie wissen, wie Sie sie behandeln, damit Sie den Status des Programms nicht beschädigt werden.</span><span class="sxs-lookup"><span data-stu-id="1db19-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db19-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1db19-125">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="1db19-126">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="1db19-126">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
