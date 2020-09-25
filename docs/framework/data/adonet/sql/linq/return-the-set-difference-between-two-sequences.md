---
title: Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 49a8d22377ef1f7d0fde16880a82002754e1bbc4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200328"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="fc7cb-102">Zurückgeben der Unterschiedsmenge zwischen zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="fc7cb-102">Return the Set Difference Between Two Sequences</span></span>

<span data-ttu-id="fc7cb-103">Verwenden Sie den <xref:System.Linq.Queryable.Except%2A>-Operator, um die Satzdifferenz zwischen zwei Sequenzen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fc7cb-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc7cb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc7cb-104">Example</span></span>  

 <span data-ttu-id="fc7cb-105">In diesem Beispiel wird verwendet <xref:System.Linq.Queryable.Except%2A> , um eine Sequenz aller Länder/Regionen zurückzugeben, in denen `Customers` Live, aber ohne `Employees` Live ist.</span><span class="sxs-lookup"><span data-stu-id="fc7cb-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="fc7cb-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Except%2A>-Operation nur für Sätze gut definiert.</span><span class="sxs-lookup"><span data-stu-id="fc7cb-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="fc7cb-107">Die Semantik für Multisets ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="fc7cb-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc7cb-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc7cb-108">See also</span></span>

- [<span data-ttu-id="fc7cb-109">Abfrage Beispiele</span><span class="sxs-lookup"><span data-stu-id="fc7cb-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="fc7cb-110">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="fc7cb-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
