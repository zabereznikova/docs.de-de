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
helpviewer_keywords:
- PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3aef90c1a1160905662f93a83d6536f6d804b179
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="f88b4-102">Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="f88b4-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="f88b4-103">Diese Beispiele zeigen die Steuerung der Reihenfolge in einer PLINQ-Abfrage mithilfe der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="f88b4-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f88b4-104">Diese Beispiele sollen primär die Nutzung darstellen und werden möglicherweise nicht schneller ausgeführt als die entsprechenden sequenziellen LINQ to Objects-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="f88b4-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f88b4-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f88b4-105">Example</span></span>  
 <span data-ttu-id="f88b4-106">Im folgenden Beispiel wird die Reihenfolge der Quellsequenz beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f88b4-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="f88b4-107">Dies ist manchmal notwendig. Beispielsweise erfordern einige Abfrageoperatoren eine geordnete Quellsequenz, um richtige Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="f88b4-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="f88b4-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f88b4-108">Example</span></span>  
 <span data-ttu-id="f88b4-109">Das folgende Beispiel zeigt einige Abfrageoperatoren, bei denen wahrscheinlich eine sortierte Quellsequenz zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="f88b4-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="f88b4-110">Diese Operatoren funktionieren bei ungeordneten Sequenzen, aber sie können zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="f88b4-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="f88b4-111">Um diese Methode auszuführen, fügen Sie sie im [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md)-Projekt in die PLINQDataSample-Klasse ein, und drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="f88b4-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f88b4-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f88b4-112">Example</span></span>  
 <span data-ttu-id="f88b4-113">Im folgenden Beispiel werden das Beibehalten der Reihenfolge für den ersten Teil einer Abfrage, dann das Entfernen der Reihenfolge zur Steigerung der Leistung einer Join-Klausel sowie das erneute Anwenden der Reihenfolge für die endgültige Ergebnissequenz gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f88b4-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="f88b4-114">Um diese Methode auszuführen, fügen Sie sie im [PLINQ-Datenbeispiel](../../../docs/standard/parallel-programming/plinq-data-sample.md)-Projekt in die PLINQDataSample-Klasse ein, und drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="f88b4-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f88b4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f88b4-115">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="f88b4-116">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="f88b4-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
