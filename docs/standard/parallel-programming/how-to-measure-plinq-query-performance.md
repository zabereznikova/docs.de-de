---
title: 'Vorgehensweise: Messen der Leistung von PLINQ-Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: 43f83a34531b853d108785052f637d9568c45280
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826878"
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="a8250-102">Vorgehensweise: Messen der Leistung von PLINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="a8250-102">How to: Measure PLINQ Query Performance</span></span>

<span data-ttu-id="a8250-103">Dieses Beispiel zeigt, wie Sie mithilfe der <xref:System.Diagnostics.Stopwatch>-Klasse messen können, wie viel Zeit für die Ausführung einer PLINQ-Abfrage benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="a8250-103">This example shows how to use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8250-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8250-104">Example</span></span>  
 <span data-ttu-id="a8250-105">In diesem Beispiel wird eine leere `foreach`-Schleife (`For Each` in Visual Basic) verwendet, um die für die Ausführung der Abfrage erforderliche Zeit zu messen.</span><span class="sxs-lookup"><span data-stu-id="a8250-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="a8250-106">In echtem Code würde die Schleife normalerweise weitere Verarbeitungsschritte enthalten, die die Gesamtzeit der Abfrageausführung erhöhen.</span><span class="sxs-lookup"><span data-stu-id="a8250-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="a8250-107">Beachten Sie, dass die Stoppuhr erst kurz vor der Schleife gestartet wird, wenn die Abfrageausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="a8250-107">Notice that the stopwatch is not started until just before the loop, because that's when the query execution begins.</span></span> <span data-ttu-id="a8250-108">Wenn Sie eine differenziertere Messung benötigen, können Sie die `ElapsedTicks`-Eigenschaft anstelle der `ElapsedMilliseconds`-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8250-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="a8250-109">Die Gesamtausführungszeit ist eine wichtige Messgröße beim Testen von Abfrageimplementierungen, sie vermittelt jedoch nicht immer das Gesamtbild.</span><span class="sxs-lookup"><span data-stu-id="a8250-109">The total execution time is a useful metric when you are experimenting with query implementations, but it doesn't always tell the whole story.</span></span> <span data-ttu-id="a8250-110">Verwenden Sie die [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer), um eine genauere und umfangreichere Darstellung der Interaktion der Abfragethreads untereinander und mit anderen laufenden Prozessen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a8250-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8250-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8250-111">See also</span></span>

- [<span data-ttu-id="a8250-112">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="a8250-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
