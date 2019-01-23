---
title: Zurückgeben der Schnittmenge von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: bb1785b12df2e8a835ba49ae59d0448fbebf794c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506822"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="7d359-102">Zurückgeben der Schnittmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="7d359-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="7d359-103">Verwenden Sie den <xref:System.Linq.Queryable.Intersect%2A>-Operator, um die Schnittmenge von zwei Sequenzen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d359-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d359-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d359-104">Example</span></span>  
 <span data-ttu-id="7d359-105">In diesem Beispiel wird <xref:System.Linq.Queryable.Intersect%2A> verwendet, um eine Sequenz aller Länder zurückzugeben, in denen `Customers` (Kunden) und `Employees` (Mitarbeiter) leben.</span><span class="sxs-lookup"><span data-stu-id="7d359-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="7d359-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Intersect%2A>-Operation nur für Sätze gut definiert.</span><span class="sxs-lookup"><span data-stu-id="7d359-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="7d359-107">Die Semantik für Multisets ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="7d359-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d359-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d359-108">See also</span></span>
- [<span data-ttu-id="7d359-109">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="7d359-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="7d359-110">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="7d359-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
