---
title: 'Gewusst wie: Schreiben einer benutzerdefinierten PLINQ-Aggregatfunktion'
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
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 210e9913ab3eba636ff99b7610df05655246f4eb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="479c9-102">Gewusst wie: Schreiben einer benutzerdefinierten PLINQ-Aggregatfunktion</span><span class="sxs-lookup"><span data-stu-id="479c9-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="479c9-103">Dieses Beispiel zeigt, wie mit der <xref:System.Linq.ParallelEnumerable.Aggregate%2A>-Methode eine benutzerdefinierte Aggregatfunktion auf eine Quellsequenz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="479c9-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="479c9-104">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="479c9-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="479c9-105">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="479c9-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="479c9-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="479c9-106">Example</span></span>  
 <span data-ttu-id="479c9-107">Im folgenden Beispiel wird die Standardabweichung einer Sequenz von ganzen Zahlen berechnet.</span><span class="sxs-lookup"><span data-stu-id="479c9-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="479c9-108">In diesem Beispiel wird eine Überladung des Aggregate-Standardabfrageoperators verwendet, der für PLINQ eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="479c9-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="479c9-109">Diese Überladung nimmt eine zusätzliche <xref:System.Func%603?displayProperty=nameWithType> als dritten Eingabeparameter an.</span><span class="sxs-lookup"><span data-stu-id="479c9-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="479c9-110">Dieser Delegat kombiniert die Ergebnisse aller Threads, bevor er die abschließende Berechnung der aggregierten Ergebnisse durchführt.</span><span class="sxs-lookup"><span data-stu-id="479c9-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="479c9-111">In diesem Beispiel addieren wir die Summen aller Threads.</span><span class="sxs-lookup"><span data-stu-id="479c9-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="479c9-112">Beachten Sie: Wenn ein Lambdaausdruckskörper aus einem einzelnen Ausdruck besteht, ist der Rückgabewert des <xref:System.Func%602?displayProperty=nameWithType>-Delegaten der Wert des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="479c9-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479c9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="479c9-113">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="479c9-114">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="479c9-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
