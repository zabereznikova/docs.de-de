---
title: 'Gewusst wie: Messen der Leistung von PLINQ-Abfragen'
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
helpviewer_keywords: PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03432e70454cb6203e55e340111a6cb7efe62dc4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="e25fc-102">Gewusst wie: Messen der Leistung von PLINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="e25fc-102">How to: Measure PLINQ Query Performance</span></span>
<span data-ttu-id="e25fc-103">In diesem Beispiel wird veranschaulicht, wie mit der <xref:System.Diagnostics.Stopwatch> Klasse, um die Zeit zu messen, dauert es für eine PLINQ-Abfrage ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e25fc-103">This example shows how use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25fc-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e25fc-104">Example</span></span>  
 <span data-ttu-id="e25fc-105">In diesem Beispiel wird eine leere `foreach`-Schleife (`For Each` in Visual Basic) verwendet, um die für die Ausführung der Abfrage erforderliche Zeit zu messen.</span><span class="sxs-lookup"><span data-stu-id="e25fc-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="e25fc-106">In echtem Code würde die Schleife normalerweise weitere Verarbeitungsschritte enthalten, die die Gesamtzeit der Abfrageausführung erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e25fc-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="e25fc-107">Beachten Sie, dass die Stoppuhr erst kurz vor der Schleife gestartet wird, wenn die Abfrageausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="e25fc-107">Notice that the stopwatch is not started until just before the loop, because that is when the query execution begins.</span></span> <span data-ttu-id="e25fc-108">Wenn Sie eine differenziertere Messung benötigen, können Sie die `ElapsedTicks`-Eigenschaft anstelle der `ElapsedMilliseconds`-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="e25fc-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="e25fc-109">Die Gesamtausführungszeit ist eine wichtige Messgröße beim Testen von Abfrageimplementierungen, sie vermittelt jedoch nicht immer das Gesamtbild.</span><span class="sxs-lookup"><span data-stu-id="e25fc-109">The total execution time is a useful metric when you are experimenting with query implementations, but it does not always tell the whole story.</span></span> <span data-ttu-id="e25fc-110">Verwenden Sie die Parallelitätsschnellansicht, um eine genauere und umfangreichere Darstellung von der Interaktion der Abfragethreads untereinander und mit anderen laufenden Prozessen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e25fc-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the Concurrency Visualizer.</span></span> <span data-ttu-id="e25fc-111">Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="e25fc-111">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25fc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e25fc-112">See Also</span></span>  
 [<span data-ttu-id="e25fc-113">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="e25fc-113">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
