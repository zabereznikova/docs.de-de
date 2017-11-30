---
title: 'Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage'
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
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="080af-102">Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="080af-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="080af-103">Diese Beispiele zeigen, wie zur Steuerung der Reihenfolge in einer PLINQ-Abfrage mithilfe der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> -Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="080af-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="080af-104">Diese Beispiele dienen in erster Linie zur Veranschaulichung der Verwendung "," und können möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="080af-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="080af-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="080af-105">Example</span></span>  
 <span data-ttu-id="080af-106">Im folgende Beispiel behält die Reihenfolge der Quellsequenz.</span><span class="sxs-lookup"><span data-stu-id="080af-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="080af-107">Dies ist manchmal notwendig. beispielsweise erfordern einige Abfrageoperatoren eine geordnete Quellsequenz, um richtige Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="080af-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="080af-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="080af-108">Example</span></span>  
 <span data-ttu-id="080af-109">Das folgende Beispiel zeigt einige Abfrageoperatoren, deren Quellsequenz wahrscheinlich erwartet wird, um sortiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="080af-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="080af-110">Diese Operatoren funktionieren für ungeordnete Sequenzen, aber sie können zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="080af-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="080af-111">Um diese Methode ausgeführt wird, fügen Sie ihn in die PLINQDataSample-Klasse die [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) Projekt, und drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="080af-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="080af-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="080af-112">Example</span></span>  
 <span data-ttu-id="080af-113">Im folgende Beispiel wird die Reihenfolge für den ersten Teil einer Abfrage beibehalten und dann entfernen Sie die Reihenfolge um die Leistung einer Join-Klausel zu erhöhen und die erneute Anwendung für das Endergebnis Sequenzen Sortierung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="080af-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="080af-114">Um diese Methode ausgeführt wird, fügen Sie ihn in die PLINQDataSample-Klasse die [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md) Projekt, und drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="080af-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="080af-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="080af-115">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="080af-116">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="080af-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
