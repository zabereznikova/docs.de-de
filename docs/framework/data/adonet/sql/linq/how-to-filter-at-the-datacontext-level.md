---
title: 'Vorgehensweise: Filtern Sie auf DataContext-Ebene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 66bbfe19c73f116b8f85cae829bb61bb2da3d4c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644217"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="f7c64-102">Vorgehensweise: Filtern Sie auf DataContext-Ebene</span><span class="sxs-lookup"><span data-stu-id="f7c64-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="f7c64-103">Sie können `EntitySets` auf `DataContext`-Ebene filtern.</span><span class="sxs-lookup"><span data-stu-id="f7c64-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="f7c64-104">Solche Filter gelten für alle Abfragen, die mit dieser <xref:System.Data.Linq.DataContext>-Instanz erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f7c64-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7c64-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7c64-105">Example</span></span>  
 <span data-ttu-id="f7c64-106">Im folgenden Beispiel wird <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> verwendet, um die vorab geladenen Reihenfolgen für Kunden nach `ShippedDate` zu filtern.</span><span class="sxs-lookup"><span data-stu-id="f7c64-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="f7c64-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7c64-107">See also</span></span>
- [<span data-ttu-id="f7c64-108">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="f7c64-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
