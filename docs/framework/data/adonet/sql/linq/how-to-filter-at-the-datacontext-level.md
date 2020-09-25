---
title: 'Vorgehensweise: Filtern auf DataContext-Ebene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 6fe79febd41c040e430dd772b87ca5624824bb65
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173470"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="bb652-102">Vorgehensweise: Filtern auf DataContext-Ebene</span><span class="sxs-lookup"><span data-stu-id="bb652-102">How to: Filter at the DataContext Level</span></span>

<span data-ttu-id="bb652-103">Sie können `EntitySets` auf `DataContext`-Ebene filtern.</span><span class="sxs-lookup"><span data-stu-id="bb652-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="bb652-104">Solche Filter gelten für alle Abfragen, die mit dieser <xref:System.Data.Linq.DataContext>-Instanz erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bb652-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb652-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb652-105">Example</span></span>  

 <span data-ttu-id="bb652-106">Im folgenden Beispiel wird <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> verwendet, um die vorab geladenen Reihenfolgen für Kunden nach `ShippedDate` zu filtern.</span><span class="sxs-lookup"><span data-stu-id="bb652-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="bb652-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb652-107">See also</span></span>

- [<span data-ttu-id="bb652-108">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="bb652-108">Query Concepts</span></span>](query-concepts.md)
