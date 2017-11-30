---
title: 'Gewusst wie: Abbrechen einer PLINQ-Abfrage'
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
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="b743e-102">Gewusst wie: Abbrechen einer PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="b743e-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="b743e-103">In den folgenden Beispielen werden zwei Möglichkeiten zum Abbrechen einer PLINQ-Abfrage veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b743e-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="b743e-104">Das erste Beispiel zeigt, wie Sie eine Abfrage abgebrochen wird, aus die Daten Durchlauf größtenteils besteht.</span><span class="sxs-lookup"><span data-stu-id="b743e-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="b743e-105">Im zweite Beispiel wird gezeigt, wie eine Abfrage abbrechen mit einer Funktion, die rechenintensive wird.</span><span class="sxs-lookup"><span data-stu-id="b743e-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b743e-106">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio wird in der Zeile, die die Ausnahme auslöst und zeigt eine Fehlermeldung an, die besagt, dass "nicht vom Benutzercode behandelten Ausnahme."</span><span class="sxs-lookup"><span data-stu-id="b743e-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="b743e-107">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="b743e-107">This error is benign.</span></span> <span data-ttu-id="b743e-108">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="b743e-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="b743e-109">Zum verhindern, dass Visual Studio den ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="b743e-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="b743e-110">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="b743e-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="b743e-111">Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="b743e-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b743e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b743e-112">Example</span></span>  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 <span data-ttu-id="b743e-113">PLINQ-Framework erfolgt kein Rollback für eine einzelne <xref:System.OperationCanceledException> in einer <xref:System.AggregateException?displayProperty=nameWithType>; das <xref:System.OperationCanceledException> müssen in einem separaten Catch-Block behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b743e-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="b743e-114">Wenn eine oder mehrere Benutzerdelegaten eine OperationCanceledException(externalCT) (mithilfe ein externen <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), aber keine anderen Ausnahmen und die Abfrage definiert wurde, als `AsParallel().WithCancellation(externalCT)`, dann PLINQ die eine einzelne ausstellen, <xref:System.OperationCanceledException> (ExternalCT) anstelle einer <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b743e-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b743e-115">Löst Sie jedoch, wenn ein Benutzer delegieren einer <xref:System.OperationCanceledException>, ein anderer Delegat löst einen anderen Ausnahmetyp aus, und beide Ausnahmen werden zurückgesetzt, in eine <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="b743e-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>  
  
 <span data-ttu-id="b743e-116">Die allgemeinen Leitfaden zum Abbruch lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b743e-116">The general guidance on cancellation is as follows:</span></span>  
  
1.  <span data-ttu-id="b743e-117">Wenn Sie Benutzerdelegaten Abbruch ausführen sollten Sie PLINQ informieren Sie über externe <xref:System.Threading.CancellationToken> und löst eine <xref:System.OperationCanceledException>(ExternalCT).</span><span class="sxs-lookup"><span data-stu-id="b743e-117">If you perform user-delegate cancellation you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>  
  
2.  <span data-ttu-id="b743e-118">Wenn ein Abbruch auftritt und keine anderen Ausnahmen ausgelöst werden, dann sollten behandelt eine <xref:System.OperationCanceledException> anstelle einer <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="b743e-118">If cancellation occurs and no other exceptions are thrown, then you should handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b743e-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b743e-119">Example</span></span>  
 <span data-ttu-id="b743e-120">Das folgende Beispiel zeigt, wie zum Abbruch behandelt wird, wenn Sie eine rechenintensive Funktion im Benutzercode haben.</span><span class="sxs-lookup"><span data-stu-id="b743e-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 <span data-ttu-id="b743e-121">Wenn Sie den Abbruch im Benutzercode behandeln, müssen Sie nicht verwenden <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in der Abfragedefinition.</span><span class="sxs-lookup"><span data-stu-id="b743e-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="b743e-122">Allerdings wird empfohlen, dass Sie da hierzu <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> hat keine Auswirkung auf die abfrageleistung und ermöglicht den Abbruch von Abfrageoperatoren und Benutzercode behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b743e-122">However, we recommended that you do this because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>  
  
 <span data-ttu-id="b743e-123">Um die Reaktionsfähigkeit des Systems zu gewährleisten, wird empfohlen, nach einem Abbruch um einmal pro Millisekunde gesucht; Allerdings wird jedem Zeitraum von bis zu 10 Millisekunden als akzeptabel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="b743e-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="b743e-124">Diese Häufigkeit sollte nicht negativ auf die Leistung Ihres Codes haben.</span><span class="sxs-lookup"><span data-stu-id="b743e-124">This frequency should not have a negative impact on your code's performance.</span></span>  
  
 <span data-ttu-id="b743e-125">Wenn ein Enumerator verworfen wird, z. B. wenn Code unterbricht aus einer Schleife Foreach (For Each in Visual Basic), die Ergebnisse der Abfrage durchläuft wird die Abfrage abgebrochen wird, jedoch wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b743e-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is cancelled, but no exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b743e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b743e-126">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="b743e-127">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="b743e-127">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [<span data-ttu-id="b743e-128">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="b743e-128">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
