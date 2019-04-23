---
title: 'Vorgehensweise: Filtern auf DataContext-Ebene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 343cffa9b1c034068e5abcc652e936f89ee6a992
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084582"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="82221-102">Vorgehensweise: Filtern auf DataContext-Ebene</span><span class="sxs-lookup"><span data-stu-id="82221-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="82221-103">Sie können `EntitySets` auf `DataContext`-Ebene filtern.</span><span class="sxs-lookup"><span data-stu-id="82221-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="82221-104">Solche Filter gelten für alle Abfragen, die mit dieser <xref:System.Data.Linq.DataContext>-Instanz erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="82221-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82221-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82221-105">Example</span></span>  
 <span data-ttu-id="82221-106">Im folgenden Beispiel wird <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> verwendet, um die vorab geladenen Reihenfolgen für Kunden nach `ShippedDate` zu filtern.</span><span class="sxs-lookup"><span data-stu-id="82221-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="82221-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82221-107">See also</span></span>

- [<span data-ttu-id="82221-108">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="82221-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
