---
title: 'Gewusst wie: Angeben von Mergeoptionen in PLINQ'
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
helpviewer_keywords: PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec601e8bbefd31650fb91c438b032942cfc93101
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="2242a-102">Gewusst wie: Angeben von Mergeoptionen in PLINQ</span><span class="sxs-lookup"><span data-stu-id="2242a-102">How to: Specify Merge Options in PLINQ</span></span>
<span data-ttu-id="2242a-103">Dieses Beispiel zeigt, wie die Mergeoptionen angeben, die für alle nachfolgenden Operatoren in einer PLINQ-Abfrage angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2242a-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="2242a-104">Sie müssen nicht explizit festlegen von Zusammenführungsoptionen, aber dies daher kann die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="2242a-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="2242a-105">Weitere Informationen zu Mergeoptionen finden Sie unter [Zusammenführungsoptionen in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="2242a-105">For more information about merge options, see [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2242a-106">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="2242a-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="2242a-107">Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="2242a-107">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2242a-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2242a-108">Example</span></span>  
 <span data-ttu-id="2242a-109">Das folgende Beispiel veranschaulicht das Verhalten von Zusammenführungsoptionen in einem einfachen Szenario, das eine ungeordnete Quelle aufweist und eine teure-Funktion auf jedes Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2242a-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="2242a-110">In Fällen, in denen die <xref:System.Linq.ParallelMergeOptions.AutoBuffered> Option verursacht einer unerwünschten Latenzzeit, bevor das erste Element ausgegeben wird, und versuchen Sie die <xref:System.Linq.ParallelMergeOptions.NotBuffered> Option aus, um die Ergebniselemente schneller und gleichmäßiger ergeben.</span><span class="sxs-lookup"><span data-stu-id="2242a-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2242a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2242a-111">See Also</span></span>  
 <xref:System.Linq.ParallelMergeOptions>  
 [<span data-ttu-id="2242a-112">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="2242a-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
