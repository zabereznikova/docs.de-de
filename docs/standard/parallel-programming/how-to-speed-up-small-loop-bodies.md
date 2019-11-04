---
title: 'Vorgehensweise: Beschleunigen von kurzen Schleifenkörpern'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 29d7fa8200ddd972c1a5c98ea6f30a7c8ff732e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139753"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="89f31-102">Vorgehensweise: Beschleunigen von kurzen Schleifenkörpern</span><span class="sxs-lookup"><span data-stu-id="89f31-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="89f31-103">Wenn eine <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Schleife nur wenig Text enthält, wird sie möglicherweise langsamer ausgeführt als die entsprechende sequenzielle Schleife, wie die [For](../../csharp/language-reference/keywords/for.md)-Schleife in C# und die [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90))-Schleife in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="89f31-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](../../csharp/language-reference/keywords/for.md) loop in C# and the [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) loop in Visual Basic.</span></span> <span data-ttu-id="89f31-104">Der Leistungsverlust wird von dem Aufwand verursacht, der mit dem Partitionieren der Daten einhergeht, und von den Kosten des Aufrufs eines Delegaten bei jeder Schleifeniteration.</span><span class="sxs-lookup"><span data-stu-id="89f31-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="89f31-105">Für solche Szenarien stellt die <xref:System.Collections.Concurrent.Partitioner>-Klasse die <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>-Methode bereit, die es Ihnen ermöglicht, eine sequenzielle Schleife für den Delegattext einzurichten, damit der Delegat nur einmal pro Partition und nicht einmal bei jeder Iteration aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="89f31-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="89f31-106">Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL (Benutzerdefinierte Partitionierer für PLINQ und TPL)](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="89f31-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89f31-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89f31-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="89f31-108">Der in diesem Beispiel gezeigte Ansatz ist hilfreich, wenn die Schleife nur eine minimale Menge an Arbeit ausführt.</span><span class="sxs-lookup"><span data-stu-id="89f31-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="89f31-109">Wenn die Arbeit berechnungsintensiver wird, erhalten Sie wahrscheinlich die gleiche oder eine bessere Leistung, wenn Sie eine <xref:System.Threading.Tasks.Parallel.For%2A>- oder <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife in Verbindung mit dem Standardpartitionierer verwenden.</span><span class="sxs-lookup"><span data-stu-id="89f31-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f31-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89f31-110">See also</span></span>

- [<span data-ttu-id="89f31-111">Datenparallelität</span><span class="sxs-lookup"><span data-stu-id="89f31-111">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="89f31-112">Benutzerdefinierte Partitionierer für PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="89f31-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="89f31-113">Iteratoren (C#)</span><span class="sxs-lookup"><span data-stu-id="89f31-113">Iterators (C#)</span></span>](../../csharp/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="89f31-114">Iteratoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89f31-114">Iterators (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="89f31-115">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="89f31-115">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
