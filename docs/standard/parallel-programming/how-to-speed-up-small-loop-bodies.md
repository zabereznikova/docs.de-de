---
title: 'Gewusst wie: Beschleunigen von kurzen Schleifenkörpern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 2597e37ed5901d704c94ff960bcb4b2c97633392
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722391"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="3885e-102">Gewusst wie: Beschleunigen von kurzen Schleifenkörpern</span><span class="sxs-lookup"><span data-stu-id="3885e-102">How to: Speed Up Small Loop Bodies</span></span>

<span data-ttu-id="3885e-103">Wenn eine <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Schleife nur wenig Text enthält, wird sie möglicherweise langsamer ausgeführt als die entsprechende sequenzielle Schleife, wie die [For](../../csharp/language-reference/keywords/for.md)-Schleife in C# und die [For](/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90))-Schleife in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3885e-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](../../csharp/language-reference/keywords/for.md) loop in C# and the [For](/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) loop in Visual Basic.</span></span> <span data-ttu-id="3885e-104">Der Leistungsverlust wird von dem Aufwand verursacht, der mit dem Partitionieren der Daten einhergeht, und von den Kosten des Aufrufs eines Delegaten bei jeder Schleifeniteration.</span><span class="sxs-lookup"><span data-stu-id="3885e-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="3885e-105">Für solche Szenarien stellt die <xref:System.Collections.Concurrent.Partitioner>-Klasse die <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>-Methode bereit, die es Ihnen ermöglicht, eine sequenzielle Schleife für den Delegattext einzurichten, damit der Delegat nur einmal pro Partition und nicht einmal bei jeder Iteration aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3885e-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="3885e-106">Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL (Benutzerdefinierte Partitionierer für PLINQ und TPL)](custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="3885e-106">For more information, see [Custom Partitioners for PLINQ and TPL](custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3885e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3885e-107">Example</span></span>  

 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="3885e-108">Der in diesem Beispiel gezeigte Ansatz ist hilfreich, wenn die Schleife nur eine minimale Menge an Arbeit ausführt.</span><span class="sxs-lookup"><span data-stu-id="3885e-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="3885e-109">Wenn die Arbeit berechnungsintensiver wird, erhalten Sie wahrscheinlich die gleiche oder eine bessere Leistung, wenn Sie eine <xref:System.Threading.Tasks.Parallel.For%2A>- oder <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife in Verbindung mit dem Standardpartitionierer verwenden.</span><span class="sxs-lookup"><span data-stu-id="3885e-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3885e-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3885e-110">See also</span></span>

- [<span data-ttu-id="3885e-111">Datenparallelität</span><span class="sxs-lookup"><span data-stu-id="3885e-111">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="3885e-112">Benutzerdefinierte Partitionierer für PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="3885e-112">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="3885e-113">Iteratoren (C#)</span><span class="sxs-lookup"><span data-stu-id="3885e-113">Iterators (C#)</span></span>](../../csharp/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="3885e-114">Iteratoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3885e-114">Iterators (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="3885e-115">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="3885e-115">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
