---
title: 'Vorgehensweise: Abbrechen einer Parallel.For-Schleife oder einer ForEach-Schleife'
description: Brechen Sie eine Parallel.For- oder Parallel.ForEach-Schleife in .NET ab, indem Sie ein Abbruchtokenobjekt für die Methode im ParallelOptions-Parameter bereitstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: 842873afcba1bba3a00ccaa8c95310bd1efd3a92
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713313"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="12c50-103">Vorgehensweise: Abbrechen einer Parallel.For-Schleife oder einer ForEach-Schleife</span><span class="sxs-lookup"><span data-stu-id="12c50-103">How to: Cancel a Parallel.For or ForEach Loop</span></span>

<span data-ttu-id="12c50-104">Die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>- und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Methode unterstützen den Abbruch durch die Verwendung von Abbruchtoken.</span><span class="sxs-lookup"><span data-stu-id="12c50-104">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="12c50-105">Weitere Informationen über Abbrüche im Allgemeinen finden Sie unter [Abbruch in verwalteten Threads](../threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="12c50-105">For more information about cancellation in general, see [Cancellation](../threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="12c50-106">Übergeben Sie in einer parallelen Schleife das <xref:System.Threading.CancellationToken> mit dem <xref:System.Threading.Tasks.ParallelOptions>-Parameter an die Methode, und schließen Sie den parallelen Aufruf in einen Try-Catch-Block ein.</span><span class="sxs-lookup"><span data-stu-id="12c50-106">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12c50-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12c50-107">Example</span></span>  

 <span data-ttu-id="12c50-108">Im folgenden Beispiel wird der Abbruch des Aufrufs einer <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="12c50-108">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="12c50-109">Sie können den gleichen Ansatz auf einen <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Aufruf anwenden.</span><span class="sxs-lookup"><span data-stu-id="12c50-109">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="12c50-110">Wenn das Token, das den Abbruch signalisiert, mit dem in der <xref:System.Threading.Tasks.ParallelOptions>-Instanz angegebenen identisch ist, löst die parallele Schleife beim Abbruch eine einzelne <xref:System.OperationCanceledException> aus.</span><span class="sxs-lookup"><span data-stu-id="12c50-110">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="12c50-111">Wenn ein anderes Token den Abbruch verursacht, löst die Schleife eine <xref:System.AggregateException> mit einer <xref:System.OperationCanceledException> als InnerException aus.</span><span class="sxs-lookup"><span data-stu-id="12c50-111">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c50-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12c50-112">See also</span></span>

- [<span data-ttu-id="12c50-113">Datenparallelität</span><span class="sxs-lookup"><span data-stu-id="12c50-113">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="12c50-114">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="12c50-114">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
