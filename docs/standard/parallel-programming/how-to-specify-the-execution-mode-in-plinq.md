---
title: "Gewusst wie: Angeben des Ausführungsmodus in PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="be772-102">Gewusst wie: Angeben des Ausführungsmodus in PLINQ</span><span class="sxs-lookup"><span data-stu-id="be772-102">How to: Specify the Execution Mode in PLINQ</span></span>
<span data-ttu-id="be772-103">Dieses Beispiel zeigt, wie PLINQ seine Standardheuristik zu umgehen und die Parallelisierung einer Abfrage unabhängig von der Form der Abfrage zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="be772-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="be772-104">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="be772-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="be772-105">Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="be772-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be772-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be772-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="be772-107">PLINQ wurde entwickelt, um Verkaufschancen für die Parallelisierung auszunutzen.</span><span class="sxs-lookup"><span data-stu-id="be772-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="be772-108">Nicht alle Abfragen werden jedoch von der parallelen Ausführung profitieren.</span><span class="sxs-lookup"><span data-stu-id="be772-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="be772-109">Wenn eine Abfrage einen einzelnen Benutzerdelegaten, der sehr geringem Aufwand ist enthält, wird beispielsweise die Abfrage, in der Regel schneller sequenziell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="be772-109">For example, when a query contains a single user delegate that does very little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="be772-110">Dies ist, da der Aufwand bei der Aktivierung der parallelen Ausführung teurer als die Beschleunigung ist, abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="be772-110">This is because the overhead involved in enabling parallelizing execution is more expensive than the speedup that is obtained.</span></span> <span data-ttu-id="be772-111">PLINQ daher nicht automatisch auf jede Abfrage parallelisieren.</span><span class="sxs-lookup"><span data-stu-id="be772-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="be772-112">Zunächst wird die Form der Abfrage und die verschiedenen Operatoren, die es bilden untersucht.</span><span class="sxs-lookup"><span data-stu-id="be772-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="be772-113">Auf Grundlage dieser Analyse kann PLINQ in der Standardmodus für die Ausführung entscheiden, einige oder alle der Abfrage sequenziell ausführen.</span><span class="sxs-lookup"><span data-stu-id="be772-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="be772-114">In einigen Fällen können Sie mehr über die Abfrage wissen jedoch als PLINQ in der Analyse ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="be772-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="be772-115">Beispielsweise können Sie wissen, dass ein Delegat sehr kostspielig ist und die Abfrage definitiv von einer Parallelisierung profitieren.</span><span class="sxs-lookup"><span data-stu-id="be772-115">For example, you may know that a delegate is very expensive, and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="be772-116">In solchen Fällen können Sie die <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> Methode, und geben Sie die <xref:System.Linq.ParallelExecutionMode.ForceParallelism> Wert PLINQ anweisen, stets die Abfrage Parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="be772-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="be772-117">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="be772-117">Compiling the Code</span></span>  
 <span data-ttu-id="be772-118">Ausschneiden und Einfügen dieser Code in der [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) und rufen Sie die Methode aus `Main`.</span><span class="sxs-lookup"><span data-stu-id="be772-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be772-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be772-119">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [<span data-ttu-id="be772-120">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="be772-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
