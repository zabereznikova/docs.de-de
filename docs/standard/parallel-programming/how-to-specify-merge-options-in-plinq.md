---
title: 'Vorgehensweise: Angeben von Mergeoptionen in PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 947f3cb15b7eb372d20884ece73374114c48f472
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988851"
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="688d1-102">Vorgehensweise: Angeben von Mergeoptionen in PLINQ</span><span class="sxs-lookup"><span data-stu-id="688d1-102">How to: Specify Merge Options in PLINQ</span></span>
<span data-ttu-id="688d1-103">Dieses Beispiel zeigt, wie Mergeoptionen angegeben werden, die für alle nachfolgenden Operatoren in einer PLINQ-Abfrage angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="688d1-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="688d1-104">Sie müssen nicht explizit Mergeoptionen festlegen, aber dies könnte die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="688d1-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="688d1-105">Weitere Informationen zu Mergeoptionen finden Sie unter [Mergeoptionen in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="688d1-105">For more information about merge options, see [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="688d1-106">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="688d1-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="688d1-107">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="688d1-107">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="688d1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="688d1-108">Example</span></span>  
 <span data-ttu-id="688d1-109">Das folgende Beispiel veranschaulicht das Verhalten von Mergeoptionen in einem einfachen Szenario, das eine ungeordnete Quelle aufweist und wo eine aufwändige Funktion auf jedes Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="688d1-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="688d1-110">In Fällen, in denen die <xref:System.Linq.ParallelMergeOptions.AutoBuffered>-Option eine unerwünschte Latenzzeit verursacht, bevor das erste Element ausgegeben wird, probieren Sie aus, ob mit der <xref:System.Linq.ParallelMergeOptions.NotBuffered>-Option Ergebniselemente schneller und reibungsloser bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="688d1-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="688d1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="688d1-111">See also</span></span>

- <xref:System.Linq.ParallelMergeOptions>
- [<span data-ttu-id="688d1-112">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="688d1-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
