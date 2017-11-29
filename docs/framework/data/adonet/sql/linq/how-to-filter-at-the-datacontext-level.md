---
title: 'Gewusst wie: Filtern auf DataContext-Ebene'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69b711802d04e005095167db7df544e0f00d0b19
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="6fe6a-102">Gewusst wie: Filtern auf DataContext-Ebene</span><span class="sxs-lookup"><span data-stu-id="6fe6a-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="6fe6a-103">Sie können `EntitySets` auf `DataContext`-Ebene filtern.</span><span class="sxs-lookup"><span data-stu-id="6fe6a-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="6fe6a-104">Solche Filter gelten für alle Abfragen, die mit dieser <xref:System.Data.Linq.DataContext>-Instanz erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6fe6a-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fe6a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fe6a-105">Example</span></span>  
 <span data-ttu-id="6fe6a-106">Im folgenden Beispiel wird <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> verwendet, um die vorab geladenen Reihenfolgen für Kunden nach `ShippedDate` zu filtern.</span><span class="sxs-lookup"><span data-stu-id="6fe6a-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="6fe6a-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fe6a-107">See Also</span></span>  
 [<span data-ttu-id="6fe6a-108">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="6fe6a-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
