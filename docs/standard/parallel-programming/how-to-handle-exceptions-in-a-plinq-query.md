---
title: 'Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
ms.openlocfilehash: aa583d8c31381d23e22f271db3d42d35e1fa14b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826943"
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="6ddfb-102">Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="6ddfb-102">How to: Handle Exceptions in a PLINQ Query</span></span>

<span data-ttu-id="6ddfb-103">Das erste Beispiel in diesem Thema zeigt, wie die <xref:System.AggregateException?displayProperty=nameWithType> behandelt wird, die während der Ausführung von einer PLINQ-Abfrage ausgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="6ddfb-104">Das zweite Beispiel zeigt, wie try-catch-Blöcke in Delegaten so nah wie möglich an der Position platziert werden, an der die Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="6ddfb-105">Auf diese Weise können Sie sie sofort nach dem Auftreten abfangen und die Ausführung der Abfrage möglicherweise fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="6ddfb-106">Wenn Ausnahmen mittels Bubbling wieder an den Verbindungsthread übergeben werden können, ist es möglich, dass eine Abfrage nach dem Auslösen der Ausnahme weiterhin einige Elemente verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>

<span data-ttu-id="6ddfb-107">Wenn PLINQ auf die sequenzielle Ausführung zurückgreift und eine Ausnahme auftritt, kann die Ausnahme in einigen Fällen direkt weitergegeben werden und muss nicht mit einer <xref:System.AggregateException> umschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="6ddfb-108"><xref:System.Threading.ThreadAbortException>s werden darüber hinaus immer direkt weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>

> [!NOTE]
> <span data-ttu-id="6ddfb-109">Wenn „Nur eigenen Code“ aktiviert ist, unterbricht Visual Studio die Ausführung in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="6ddfb-110">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-110">This error is benign.</span></span> <span data-ttu-id="6ddfb-111">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="6ddfb-112">Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>
>
> <span data-ttu-id="6ddfb-113">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="6ddfb-114">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="6ddfb-114">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>

## <a name="example"></a><span data-ttu-id="6ddfb-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ddfb-115">Example</span></span>

<span data-ttu-id="6ddfb-116">Dieses Beispiel zeigt, wie die try-catch-Blöcke um den Code herum platziert werden, der die Abfrage ausführt, um alle ausgelösten <xref:System.AggregateException?displayProperty=nameWithType>s abzufangen.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>

[!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
[!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]

<span data-ttu-id="6ddfb-117">In diesem Beispiel kann die Abfrage nach dem Auslösen der Ausnahme nicht fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="6ddfb-118">Zu dem Zeitpunkt, an dem Ihr Anwendungscode die Ausnahme abfängt, hat PLINQ die Abfrage bereits in allen Threads beendet.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>

## <a name="example"></a><span data-ttu-id="6ddfb-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ddfb-119">Example</span></span>

<span data-ttu-id="6ddfb-120">Das folgende Beispiel zeigt, wie Sie einen try-catch-Block in einem Delegaten platzieren, um zu ermöglichen, dass eine Ausnahme abgefangen und die Ausführung der Abfrage fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>

[!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
[!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]

## <a name="compiling-the-code"></a><span data-ttu-id="6ddfb-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6ddfb-121">Compiling the Code</span></span>

- <span data-ttu-id="6ddfb-122">Um diese Beispiele zu kompilieren und auszuführen, kopieren Sie sie in das PLINQ Data Sample-Beispiel und rufen die Methode aus „Main“ auf.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="6ddfb-123">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6ddfb-123">Robust Programming</span></span>

<span data-ttu-id="6ddfb-124">Fangen Sie Ausnahmen nur ab, wenn Sie wissen, wie sie behandelt werden müssen, damit der Status Ihres Programms nicht beschädigt wird.</span><span class="sxs-lookup"><span data-stu-id="6ddfb-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ddfb-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ddfb-125">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="6ddfb-126">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="6ddfb-126">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
