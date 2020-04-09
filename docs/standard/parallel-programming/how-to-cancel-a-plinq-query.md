---
title: 'Vorgehensweise: Abbrechen einer PLINQ-Abfrage'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
ms.openlocfilehash: 312c71b787ac7b4aa092f1517d2ed5af314a22e4
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635880"
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="98068-102">Vorgehensweise: Abbrechen einer PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="98068-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="98068-103">In den folgenden Beispielen werden zwei Möglichkeiten zum Ändern einer PLINQ-Abfrage veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="98068-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="98068-104">Das erste Beispiel zeigt, wie eine Abfrage abgebrochen wird, die größtenteils aus Datendurchlauf besteht.</span><span class="sxs-lookup"><span data-stu-id="98068-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="98068-105">Im zweiten Beispiel wird gezeigt, wie eine Abfrage abgebrochen wird, die eine rechenintensive Benutzerfunktion enthält.</span><span class="sxs-lookup"><span data-stu-id="98068-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>

> [!NOTE]
> <span data-ttu-id="98068-106">Wenn „Nur eigenen Code“ aktiviert ist, unterbricht Visual Studio die Ausführung in der Zeile, die die Ausnahme auslöst, und zeigt eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme an.</span><span class="sxs-lookup"><span data-stu-id="98068-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="98068-107">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="98068-107">This error is benign.</span></span> <span data-ttu-id="98068-108">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="98068-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="98068-109">Um zu verhindern, dass Visual Studio beim ersten Fehler abbricht, deaktivieren Sie einfach unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.</span><span class="sxs-lookup"><span data-stu-id="98068-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>
>
> <span data-ttu-id="98068-110">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="98068-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="98068-111">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="98068-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>

## <a name="example"></a><span data-ttu-id="98068-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98068-112">Example</span></span>

[!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
[!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]

<span data-ttu-id="98068-113">Das PLINQ-Framework setzt keine einzelne <xref:System.OperationCanceledException> in eine <xref:System.AggregateException?displayProperty=nameWithType> zurück; die <xref:System.OperationCanceledException> muss in einem separaten Catch-Block behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="98068-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="98068-114">Wenn mindestens ein Benutzerdelegat eine OperationCanceledException(externalCT) (mithilfe einer externen <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) auslöst, aber keine weitere Ausnahme, und die Abfrage als `AsParallel().WithCancellation(externalCT)` definiert wurde, dann gibt PLINQ eine einzelne <xref:System.OperationCanceledException>(externalCT) anstelle einer <xref:System.AggregateException?displayProperty=nameWithType> aus.</span><span class="sxs-lookup"><span data-stu-id="98068-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="98068-115">Löst jedoch ein Benutzerdelegat eine <xref:System.OperationCanceledException> und ein anderer Delegat einen anderen Ausnahmetyp aus, werden beide Ausnahmen in eine <xref:System.AggregateException> zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="98068-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>

<span data-ttu-id="98068-116">Der allgemeine Leitfaden zum Abbruch lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="98068-116">The general guidance on cancellation is as follows:</span></span>

1. <span data-ttu-id="98068-117">Wenn Sie einen Benutzerdelegatenabbruch ausführen, sollten Sie PLINQ über das externe <xref:System.Threading.CancellationToken> informieren und eine <xref:System.OperationCanceledException>(externalCT) auslösen.</span><span class="sxs-lookup"><span data-stu-id="98068-117">If you perform user-delegate cancellation, you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>

2. <span data-ttu-id="98068-118">Wenn ein Abbruch auftritt und keine anderen Ausnahmen ausgelöst werden, sollten Sie eine <xref:System.OperationCanceledException> anstelle einer <xref:System.AggregateException> behandeln.</span><span class="sxs-lookup"><span data-stu-id="98068-118">If cancellation occurs and no other exceptions are thrown, then handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>

## <a name="example"></a><span data-ttu-id="98068-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98068-119">Example</span></span>

<span data-ttu-id="98068-120">Das folgende Beispiel zeigt, wie Sie einen Abbruch behandeln müssen, wenn der Benutzercode eine rechenintensive Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="98068-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>

[!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
[!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]

<span data-ttu-id="98068-121">Wenn Sie den Abbruch im Benutzercode behandeln, müssen Sie <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> nicht in der Abfragedefinition verwenden.</span><span class="sxs-lookup"><span data-stu-id="98068-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="98068-122">Allerdings sollten Sie <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> verwenden, da <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> keine Auswirkung auf die Abfrageleistung hat und die Behandlung des Abbruchs durch Abfrageoperatoren und Ihren Benutzercode ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="98068-122">However, we recommended that you do use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>, because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>

<span data-ttu-id="98068-123">Um die Reaktionsfähigkeit des Systems zu gewährleisten, sollten Sie etwa einmal pro Millisekunde prüfen, ob ein Abbruch vorliegt; allerdings ist jeder Zeitraum von bis zu 10 Millisekunden akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="98068-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="98068-124">Diese Häufigkeit sollte sich nicht negativ auf die Leistung Ihres Codes auswirken.</span><span class="sxs-lookup"><span data-stu-id="98068-124">This frequency should not have a negative impact on your code's performance.</span></span>

<span data-ttu-id="98068-125">Wenn ein Enumerator verworfen wird, z. B. wenn Code aus einer foreach-Schleife („For Each“ in Visual Basic) ausbricht, die eine Iteration über Abfrageergebnisse durchführt, wird die Abfrage abgebrochen, jedoch keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="98068-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is canceled, but no exception is thrown.</span></span>

## <a name="see-also"></a><span data-ttu-id="98068-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98068-126">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="98068-127">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="98068-127">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
- [<span data-ttu-id="98068-128">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="98068-128">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
