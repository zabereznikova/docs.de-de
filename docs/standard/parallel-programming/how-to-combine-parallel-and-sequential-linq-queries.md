---
title: 'Vorgehensweise: Kombinieren von parallelen und sequenziellen LINQ-Abfragen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: 4c04afb23a168a9cff60962bd5a75a65e3ebca4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134186"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="08036-102">Vorgehensweise: Kombinieren von parallelen und sequenziellen LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="08036-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="08036-103">Dieses Beispiel zeigt die Verwendung der <xref:System.Linq.ParallelEnumerable.AsSequential%2A>-Methode, um PLINQ anzuweisen, alle nachfolgenden Operatoren in der Abfrage sequenziell zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="08036-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="08036-104">Sequenzielle Verarbeitung ist zwar in der Regel langsamer als parallele, doch manchmal ist sie erforderlich, um richtige Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="08036-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="08036-105">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="08036-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="08036-106">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="08036-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08036-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08036-107">Example</span></span>  
 <span data-ttu-id="08036-108">Das folgende Beispiel zeigt ein Szenario, in dem <xref:System.Linq.ParallelEnumerable.AsSequential%2A> erforderlich ist, um die Reihenfolge in einer vorherigen Klausel der Abfrage beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="08036-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="08036-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="08036-109">Compiling the Code</span></span>  
 <span data-ttu-id="08036-110">Um diesen Code zu kompilieren und auszuführen, fügen Sie ihn in das [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md)-Projekt ein, fügen Sie eine Zeile für den Methodenaufruf aus `Main` hinzu, und drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="08036-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08036-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08036-111">See also</span></span>

- [<span data-ttu-id="08036-112">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="08036-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
