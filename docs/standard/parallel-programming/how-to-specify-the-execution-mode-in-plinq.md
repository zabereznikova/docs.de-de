---
title: 'Vorgehensweise: Angeben des Ausführungsmodus in PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: f035dbcd5091d81a3cce3b9e9e683d836fe84bb7
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635815"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="d7399-102">Vorgehensweise: Angeben des Ausführungsmodus in PLINQ</span><span class="sxs-lookup"><span data-stu-id="d7399-102">How to: Specify the Execution Mode in PLINQ</span></span>

<span data-ttu-id="d7399-103">Dieses Beispiel zeigt, wie erzwungen wird, dass PLINQ seine Standardheuristik umgeht und eine Abfrage unabhängig von der Form parallelisiert.</span><span class="sxs-lookup"><span data-stu-id="d7399-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7399-104">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d7399-104">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="d7399-105">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="d7399-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7399-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7399-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="d7399-107">PLINQ ist dazu konzipiert, Gelegenheiten zur Parallelisierung auszunutzen.</span><span class="sxs-lookup"><span data-stu-id="d7399-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="d7399-108">Nicht alle Abfragen profitieren jedoch von der parallelen Ausführung.</span><span class="sxs-lookup"><span data-stu-id="d7399-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="d7399-109">Wenn eine Abfrage z. B. einen einzelnen Benutzerdelegaten enthält, der wenig ausführt, ist die sequenzielle Ausführung der Abfrage in der Regel schneller.</span><span class="sxs-lookup"><span data-stu-id="d7399-109">For example, when a query contains a single user delegate that does little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="d7399-110">Die sequenzielle Ausführung ist schneller, da sich der Mehraufwand zum Aktivieren der parallelen Ausführung im Vergleich zur erzielten Beschleunigung nicht rentiert.</span><span class="sxs-lookup"><span data-stu-id="d7399-110">Sequential execution is faster because the overhead involved in enabling parallelizing execution is more expensive than the speedup that's obtained.</span></span> <span data-ttu-id="d7399-111">Darum parallelisiert PLINQ nicht automatisch jede Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d7399-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="d7399-112">Zunächst werden die Form der Abfrage und die verschiedenen enthaltenen Operatoren untersucht.</span><span class="sxs-lookup"><span data-stu-id="d7399-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="d7399-113">Auf Grundlage dieser Analyse kann PLINQ im Standardausführungsmodus entscheiden, die Abfrage zum Teil oder im Ganzen sequenziell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d7399-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="d7399-114">In einigen Fällen wissen Sie jedoch vielleicht mehr über die Abfrage, als PLINQ in seiner Analyse ermitteln kann.</span><span class="sxs-lookup"><span data-stu-id="d7399-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="d7399-115">Möglicherweise wissen Sie, dass ein Delegat aufwendig ist und die Abfrage definitiv von einer Parallelisierung profitiert.</span><span class="sxs-lookup"><span data-stu-id="d7399-115">For example, you may know that a delegate is expensive and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="d7399-116">In solchen Fällen können Sie mit der <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>-Methode den <xref:System.Linq.ParallelExecutionMode.ForceParallelism>-Wert angeben und PLINQ anweisen, die Abfrage stets parallel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d7399-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7399-117">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d7399-117">Compiling the Code</span></span>  
 <span data-ttu-id="d7399-118">Schneiden Sie diesen Code aus, fügen Sie ihn in das [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) ein, und rufen Sie die Methode in `Main` auf.</span><span class="sxs-lookup"><span data-stu-id="d7399-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7399-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7399-119">See also</span></span>

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [<span data-ttu-id="d7399-120">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="d7399-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
