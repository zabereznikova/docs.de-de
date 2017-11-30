---
title: 'Gewusst wie: Kombinieren von parallelen und sequenziellen LINQ-Abfragen'
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="3e071-102">Gewusst wie: Kombinieren von parallelen und sequenziellen LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="3e071-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="3e071-103">Dieses Beispiel zeigt, wie die <xref:System.Linq.ParallelEnumerable.AsSequential%2A> Methode PLINQ anweisen, alle nachfolgende Operatoren in der Abfrage sequenziell zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3e071-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="3e071-104">Obwohl sequenzielle Verarbeitung i. a. langsamer als die parallele ist, ist es manchmal erforderlich, um richtige Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="3e071-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3e071-105">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="3e071-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="3e071-106">Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="3e071-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e071-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e071-107">Example</span></span>  
 <span data-ttu-id="3e071-108">Das folgende Beispiel zeigt ein Szenario, in dem <xref:System.Linq.ParallelEnumerable.AsSequential%2A> erforderlich ist, d. h. um die Reihenfolge, die in einer vorherigen-Klausel der Abfrage eingerichtet wurde beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3e071-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3e071-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3e071-109">Compiling the Code</span></span>  
 <span data-ttu-id="3e071-110">Zum Kompilieren und führen Sie diesen Code, fügen Sie ihn in die [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) Projekt, fügen Sie eine Zeile für den Methodenaufruf aus `Main`, und drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="3e071-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e071-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e071-111">See Also</span></span>  
 [<span data-ttu-id="3e071-112">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="3e071-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
