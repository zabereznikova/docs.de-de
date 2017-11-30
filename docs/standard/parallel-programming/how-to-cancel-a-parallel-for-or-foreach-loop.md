---
title: 'Gewusst wie: Abbrechen einer Parallel.For-Schleife oder einer ForEach-Schleife'
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
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f82c5758e02b4beebf035fe8f43f856447855a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="65ff5-102">Gewusst wie: Abbrechen einer Parallel.For-Schleife oder einer ForEach-Schleife</span><span class="sxs-lookup"><span data-stu-id="65ff5-102">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="65ff5-103">Die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> Methoden unterstützen einen Abbruch durch die Verwendung von Abbruchtoken.</span><span class="sxs-lookup"><span data-stu-id="65ff5-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="65ff5-104">Weitere Informationen über Abbrüche in der Regel finden Sie unter [Abbruch](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="65ff5-104">For more information about cancellation in general, see [Cancellation](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="65ff5-105">Geben Sie in einer parallelen Schleife die <xref:System.Threading.CancellationToken> an die Methode in der <xref:System.Threading.Tasks.ParallelOptions> Parameter und schließen Sie den parallelen Aufruf in einem Try / Catch-Block.</span><span class="sxs-lookup"><span data-stu-id="65ff5-105">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ff5-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65ff5-106">Example</span></span>  
 <span data-ttu-id="65ff5-107">Im folgende Beispiel wird gezeigt, wie einen Aufruf zum Abbrechen <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65ff5-107">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="65ff5-108">Sie können den gleichen Ansatz zum Anwenden einer <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="65ff5-108">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="65ff5-109">Wenn das Token, das den Abbruch signalisiert dem token im angegeben sind die <xref:System.Threading.Tasks.ParallelOptions> -Instanz erfolgt, die parallele Schleife ein einzelnes auslöst, <xref:System.OperationCanceledException> einem Abbruch.</span><span class="sxs-lookup"><span data-stu-id="65ff5-109">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="65ff5-110">Wenn ein anderes Token einen Abbruch verursacht, löst die Schleife ein <xref:System.AggregateException> mit einem <xref:System.OperationCanceledException> als ein "InnerException".</span><span class="sxs-lookup"><span data-stu-id="65ff5-110">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ff5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65ff5-111">See Also</span></span>  
 [<span data-ttu-id="65ff5-112">Datenparallelität</span><span class="sxs-lookup"><span data-stu-id="65ff5-112">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="65ff5-113">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="65ff5-113">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
