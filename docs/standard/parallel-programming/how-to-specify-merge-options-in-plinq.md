---
title: 'Gewusst wie: Angeben von Zusammenführungsoptionen in PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
ms.openlocfilehash: 7c7979dc828f89435422b464b22710b3a052911b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722426"
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="2aa8a-102">Gewusst wie: Angeben von Zusammenführungsoptionen in PLINQ</span><span class="sxs-lookup"><span data-stu-id="2aa8a-102">How to: Specify Merge Options in PLINQ</span></span>

<span data-ttu-id="2aa8a-103">Dieses Beispiel zeigt, wie Mergeoptionen angegeben werden, die für alle nachfolgenden Operatoren in einer PLINQ-Abfrage angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2aa8a-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="2aa8a-104">Sie müssen nicht explizit Mergeoptionen festlegen, aber dies könnte die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="2aa8a-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="2aa8a-105">Weitere Informationen zu Mergeoptionen finden Sie unter [Mergeoptionen in PLINQ](merge-options-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="2aa8a-105">For more information about merge options, see [Merge Options in PLINQ](merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="2aa8a-106">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="2aa8a-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="2aa8a-107">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="2aa8a-107">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa8a-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2aa8a-108">Example</span></span>  

 <span data-ttu-id="2aa8a-109">Das folgende Beispiel veranschaulicht das Verhalten von Mergeoptionen in einem einfachen Szenario, das eine ungeordnete Quelle aufweist und wo eine aufwändige Funktion auf jedes Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2aa8a-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="2aa8a-110">In Fällen, in denen die <xref:System.Linq.ParallelMergeOptions.AutoBuffered>-Option eine unerwünschte Latenzzeit verursacht, bevor das erste Element ausgegeben wird, probieren Sie aus, ob mit der <xref:System.Linq.ParallelMergeOptions.NotBuffered>-Option Ergebniselemente schneller und reibungsloser bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2aa8a-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa8a-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2aa8a-111">See also</span></span>

- <xref:System.Linq.ParallelMergeOptions>
- [<span data-ttu-id="2aa8a-112">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="2aa8a-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
